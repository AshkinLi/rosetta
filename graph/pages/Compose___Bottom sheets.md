alias:: Android/Compose/Bottom sheets
tags:: [[Android]], [[Compose]], [[Components]]

- Overview
  heading:: true
	- `Bottom sheets` 用于在屏幕底部显示次要内容，并固定在屏幕底部
	- 在 Compose 中，使用 `ModalBottomSheet` 实现 `Bottom sheets` 功能
	- ![image](https://gist.github.com/user-attachments/assets/625d5e10-c17e-4b08-b1b6-459ae5e53a33)
- Basic Bottom sheet
  heading:: true
	- 以下代码使用 `ModalBottomSheet` 来显示底部弹窗，并通过 `showBottomSheet` 状态进行控制：
		- `rememberModalBottomSheetState()` 和 `rememberCoroutineScope()` 用于管理与底部弹窗交互的状态及协程作用域
		- `ExtendedFloatingActionButton` 点击后将 `showBottomSheet` 设置为 `true`，从而显示底部弹窗
		- `ModalBottomSheet` 可以通过 `onDismissRequest` 来关闭，当 `isVisible` 为 false 时，将 `showBottomSheet` 重置为 `false`
		- 底部弹窗内部有一个按钮，通过调用 `sheetState.hide()` 隐藏底部弹窗，以同样的方式更新 `showBottomSheet`
	- ```kotlin
	  val sheetState = rememberModalBottomSheetState()
	  val scope = rememberCoroutineScope()
	  var showBottomSheet by remember { mutableStateOf(false) }
	  Scaffold(
	      floatingActionButton = {
	          ExtendedFloatingActionButton(
	              text = { Text("Show bottom sheet") },
	              icon = { Icon(Icons.Filled.Add, contentDescription = "") },
	              onClick = {
	                  showBottomSheet = true
	              }
	          )
	      }
	  ) { contentPadding ->
	      // Screen content
	  
	      if (showBottomSheet) {
	          ModalBottomSheet(
	              onDismissRequest = {
	                  showBottomSheet = false
	              },
	              sheetState = sheetState
	          ) {
	              // Sheet content
	              Button(onClick = {
	                  scope.launch { sheetState.hide() }.invokeOnCompletion {
	                      if (!sheetState.isVisible) {
	                          showBottomSheet = false
	                      }
	                  }
	              }) {
	                  Text("Hide bottom sheet")
	              }
	          }
	      }
	  }
	  ```
- Partial bottom sheet
  heading:: true
	- 以下代码实现了一个简单的局部 `Bottom sheet`，当用户点击按钮时显示，用户可以通过滑动手势来控制弹窗的展开和关闭：
		- `PartialBottomSheet` 是一个可组合函数
		- 使用 `remember` 和 `mutableStateOf` 创建一个状态变量 `showBottomSheet`，用于控制底部弹窗的显示与否
		- 使用 `rememberModalBottomSheetState` 创建一个 `sheetState`，用于管理底部弹窗的状态，并设置 `skipPartiallyExpanded` 为 `false`，允许部分展开
		- 在 `Column` 布局中，添加一个按钮，当按钮被点击时，将 `showBottomSheet` 设置为 `true`，显示底部弹窗
		- 使用 `if` 语句检查 `showBottomSheet` 的值，如果为 `true`，则显示 `ModalBottomSheet`
		- `ModalBottomSheet` 的 `modifier` 设置为 `fillMaxHeight()`，使其填满屏幕高度，`sheetState` 设置为之前创建的 `sheetState`，并且 `onDismissRequest` 回调将 `showBottomSheet` 设置为 `false`，以关闭底部弹窗
		- 在 `ModalBottomSheet` 内部，显示一段文本，提示用户可以向上滑动以打开底部弹窗，向下滑动以关闭
	- ```kotlin
	  @Composable
	  fun PartialBottomSheet() {
	      var showBottomSheet by remember { mutableStateOf(false) }
	      val sheetState = rememberModalBottomSheetState(
	          skipPartiallyExpanded = false,
	      )
	  
	      Column(
	          modifier = Modifier.fillMaxWidth(),
	          horizontalAlignment = Alignment.CenterHorizontally,
	      ) {
	          Button(
	              onClick = { showBottomSheet = true }
	          ) {
	              Text("Display partial bottom sheet")
	          }
	  
	          if (showBottomSheet) {
	              ModalBottomSheet(
	                  modifier = Modifier.fillMaxHeight(),
	                  sheetState = sheetState,
	                  onDismissRequest = { showBottomSheet = false }
	              ) {
	                  Text(
	                      "Swipe up to open sheet. Swipe down to dismiss.",
	                      modifier = Modifier.padding(16.dp)
	                  )
	              }
	          }
	      }
	  }
	  ```
	- ![image](https://gist.github.com/user-attachments/assets/bcbaa1a6-c655-40b4-a107-60cb834abfc2){:height 449, :width 272}![image](https://gist.github.com/user-attachments/assets/5b651268-54fc-4752-90b2-4fa97dbc3d1e){:height 444, :width 258}
- Additional resources
  heading:: true
	- [Bottom sheets  |  Jetpack Compose  |  Android Developers](https://developer.android.com/develop/ui/compose/components/bottom-sheets)
	- [Bottom sheets – Material Design 3](https://m3.material.io/components/bottom-sheets/overview)