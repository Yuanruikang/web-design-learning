# 使用包

在 webpack 之前，搜寻整个 node_modules 目录来定位每个包的路径再手动添加到 HTML 文件中，不是很方便

```html
<script scr="./node_modules/jquery/dist/jquery.min.js"></script>
```

之后，通过 CommonJS 的 `require` 来导入语句包

> 参考：
>
> [Node Modules at War: Why CommonJS and ES Modules Can’t Get Along](https://redfin.engineering/node-modules-at-war-why-commonjs-and-es-modules-cant-get-along-9617135eeca1)
>
> [基于 V8 引擎的 JS 执行过程详解](https://segmentfault.com/a/1190000039380905)
>
> [知乎：CommonJs 和 ES6 module 的区别是什么呢？](https://www.zhihu.com/question/62791509)

在 ES6 中可以通过 import 来导入包

# 实例：通过 babel 包来解决 ES6 兼容性问题

兼容低版本浏览器两种方式：

✅ 在线编译（会增加页面渲染时间）

```bash
<head>
    <script crossorigin="anonymous" integrity="sha384-    iQlPtMA6c6YqCm54Nvf5MAtY9MpqiRZVzw3i4bwed99geBlsx5Da1UJgfUmYIHyP" src="https://lib.baomitu.com/babel-core/4.7.16/browser.js"></script>
</head>
<body>
    <script type='text/babel'>
    # type不再是text/javascript
        const name = 'xxx';
        console.log(name);
    </script>
</body>
```

✅ 提前编译（在服务区端先编译好再发送给客户端）

```bash
# 使用NPM全局安装babel-cli
npm i babel-cli -g --save-dev
# 在项目目录下新建.babelrc文件
{
    "presets":["es2015","stage2"], //设置转码格式
    "plugins":["transform-runtime"] // 设置插件
}

# 安装相关库
npm install babel-core babel-preset-es2015 babel-plugin-transform-runtime babel-preset-stage-2 --save-dev

#再打开项目下的package.json文件，做如下修改
"scripts":{"build": "babel src -W -d lib",}

npm run build
```

编译整个 src 目录并将其输出到 lib 目录。这里的 src 指的是需要转换的目录，lib 指的是输出的内容的存放目录，w 是-watch 的意思会实时编译输出

# NPX

[Source1_npx、npm、cnpm、pnpm区别你搞清楚了吗？](https://juejin.cn/post/7083468345579667493)

NPX(Node Package Execute)是一个 [Node package runner](https://nodejs.dev/learn/the-npx-nodejs-package-runner)，可以自动找到并执行指定的包。

```bash
npx webpack
```

上面的命令会自动找到并执行 [webpack](https://www.codesweetly.com/javascript-module-bundler/)。因此，我们不需要在 `package.json` 文件的 `"build": "webpack"` 属性添加到我们的 `package.json` 文件的 `"scripts"` 字段中。

# 如何使用你喜欢的Node.js版本来运行代码

[Source](https://chinese.freecodecamp.org/news/javascript-package-manager-npm-and-yarn/#:~:text=%E5%A6%82%E4%BD%95%E4%BD%BF%E7%94%A8%E4%BD%A0,%E4%BE%8B%E5%A6%82%EF%BC%8Cv7.10.1%E3%80%82)

你可以使用 `@` 字符和 [node npm package](https://www.npmjs.com/package/node) 来指定你希望用来执行代码的Node.js版本。

**这是一个例子：**

```bash
npx node@7 index.js
```

上面的片段告诉NPX用最新的Node 7 major版本来运行`index.js`。

使用`node@`命令是一个有用的方法，可以避免使用Node.js版本管理工具，如[nvm](https://github.com/nvm-sh/nvm)在Node版本之间切换。

假设你想确认NPX将使用哪个Node版本来运行你的代码。在这种情况下，运行：

```bash
npx node@7 -v
```

上面的片段将显示NPX将用于运行你的代码的最新Node版本，即7大版本--例如，`v7.10.1`。
