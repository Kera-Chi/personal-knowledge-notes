### Java - print 的差異

Java 世界中，無人不知無人不曉的 `System.out.print`，堪稱史詩級的存在，地位就跟國文課本第一冊、第一課翻開的「雅量」一樣，一塊一塊的綠豆糕，到死都忘不了XD

今天想分享關於 `print`、`println` 和 `printf` 的細微差異：

1. `print` 和 `println` 用在簡單的文字輸出，而 `printf` 支援格式化字串（formatted string）。
2. `print` 和 `printf` 輸出後不會自動換行，但 `println` 會！
3. `printf` 推薦用 `%n` 換行。（適用所有系統）
4. `println` 用 `\n` 換行。

**範例：**

```java
String name = "AngelChi";
int age = 18;

// 用 print 輸出
System.out.print("我是");
System.out.print("鼎鼎大名: " + name + "，今年 " + age + " 歲！");
// 輸出：我是鼎鼎大名: AngelChi，今年 18 歲！

// 用 println 輸出
System.out.print(ln"我是");
System.out.println("鼎鼎大名: " + name + "，今年 " + age + " 歲！");
// 輸出：
// 我是
// 鼎鼎大名: AngelChi，今年 18 歲！

// 用 printf 輸出
System.out.printf("鼎鼎大名: %s，今年 %d 歲！", name, age);
// 輸出：鼎鼎大名: AngelChi，今年 18 歲！
```