# install module

```bash
npm install <module name> 

# -g或者--global 全局安装，能在命令行里使用 
npm install <module name> -g

# @后面加版本号可以安装指定版本的模块
npm install <module name>@5.1.1 -g

# --save-dev 开发时依赖，--save-dev在package文件的devDependencies节点写入依赖
# devDependencies：开发时的依赖，里面的模块开发时使用，发布后用不到，如项目中使用的gulp，压缩css、js的一些模块
npm install --save-dev <module name>

# 运行时依赖，在生产环境下还需要被使用的模块，--save在package文件的dependencies节点写入依赖
# 默认参数
npm install --save <module name>
```

```bash
# 本地包
npm list

#全局包
npm list -g

# 查看版本号
npm list <module name>
```

**注意**：如果没有安装本地包，这时会调用全局包

⚠️但是在项目中非常不推荐本地包和全局包混用，这会造成项目中被使用的包之间关系不清楚，也不方便在其他机器上直接复用，此外如果升级破坏了与其他包的兼容性，会增大维护难度。

yarn也做了进一步的优化，若要添加全局包，必须用global关键字，而非简单的-g

```bash
yarn global add package-name
```

[NPM](https://www.npmjs.com/)，[React Native CLI](https://reactnative.dev/docs/environment-setup)，[Gatsby CLI](https://www.gatsbyjs.com/docs/reference/gatsby-cli/)，[Grunt CLI](https://gruntjs.com/getting-started), 和 [Vue CLI](https://cli.vuejs.org/) 是可以全局安装的软件包。

本地包的常见例子有 [Webpack](https://webpack.js.org/)，[Lodash](https://lodash.com/)，[Jest](https://jestjs.io/) 和 [MomentJS](https://momentjs.com/)。

# update

查看过时包

```bash
npm outdated package_name | -g 
```

更新包

```bash
npm update package_name | -g
```



> Ref: https://chinese.freecodecamp.org/news/javascript-package-manager-npm-and-yarn/

