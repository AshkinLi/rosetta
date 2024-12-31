heading:: true
alias:: Android/Compose/Button
tags:: [[Android]], [[Compose]], [[Components]]

- Overview
  heading:: true
	- 按钮是基本组件，可让用户触发已定义的操作。按钮有 5 种类型。
	  heading:: true
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
	- 默认情况下，它会填充纯色
	  heading:: true
	- ```kotlin
	  @Composable
	  fun FilledButtonExample(onClick: () -> Unit) {
	      Button(onClick = { onClick() }) {
	          Text("Filled")
	      }
	  }
	  ```
- ## Tonal Button
	- `Tonal Button` 使用 FilledTonalButton 可组合项
	  heading:: true
	- 默认情况下，它会填充色调颜色
	  heading:: true
	- ```kotlin
	  @Composable
	  fun FilledTonalButtonExample(onClick: () -> Unit) {
	      FilledTonalButton(onClick = { onClick() }) {
	          Text("Tonal")
	      }
	  }
	  ```
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