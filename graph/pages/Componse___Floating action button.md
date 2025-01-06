概览
heading:: true
	- 一个浮动操作按钮（FAB）是一个高强调按钮，允许用户在应用程序中执行主要操作。它促进单一、集中的操作，这是用户可能采取的最常见路径，通常固定在屏幕的右下角。
	  heading:: true
	- 以下一些常见的场景，可以考虑使用 FAB：
	  heading:: true
		- **创建新项目（Create new item）**：在记事应用中，FAB 可能被用来快速创建一条新笔记。
		  logseq.order-list-type:: number
		- **添加新联系人（Add new contact）**：在聊天应用中，FAB 可以打开一个界面，让用户将某人添加到对话中。
		  logseq.order-list-type:: number
		- **中心位置（Center location）**：在地图界面中，一个浮动操作按钮可以将地图中心定位到用户的当前位置。
		  logseq.order-list-type:: number
	- 在 Material Design 种，有 4 种类型的 FAB：
	  heading:: true
		- **FAB**：普通尺寸的浮动操作按钮
		  logseq.order-list-type:: number
		- **小型（Small）FAB**：一个较小的浮动操作按钮。
		  logseq.order-list-type:: number
		- **大型（Large）FAB**：一个较大的浮动操作按钮。
		  logseq.order-list-type:: number
		- **扩展（Extended）FAB**：一个包含不仅仅是图标的浮动操作按钮。
		  logseq.order-list-type:: number
- API 接口
  heading:: true
	- FAB 常有的接口有以下几个：
	  heading:: true
		- `onClick`：用户按下按钮时调用的函数
		  logseq.order-list-type:: number
		- `containerColor`：设置按钮的颜色
		  logseq.order-list-type:: number
		- `contentColor`：设置图标的颜色
		  logseq.order-list-type:: number
- Floating action button(FAB)
  heading:: true
	- 创建通用的 FAB，使用 `FloatingActionButton`
	  heading:: true
	- heading:: true
	  ```kotlin
	  @Composable
	  fun Example(onClick: () -> Unit) {
	      FloatingActionButton(
	          onClick = { onClick() },
	      ) {
	          Icon(Icons.Filled.Add, "Floating action button.")
	      }
	  }
	  ```
	- ![image](https://gist.github.com/user-attachments/assets/2626b21a-bdcc-44ac-8d10-24e45255b0b7)
	  heading:: true
- Small button
  heading:: true
	- 创建小型的 FAB，使用 `SmallFloatingActionButton`
	- ```kotlin
	  @Composable
	  fun SmallExample(onClick: () -> Unit) {
	      SmallFloatingActionButton(
	          onClick = { onClick() },
	          containerColor = MaterialTheme.colorScheme.secondaryContainer,
	          contentColor = MaterialTheme.colorScheme.secondary
	      ) {
	          Icon(Icons.Filled.Add, "Small floating action button.")
	      }
	  }
	  ```
	- ![image](https://gist.github.com/user-attachments/assets/46a93ada-fdca-4435-97a0-8e07f14cbd09)
- Large button
  heading:: true
	- 创建大型的 FAB，使用 `LargeFloatingActionButton`
	- ```kotlin
	  @Composable
	  fun LargeExample(onClick: () -> Unit) {
	      LargeFloatingActionButton(
	          onClick = { onClick() },
	          shape = CircleShape,
	      ) {
	          Icon(Icons.Filled.Add, "Large floating action button")
	      }
	  }
	  ```
	- ![image](https://gist.github.com/user-attachments/assets/b28d3e9e-1863-43ca-aab9-e46e23e0020d)
- Extended button
  heading:: true
	- 可以使用ExtendedFloatingActionButton组件创建更复杂的浮动操作按钮。它与FloatingActionButton的主要区别在于它有专门的图标和文本参数。它们让您创建一个具有更复杂内容的按钮，并且能够适当地缩放以适应其内容。
	- ```kotlin
	  @Composable
	  fun ExtendedExample(onClick: () -> Unit) {
	      ExtendedFloatingActionButton(
	          onClick = { onClick() },
	          icon = { Icon(Icons.Filled.Edit, "Extended floating action button.") },
	          text = { Text(text = "Extended FAB") },
	      )
	  }
	  ```
	- ![image](https://gist.github.com/user-attachments/assets/018813b3-0b57-4393-9185-48081f804ace)
- Additional resources
  heading:: true
	- [Componse Buttons]([[Compose/Buttons]])
	  heading:: true
	- [Compose Floating action button](https://developer.android.com/develop/ui/compose/components/fab)
	- [Material Floating action buttons](https://m3.material.io/components/floating-action-button/overview)