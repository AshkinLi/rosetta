alias:: Android/Compose/Badges
tags:: [[Android]], [[Compose]], [[Components]]

- Overview
  heading:: true
	- **Badges** 用于显示一个小的视觉元素，以表示状态或在另一个可组合物上的数值
	- 在以下的场景中，可以考虑使用 **Badges**：
		- **通知（Notifications）**：在应用图标或通知铃铛上显示未读通知的数量
		- **消息（Messages）**：在聊天应用中指示新消息或未读消息
		- **状态更新（Status updates）**：显示任务的状态，例如“已完成”、“进行中”或“失败”
		- **购物车数量（Cart quantity）**：显示用户购物车中的商品数量
		- **新内容（New content）**：突出显示用户可用的新内容或功能
	- ![image](https://gist.github.com/user-attachments/assets/f64b08b2-4294-4d9e-aa8d-5be482f0302e)
- API surface
  heading:: true
	- 请使用 BadgedBox 组合项在应用内实现徽章功能。它本质上是一个容器，可通过以下两个主要参数来自定义外观：
		- content：BadgedBox 所包含的可组合内容，通常是 Icon
		- badge：显示在内容上方的徽章可组合项，通常是专门的 Badge 组件
- Basic example
  heading:: true
	- 以下代码片段展示了 BadgedBox 的基本实现，一个徽章与指定的 Icon 组合项重叠，请注意以下代码点：
		- `BadgedBox` 用作整体容器
		- `BadgedBox` 的 `badge` 参数使用 `Badge`。由于 `Badge` 本身没有任何参数，应用会显示默认徽章——一个小红点
		- `Icon` 用作 `BadgedBox` 的 `content` 参数，即徽章所覆盖的图标。在此示例中为邮件图标
	- ```kotlin
	  @Composable
	  fun BadgeExample() {
	      BadgedBox(
	          badge = {
	              Badge()
	          }
	      ) {
	          Icon(
	              imageVector = Icons.Filled.Mail,
	              contentDescription = "Email"
	          )
	      }
	  }
	  ```
	- ![image](https://gist.github.com/user-attachments/assets/addba8d3-1c34-4e01-9b01-44635ec201ba)
- Detailed example
  heading:: true
	- 以下代码片段演示了如何在 badge 中显示可响应用户操作的数值，此示例实现了一个带有 badge 的购物车图标，用于显示用户购物车中的商品数量：
		- 仅当商品数量大于 0 时，才会显示 `BadgedBox`
		- 通过参数 `containerColor` 和 `contentColor` 控制 badge 的外观
		- `Badge` 的 content 槽中使用 `Text` composable 显示购物车中的商品数量
	- ```kotlin
	  @Composable
	  fun BadgeInteractiveExample() {
	      var itemCount by remember { mutableStateOf(0) }
	  
	      Column(
	          verticalArrangement = Arrangement.spacedBy(16.dp)
	      ) {
	          BadgedBox(
	              badge = {
	                  if (itemCount > 0) {
	                      Badge(
	                          containerColor = Color.Red,
	                          contentColor = Color.White
	                      ) {
	                          Text("$itemCount")
	                      }
	                  }
	              }
	          ) {
	              Icon(
	                  imageVector = Icons.Filled.ShoppingCart,
	                  contentDescription = "Shopping cart",
	              )
	          }
	          Button(onClick = { itemCount++ }) {
	              Text("Add item")
	          }
	      }
	  }
	  ```
	- ![image](https://gist.github.com/user-attachments/assets/56a27037-215f-4cdf-a1f2-07c3f305209f)
- Additional resources
  heading:: true
	- [Material 3 - Badges](https://m3.material.io/components/badges/overview)
	- [`BadgedBox`](https://developer.android.com/reference/kotlin/androidx/compose/material3/package-summary#BadgedBox(kotlin.Function1,androidx.compose.ui.Modifier,kotlin.Function1))
	- [`Badge`](https://developer.android.com/reference/kotlin/androidx/compose/material3/package-summary#Badge(androidx.compose.ui.Modifier,androidx.compose.ui.graphics.Color,androidx.compose.ui.graphics.Color,kotlin.Function1))