tags:: 分布式版本管理系统

- 概览
  heading:: true
	- 分布式版本控制系统（Distributed version control system）
	- 最初由 [[Linus]] 用 [[C 语言]] 编写
- 外部链接
  heading:: true
	- [Git 官方网站](https://git-scm.com/)
- 常用命令
  heading:: true
	- 初始化 `init`
	  heading:: true
		- 初始化一个新的本地仓库：
		  `git init`
		- 使用指定的名称初始化一个仓库作为初始分支：
		  `git init --initial-branch=branch_name`
		- 使用 SHA256 作为对象哈希初始化仓库（需要 Git 版本 2.29+）：
		  `git init --object-format=sha256`
		- 初始化一个基础仓库，适合作为通过SSH使用的远程仓库：
		  `git init --bare`
	- 获取状态 `status`
	  heading:: true
		- 显示已更改（changed）但尚未添加到提交（commit）的文件：
		  `git status`
		- 以简短格式输出：
		  `git status --short`