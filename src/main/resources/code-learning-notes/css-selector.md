### CSS Selector

在 Selenium WebDriver 中，常常會用使用 CSS Selector 進行元素定位。分享一些常用的 CSS Selector 寫法：

- 使用元素標籤名稱進行定位：
  ```java
  By.cssSelector("div")
  ```

- 使用`.`來選擇具有特定 class 的元素：
  ```java
  By.cssSelector(".rank-info")
  ```

- 使用`#`來選擇具有特定 id 的元素：
  ```java
  By.cssSelector("#header")
  ```

- 使用`[attribute=value]`來選擇具有特定屬性和值的元素：
  ```java
  By.cssSelector("[type=text]")
  ```

- 使用`>`來選擇直接的子元素：
  ```java
  By.cssSelector("div > h6")
  ```

- 直接使用空格來選擇所有後代元素：
  ```java
  By.cssSelector("form input")
  ```

- 使用標籤和 class 來進行元素定位：
  ```java
  By.cssSelector("div.container")
  ```
