将博客转移到了Hugo框架上面，比hexo更轻更快，自己需要的功能也都有，同时托管在cloudflare page上面，省去了每年的服务器花销。我借鉴了[@Elizen](https://elizen.me/)的博客，界面很美观。其实Hugo设置主题很简单，只需要花一点时间，把各位大佬的源码仓库下载下来，仔细看看，实在看不懂，直接copy代码😂。


Hugo在安装主题的时候，官方建议使用子模块的形式进行安装，也就是`git submodule add ...`的方式。但是在卸载主题模块的时候，官方文档就没有给出教程了。所以把卸载submodule的方法记录下来，希望对计算机小白有所帮助。


```shell
$ git submodule deinit -f {path}
$ rm -rf .git/modules {path}
$ git rm -f {path}
```


命令 `git submodule deninit` 取消注册子模块 。它从 `git/config` 文件中删除整个 `submodule.$name` 部分。此外，它还删除了子模块的工作树。


项目目录中带有 子模块路径的命令 `git rm` 删除了超级项目（我们的项目）的跟踪数据。它删除了 `gitlink` 条目。此外，它消除了 `.gitmodules` 文件中存在的子模块部分并暂存该文件。


<!-- ##{"timestamp":1668474761}## -->