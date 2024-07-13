## 【不專業筆記分享 36】Stream API 的小陷阱

分享一下小菜雞的 debug 日常~

在這個 list 中，`findAny` 沒有隨機回傳元素給我！每次資料都一定從第一筆開始打印，啊我明明就 `findAny` 了，你到底是想怎樣膩！！！

結果，這小傢伙，這小壞蛋，魔鬼藏在細節裡...

`findAny` 在這裡之所以沒有達到它字面上的功能，是因為 `questions.stream()`。在這個步驟的 stream 是建立一個「順序流」，代表資料的處理會依照列表的順序，所以在 stream 中的 `findAny` 就有點類似 `findFirst`。

反之，如果是 `parallelStream` 的話，使用 `findFirst` 很可能會因為資料並行處理，導致於沒辦法如期地返回所謂的「第一個」元素，因為大家一起處理，也不知道到底哪個是第一個，但用 `findAny` 的話就會剛剛好~

### 範例代碼

```java
Question question = questions.stream()
    .filter(q -> q.getDifficulty().equalsIgnoreCase(difficulty) && !q.isAnswered())
    .findAny()
    .orElse(null);
```