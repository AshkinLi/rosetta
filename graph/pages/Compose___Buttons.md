heading:: true
alias:: Android/Compose/Buttons
tags:: [[Android]], [[Compose]], [[Components]]
title:: Compose/Buttons

- Overview
  heading:: true
	- 按钮是基本组件，可让用户触发已定义的操作。按钮有 5 种类型。
	  heading:: true
	- ![image](https://gist.github.com/user-attachments/assets/1e77dbff-22aa-4368-b6d7-b747ddffa518)
- ## API Surface
	- `onClick`：用户按下按钮时调用的函数。
	  heading:: true
	- `enabled`：如果为 false，此参数会导致按钮显示为不可用且处于非活动状态。
	  heading:: true
	- `colors`：一个 `ButtonColors` 实例，用于确定按钮中使用的颜色。
	  heading:: true
	- `contentPadding`：按钮内的内边距。
	  heading:: true
- ## Filled Button
	- `Filled Button` 使用基本 Button 可组合项
	  heading:: true
	- 默认情况下，它会填充纯色（primaryColor）
	  heading:: true
	- ```kotlin
	  @Composable
	  fun FilledButtonExample(onClick: () -> Unit) {
	      Button(onClick = { onClick() }) {
	          Text("Filled")
	      }
	  }
	  ```
	- ![image](https://gist.github.com/user-attachments/assets/ce42c5c6-f37c-4942-a954-48ad0ea002e5)
- ## Tonal Button
	- `Tonal Button` 使用 FilledTonalButton 可组合项
	  heading:: true
	- 默认情况下，它会填充色调颜色（tonal color）
	  heading:: true
	- ```kotlin
	  @Composable
	  fun FilledTonalButtonExample(onClick: () -> Unit) {
	      FilledTonalButton(onClick = { onClick() }) {
	          Text("Tonal")
	      }
	  }
	  ```
	- ![image](https://gist.github.com/user-attachments/assets/690fc479-02b8-4da4-a80d-ccae39612985)
- ## Outlined Button
	- `Outlined Button` 默认情况下，它会显示轮廓
	  heading:: true
	- ```kotlin
	  @Composable
	  fun OutlinedButtonExample(onClick: () -> Unit) {
	      OutlinedButton(onClick = { onClick() }) {
	          Text("Outlined")
	      }
	  }
	  ```
	- ![image](https://gist.github.com/user-attachments/assets/a380129f-4d65-44bb-aada-f729e6566023)
- ## Elevated Button
	- `Elevated Button` 默认情况下，它具有表示高度效果的阴影
	  heading:: true
	- `Elevated Button` 本质上是一个带阴影的外轮廓按钮
	  heading:: true
	- ```kotlin
	  @Composable
	  fun ElevatedButtonExample(onClick: () -> Unit) {
	      ElevatedButton(onClick = { onClick() }) {
	          Text("Elevated")
	      }
	  }
	  ```
	- ![image](https://gist.github.com/user-attachments/assets/0d116e0d-23e3-4410-8929-225d1872943d)
- ## Text Button
	- `Text Button` 在被按下之前，它只会显示文本
	  heading:: true
	- 默认情况下，它没有实心填充或轮廓
	  heading:: true
	- heading:: true
	  ```kotlin
	  @Composable
	  fun TextButtonExample(onClick: () -> Unit) {
	      TextButton(
	          onClick = { onClick() }
	      ) {
	          Text("Text Button")
	      }
	  }
	  ```
	- ![image](https://gist.github.com/user-attachments/assets/496d59c6-50d2-49e4-866a-60d7606f5178)
