# package.json 属性说明
* name - 包名
* version - 包的版本号
* description - 对包的描述
* homepage - 包的官网 url
* author - 包的作者姓名
* contributors - 包的其他贡献者姓名
* dependencies - 依赖包列表，如果没有安装依赖包，npm会自动把依赖包安装在node_module目录下
* repository - 包代码存放位置的类型，git 或 svn
* main - main字段指定了程序的主入口文件，require('moduleName')就会加载此文件。main字段默认值为模块根目录下的index.js
* keywords - 包
* 版本号说明 - “5.0.3”表示安装指定的5.0.3版本，“~5.0.3”表示安装5.0.X中最新版本，"^5.0.3"表示安装5.X.X中最新版 具体参照[使用 npm 的语义版本控制](http://nodejs.cn/learn/semantic-versioning-using-npm)
* private - 让软件包管理员知道他们是否应该将你的项目发布到 NPM registry

  如果你把package.json的 `"private"` 属性设置为 `true`，包管理器将不会发布你的项目

  因此，设置该属性可以防止意外发布你的包

如果没有package.json配置文件，自动生成：

```bash
npm init --yes | -y
```

可以手动输入条目，一项一项填写

```bash
npm init
# 直接回车
> This utility will walk you through creating a package.json file.
> It only covers the most common items, and tries to guess sensible defaults.

> See `npm help json` for definitive documentation on these fields
> and exactly what they do.

> Use `npm install <pkg> --save` afterwards to install a package and
> save it as a dependency in the package.json file.

> Press ^C at any time to quit.
package name:
```

输入完毕后，如下

```bash
Press ^C at any time to quit.
package name: (connor) learn-2207
version: (1.0.0)
description:
entry point: (index.js)
test command: echo 'hello js'
git repository:
keywords: learn
author: connor
license: (ISC) MIT
About to write to /Users/connor/package.json:

{
  "dependencies": {
    "bootstrap": "^5.1.3",
    "jquery": "^3.6.0"
  },
  "name": "learn-2207",
  "version": "1.0.0",
  "main": "index.js",
  "devDependencies": {},
  "scripts": {
    "test": "echo 'hello js'"
  },
  "keywords": [
    "learn"
  ],
  "author": "connor",
  "license": "MIT",
  "description": ""
}


Is this OK? (yes) y
```

其中test部分的脚本可以运行，如上所示

```bash
npm run test
> hello
```

拿到别人的package.json后，直接`npm install`会自动安装package.json中各种包包括其依赖包

# package-lock.json 文件

在版本 5 中，npm 引入了 `package-lock.json` 文件。<a href="#shili" >示例</a>

该文件旨在跟踪被安装的每个软件包的确切版本，以便产品可以以相同的方式被 100％ 复制（即使软件包的维护者更新了软件包）。

这解决了 `package.json` 一直尚未解决的特殊问题。 在 package.json 中，可以使用 semver 表示法设置要升级到的版本（补丁版本或次版本），例如：

- 如果写入的是 `〜0.13.0`，则只更新补丁版本：即 `0.13.1` 可以，但 `0.14.0` 不可以。
- 如果写入的是 `^0.13.0`，则要更新补丁版本和次版本：即 `0.13.1`、`0.14.0`、依此类推。
- 如果写入的是 `0.13.0`，则始终使用确切的版本。

无需将 node_modules 文件夹（该文件夹通常很大）提交到 Git，当尝试使用 `npm install` 命令在另一台机器上复制项目时，如果指定了 `〜` 语法并且软件包发布了补丁版本，则该软件包会被安装。 `^` 和次版本也一样。

> 如果指定确切的版本，例如示例中的 `0.13.0`，则不会受到此问题的影响。

可能是你，或者是其他人，会在某处尝试通过运行 `npm install` 初始化项目。

因此，原始的项目和新初始化的项目实际上是不同的。 即使补丁版本或次版本不应该引入重大的更改，但还是可能引入缺陷。

`package-lock.json` 会固化当前安装的每个软件包的版本，当运行 `npm install`时，`npm` 会使用这些确切的版本。

这个概念并不新鲜，其他编程语言的软件包管理器（例如 PHP 中的 Composer）使用类似的系统已有多年。

`package-lock.json` 文件需要被提交到 Git 仓库，以便被其他人获取（如果项目是公开的或有合作者，或者将 Git 作为部署源）。

当运行 `npm update` 时，`package-lock.json` 文件中的依赖的版本会被更新。

<a id="shili">示例</a>

这是在空文件夹中运行 `npm install cowsay` 时获得的 `package-lock.json` 文件的示例结构：

```json
JSON
{
  "requires": true,
  "lockfileVersion": 1,
  "dependencies": {
    "ansi-regex": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/ansi-regex/-/ansi-regex-3.
0.0.tgz",
      "integrity": "sha1-7QMXwyIGT3lGbAKWa922Bas32Zg="
    },
    "cowsay": {
      "version": "1.3.1",
      "resolved": "https://registry.npmjs.org/cowsay/-/cowsay-1.3.1.tgz"
,
      "integrity": "sha512-3PVFe6FePVtPj1HTeLin9v8WyLl+VmM1l1H/5P+BTTDkM
Ajufp+0F9eLjzRnOHzVAYeIYFF5po5NjRrgefnRMQ==",
      "requires": {
        "get-stdin": "^5.0.1",
        "optimist": "~0.6.1",
        "string-width": "~2.1.1",
        "strip-eof": "^1.0.0"
      }
    },
    "get-stdin": {
      "version": "5.0.1",
      "resolved": "https://registry.npmjs.org/get-stdin/-/get-stdin-5.0.
1.tgz",
      "integrity": "sha1-Ei4WFZHiH/TFJTAwVpPyDmOTo5g="
    },
    "is-fullwidth-code-point": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/is-fullwidth-code-point/-/
is-fullwidth-code-point-2.0.0.tgz",
      "integrity": "sha1-o7MKXE8ZkYMWeqq5O+764937ZU8="
    },
    "minimist": {
      "version": "0.0.10",
      "resolved": "https://registry.npmjs.org/minimist/-/minimist-0.0.10
.tgz",
      "integrity": "sha1-3j+YVD2/lggr5IrRoMfNqDYwHc8="
    },
    "optimist": {
      "version": "0.6.1",
      "resolved": "https://registry.npmjs.org/optimist/-/optimist-0.6.1.tgz",
      "integrity": "sha1-2j6nRob6IaGaERwybpDrFaAZZoY=",


      "requires": {
        "minimist": "~0.0.1",
        "wordwrap": "~0.0.2"
      }
    },
    "string-width": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/string-width/-/string-width-2.1.1.tgz",
      "integrity": "sha512-nOqH59deCq9SRHlxq1Aw85Jnt4w6KvLKqWVik6oA9ZklXLNIOlqg4F2yrT1MVaTjAqvVwdfeZ7w7aCvJD7ugkw==",
      "requires": {
        "is-fullwidth-code-point": "^2.0.0",
        "strip-ansi": "^4.0.0"
      }
    },
    "strip-ansi": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/strip-ansi/-/strip-ansi-4.0.0.tgz",
      "integrity": "sha1-qEeQIusaw2iocTibY1JixQXuNo8=",
      "requires": {
        "ansi-regex": "^3.0.0"
      }
    },
    "strip-eof": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/strip-eof/-/strip-eof-1.0.0.tgz",
      "integrity": "sha1-u0P/VZim6wXYm1n80SnJgzE2Br8="
    },
    "wordwrap": {
      "version": "0.0.3",
      "resolved": "https://registry.npmjs.org/wordwrap/-/wordwrap-0.0.3.tgz",
      "integrity": "sha1-o9XabNXAvAAI03I0u68b7WMFkQc="
    }
  }
}
```

安装 `cowsay`，其依赖于：

- `get-stdin`
- `optimist`
- `string-width`
- `strip-eof`

这些软件包还需要其他软件包，正如从 `require` 属性可以看到的：

- `ansi-regex`
- `is-fullwidth-code-point`
- `minimist`
- `wordwrap`
- `strip-eof`

它们会按字母顺序被添加到文件中，每个都有 `version` 字段、指向软件包位置的 `resolved` 字段、以及用于校验软件包的 `integrity` 字符串。

