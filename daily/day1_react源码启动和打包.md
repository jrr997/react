这是React学习日记的开端。读react源码的目的是：

1. 了解react的如何运行
2. 通过看优秀的开源代码来提升自己的代码质量



day1:

今天的主要任务是:

1. 把react源码项目运行起来。
2. 初始化react学习日记。

任务1：

1. 下载项目。从github上fork react，然后clone到本地。
2. 安装依赖。此次看的是react最新的打了tag的源码(v17.0.2)，因此本地切分支到origin/17.0.2，然后执行`yarn`。
   - 这里有坑，为什么不用npm？因为`npm i`会报错: module not found，我也不知道为什么。
3. 打包。只要打包react和react-dom即可。执行命令: `yarn build react/index react-dom/index`。
   - 这里的坑是打包时需要用到java环境，否则报错: The build stops with the error: "process spawn error. is java in the path spawn java enoent"。解决方法是安装jdk。另一个坑是powershell和cmd都能执行`java -version`命令，但是vscode终端却找不到这个命令。网上搜了答案，都说用管理员身份启动vscode，但是试了无效。在公司的尝试了几次在powershell中执行`set-executionpolicy remotesigned`并选择Y，然后vscode居然成功找到了java命令。但是在家里的笔记本却不行。在家的解决方案是vscode终端右上角，选择cmd，可以找到java命令。
4. 调试源码。[react官网原话](https://react.docschina.org/docs/how-to-contribute.html)：
   1. *想测试你做出的更改的话，最简单的方法就是运行 `yarn build react/index,react-dom/index --type=UMD`，之后再打开 `fixtures/packaging/babel-standalone/dev.html`，该文件已使用 `build` 文件夹内的 `react.development.js` 来搞定你的更改。**
   2. **如果你想测试你对已有 React 项目做出的更改，你可以复制 `build/dist/react.development.js` 和 `build/dist/react-dom.development.js` 或其它构建版本，放入你的应用中并使用这些构建版本而非稳定版。*

任务2：成果就是目前看到的这些。如果看了代码没有留下痕迹，过一两个星期就会忘记，相当于白看，这就是日记存在的意义。