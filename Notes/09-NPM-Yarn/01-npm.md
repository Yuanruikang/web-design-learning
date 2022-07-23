# npm

[npm](www.npmjs.com)全称为Node Package Manager，即Node包管理器。其是Node.js 默认的且以Javascript编写的软件包管理系统

npm用来解决各种包之间的依赖关系和包版本，不用程序员手动配置，主要干这么几个事情：

- 找到你需要使用的软件包，下载并自定义安装
- 验证软件包漏洞，并尝试修复（yarn audit fix）
- 更新和删除软件包，并管理所有软件包的版本
- 协助开发自己的软件包并发布

# Install npm

npm 是Node.js 默认的软件包管理系统，安装Node后，会默认安装好npm，npm最开始是为Node.js服务的

> npm is written entirely in JavaScript and was developed by Isaac Z. Schlueter as a result of having "seen module packaging done terribly" and with inspiration from other similar projects such as [PEAR](https://en.wikipedia.org/wiki/PEAR) ([PHP](https://en.wikipedia.org/wiki/PHP)) and [CPAN](https://en.wikipedia.org/wiki/CPAN) ([Perl](https://en.wikipedia.org/wiki/Perl)).[8](https://en.wikipedia.org/wiki/Npm_(software)#cite_note-8)

```bash
# macOS
brew install node
node -v
npm -v
```

To be sure that this matches the latest version, scroll to the bottom of this page. If the version you see does not match the latest version, run:

```bash
npm install npm@latest -g
# g 为global 全局安装
```

## 安装镜像

查看当前安装源

```bash
npm config get registry
# 或者
npm config list [-g]
```

设定其他镜像

```bash
# taobao 全局设置需要增加--global
npm config set registry https://registry.npmmirror.com --global
# tencent
npm config set registry http://mirrors.cloud.tencent.com/npm/ --global
```

使用nrm工具切换源

```bash
npx nrm use taobao
## 再切换回去
npx nrm use npm
```

But, 用nvm来管理多版本node

> Since npm and node.js products are managed by different entities, updates and maintenance can become complex. Also, the Node.js installation process installs npm in a directory that only has local permissions. This can cause permissions errors when you attempt to run packages globally.
>
> To solve both these issues, many developers opt to use a *node version manager*, or *nvm*, to install npm. The version manager will avoid permissions errors, and will solve the complexities of updating Node.js and npm.
>
> In addition, developers can use an nvm to test their applications on multiple versions of npm. The nvm enables you to easily switch npm as well as node versions. This makes it easier to ensure that your applications work for most users, even if they are using other versions of npm. If you decide to install a version manager, use the instructions for the version manager you select to learn how to switch versions, and to learn how to keep up-to-date with the latest version of npm.