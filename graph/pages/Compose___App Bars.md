heading:: true
alias:: Android/Compose/App Bars
tags:: [[Android]], [[Compose]], [[Components]]

- Usage
  heading:: true
  collapsed:: true
	- 应用栏是屏幕顶部或底部的容器，它们为用户提供访问关键功能和导航项的入口：
	  heading:: true
		- **Top app bar**
		  heading:: true
			- 位于屏幕顶部
			  heading:: true
			- 提供访问关键任务和信息的功能。通常包含标题、核心操作项和某些导航项
			  heading:: true
		- **Bottom app bar**
		  heading:: true
			- 位于屏幕底部
			  heading:: true
			- 通常包括核心导航项。可能通过使用一个浮动操作按钮来访问其他操作
			  heading:: true
- Top app bar
  heading:: true
  collapsed:: true
	- **Small top app bar**
	  heading:: true
		- heading:: true
		  ```Kotlin
		  @Composable
		  fun SmallTopAppBarExample() {
		      Scaffold(
		          topBar = {
		              TopAppBar(
		                  colors = TopAppBarDefaults.topAppBarColors(
		                      containerColor = MaterialTheme.colorScheme.primaryContainer,
		                      titleContentColor = MaterialTheme.colorScheme.primary,
		                  ),
		                  title = {
		                      Text("Small Top App Bar")
		                  }
		              )
		          },
		      ) { innerPadding ->
		          ScrollContent(innerPadding)
		      }
		  }
		  ```
		- ![appbar-small](https://github.com/user-attachments/assets/abe55c64-9597-481a-8926-449a4eef407e)
		  heading:: true
	- **Center-aligned top app bar**
	  heading:: true
		- heading:: true
		  ```kotlin
		  @Composable
		  fun CenterAlignedTopAppBarExample() {
		      val scrollBehavior = TopAppBarDefaults.pinnedScrollBehavior(rememberTopAppBarState())
		  
		      Scaffold(
		          modifier = Modifier.nestedScroll(scrollBehavior.nestedScrollConnection),
		  
		          topBar = {
		              CenterAlignedTopAppBar(
		                  colors = TopAppBarDefaults.centerAlignedTopAppBarColors(
		                      containerColor = MaterialTheme.colorScheme.primaryContainer,
		                      titleContentColor = MaterialTheme.colorScheme.primary,
		                  ),
		                  title = {
		                      Text(
		                          "Centered Top App Bar",
		                          maxLines = 1,
		                          overflow = TextOverflow.Ellipsis
		                      )
		                  },
		                  navigationIcon = {
		                      IconButton(onClick = { /* do something */ }) {
		                          Icon(
		                              imageVector = Icons.AutoMirrored.Filled.ArrowBack,
		                              contentDescription = "Localized description"
		                          )
		                      }
		                  },
		                  actions = {
		                      IconButton(onClick = { /* do something */ }) {
		                          Icon(
		                              imageVector = Icons.Filled.Menu,
		                              contentDescription = "Localized description"
		                          )
		                      }
		                  },
		                  scrollBehavior = scrollBehavior,
		              )
		          },
		      ) { innerPadding ->
		          ScrollContent(innerPadding)
		      }
		  }
		  ```
		- ![appbar-centered](https://github.com/user-attachments/assets/8f6a552f-fc7c-4a42-8ea5-398daa8ac1f4){:height 379, :width 718}
		  heading:: true
	- **Medium top app bar**
	  heading:: true
		- heading:: true
		  ```kotlin
		  @Composable
		  fun MediumTopAppBarExample() {
		      val scrollBehavior = TopAppBarDefaults.enterAlwaysScrollBehavior(rememberTopAppBarState())
		  
		      Scaffold(
		          modifier = Modifier.nestedScroll(scrollBehavior.nestedScrollConnection),
		          topBar = {
		              MediumTopAppBar(
		                  colors = TopAppBarDefaults.topAppBarColors(
		                      containerColor = MaterialTheme.colorScheme.primaryContainer,
		                      titleContentColor = MaterialTheme.colorScheme.primary,
		                  ),
		                  title = {
		                      Text(
		                          "Medium Top App Bar",
		                          maxLines = 1,
		                          overflow = TextOverflow.Ellipsis
		                      )
		                  },
		                  navigationIcon = {
		                      IconButton(onClick = { /* do something */ }) {
		                          Icon(
		                              imageVector = Icons.AutoMirrored.Filled.ArrowBack,
		                              contentDescription = "Localized description"
		                          )
		                      }
		                  },
		                  actions = {
		                      IconButton(onClick = { /* do something */ }) {
		                          Icon(
		                              imageVector = Icons.Filled.Menu,
		                              contentDescription = "Localized description"
		                          )
		                      }
		                  },
		                  scrollBehavior = scrollBehavior
		              )
		          },
		      ) { innerPadding ->
		          ScrollContent(innerPadding)
		      }
		  }
		  ```
		- https://developer.android.com/static/develop/ui/compose/images/components/appbar-scroll.mp4
		  heading:: true
	- **Large top app bar**
	  heading:: true
		- heading:: true
		  ```kotlin
		  @Composable
		  fun LargeTopAppBarExample() {
		      val scrollBehavior = TopAppBarDefaults.exitUntilCollapsedScrollBehavior(rememberTopAppBarState())
		  
		      Scaffold(
		          modifier = Modifier.nestedScroll(scrollBehavior.nestedScrollConnection),
		          topBar = {
		              LargeTopAppBar(
		                  colors = TopAppBarDefaults.topAppBarColors(
		                      containerColor = MaterialTheme.colorScheme.primaryContainer,
		                      titleContentColor = MaterialTheme.colorScheme.primary,
		                  ),
		                  title = {
		                      Text(
		                          "Large Top App Bar",
		                          maxLines = 1,
		                          overflow = TextOverflow.Ellipsis
		                      )
		                  },
		                  navigationIcon = {
		                      IconButton(onClick = { /* do something */ }) {
		                          Icon(
		                              imageVector = Icons.AutoMirrored.Filled.ArrowBack,
		                              contentDescription = "Localized description"
		                          )
		                      }
		                  },
		                  actions = {
		                      IconButton(onClick = { /* do something */ }) {
		                          Icon(
		                              imageVector = Icons.Filled.Menu,
		                              contentDescription = "Localized description"
		                          )
		                      }
		                  },
		                  scrollBehavior = scrollBehavior
		              )
		          },
		      ) { innerPadding ->
		          ScrollContent(innerPadding)
		      }
		  }
		  ```
		- ![appbar-large](https://github.com/user-attachments/assets/9b587713-c592-4491-a4f2-b29de8572400)
		  heading:: true
- Bottom app bar
  heading:: true
  collapsed:: true
	- `BottomAppBar` 常用参数如下：
	  heading:: true
		- `actions`：一系列图标出现在工具栏的左侧。这些通常是给定屏幕的关键操作或导航项。
		  heading:: true
		- `floatingActionButton`：出现在栏右侧的浮动操作按钮。
		  heading:: true
	- **Bottom app bar**
	  heading:: true
		- heading:: true
		  ```kotlin
		  @Composable
		  fun BottomAppBarExample() {
		      Scaffold(
		          bottomBar = {
		              BottomAppBar(
		                  actions = {
		                      IconButton(onClick = { /* do something */ }) {
		                          Icon(Icons.Filled.Check, contentDescription = "Localized description")
		                      }
		                      IconButton(onClick = { /* do something */ }) {
		                          Icon(
		                              Icons.Filled.Edit,
		                              contentDescription = "Localized description",
		                          )
		                      }
		                      IconButton(onClick = { /* do something */ }) {
		                          Icon(
		                              Icons.Filled.Mic,
		                              contentDescription = "Localized description",
		                          )
		                      }
		                      IconButton(onClick = { /* do something */ }) {
		                          Icon(
		                              Icons.Filled.Image,
		                              contentDescription = "Localized description",
		                          )
		                      }
		                  },
		                  floatingActionButton = {
		                      FloatingActionButton(
		                          onClick = { /* do something */ },
		                          containerColor = BottomAppBarDefaults.bottomAppBarFabColor,
		                          elevation = FloatingActionButtonDefaults.bottomAppBarFabElevation()
		                      ) {
		                          Icon(Icons.Filled.Add, "Localized description")
		                      }
		                  }
		              )
		          },
		      ) { innerPadding ->
		          Text(
		              modifier = Modifier.padding(innerPadding),
		              text = "Example of a scaffold with a bottom app bar."
		          )
		      }
		  }
		  ```
		- ![appbar-bottom](https://github.com/user-attachments/assets/d88d9d96-286b-4c47-bd33-059374501fbe)
		  heading:: true
- Key points
  heading:: true
  collapsed:: true
	- 将 `app bars` 传递给 `Scaffold` 组合，它有特定的参数来接收它们。
	  heading:: true
	- `Top app bar` 常用参数如下：
	  heading:: true
		- `title`：标题
		  heading:: true
		- `navigationIcon`：用于导航的主要图标，显示在 `Top app bar` 的左侧。
		  heading:: true
		- `actions`：提供用户访问关键操作的图标，出现在 `Top app bar` 的右侧。
		  heading:: true
		- `scrollBehavior`：确定顶部 `Top app bar` 如何响应 `Scaffold` 内部内容的滚动。
		  heading:: true
		- `colors`：决定 `Top app bar` 的外观。
		  heading:: true
	- 使用 `TopAppBarScrollBehavior` 来控制 `Top app bar` 的行为，有 3 种类型可选：
	  heading:: true
		- `enterAlwaysScrollBehavior`：当用户向上滑动的时候，`Top app bar` 会折叠。当用户向下滑动时，`Top app bar` 会展开。
		  heading:: true
		- `exitUntilCollapsedScrollBehavior`：类似于 `enterAlwaysScrollBehavior`，不过当用户滚动到底部时，`Top app bar` 也会展开。
		  heading:: true
		- `pinnedScrollBehavior`：`Top app bar` 保持固定，不会随着滚动而变化。
		  heading:: true
- External links
  heading:: true
  collapsed:: true
	- **UI Specs**
	  heading:: true
		- [Bottom app bar](https://m3.material.io/components/bottom-app-bar/overview)
		  heading:: true
		- [Top app bars](https://m3.material.io/components/top-app-bar/overview)
		  heading:: true
	- **Quick Guides**
	  heading:: true
		- [Display an app bar](https://developer.android.com/quick-guides/content/display-app-bar)
		  heading:: true
		- [Display a bottom app bar](https://developer.android.com/quick-guides/content/display-bottom-app-bar)
		  heading:: true
		- [Display a top app bar](https://developer.android.com/quick-guides/content/display-top-app-bar)
		  heading:: true