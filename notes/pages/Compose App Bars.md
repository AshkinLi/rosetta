- 应用栏是屏幕顶部或底部的容器，它们为用户提供访问关键功能和导航项的入口：
	- **Top app bar**
		- 位于屏幕顶部
		- 提供访问关键任务和信息的功能。通常包含标题、核心操作项和某些导航项
	- **Bottom app bar**
		- 位于屏幕底部
		- 通常包括核心导航项。可能通过使用一个浮动操作按钮来访问其他操作
- ## Top app bar
	- Small top app bar
		- ```Kotlin
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
		  ![appbar-small](https://github.com/user-attachments/assets/abe55c64-9597-481a-8926-449a4eef407e)
	- Center-aligned top app bar
		- ```kotlin
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
		  ![appbar-centered](https://github.com/user-attachments/assets/8f6a552f-fc7c-4a42-8ea5-398daa8ac1f4)
	- Medium top app bar
		- ```kotlin
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
		  https://developer.android.com/static/develop/ui/compose/images/components/appbar-scroll.mp4
	- Large top app bar
		- ```kotlin
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
		  ![appbar-large](https://github.com/user-attachments/assets/9b587713-c592-4491-a4f2-b29de8572400)