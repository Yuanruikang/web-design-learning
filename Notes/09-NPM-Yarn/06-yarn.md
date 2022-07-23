# yarn优势

> Yarn is a package manager for your code. It allows you to use and share code with other developers from around the world. Yarn does this quickly, securely, and reliably so you don't ever have to worry.
>
> Yarn allows you to use other developers' solutions to different problems, making it easier for you to develop your software. If you have problems, you can report issues or contribute back on [GitHub](https://github.com/yarnpkg/berry), and when the problem is fixed, you can use Yarn to keep it all up to date.
>
> Code is shared through something called a **package**. A package contains all the code being shared as well as a `package.json` file (called a **manifest**) which describes the package.

* stable
* Offline Cache 
  - yarn add  <module_name> --offline
* reproducible
  - Lockfile

# yarn基础命令

```bash
# 安装yarn
npm i -g yarn
brew install yarn

# 特别说明
brew 安装的yarn是yarn1
如果想升级到yarn2👇
yarn set version berry
#再初始化
yarn init -2
```
```shell
# 更新
yarn set version stable

# 安装其他版本
#try out the very latest master branch to check if a bug has been fixed. This #has become very simple! Just run the following command:
yarn set version from sources

#Similarly, specific PRs can be installed using the --branch flag:
yarn set version from sources --branch 1211
```

```bash
#Accessing the list of commands
yarn help

#Starting a new project
yarn init

#Installing all the dependencies
yarn
yarn install

#Adding a dependency
yarn add [package]
yarn add [package]@[version]
yarn add [package]@[tag]
#
Adding a dependency to different categories of dependencies
yarn add [package] --dev  # dev dependencies
yarn add [package] --peer # peer dependencies

#Upgrading a dependency
yarn up [package]
yarn up [package]@[version]
yarn up [package]@[tag]

#Removing a dependency
yarn remove [package]

#Upgrading Yarn itself
yarn set version latest
yarn set version from sources
```

解释[peerdependency](https://blog.bitsrc.io/understanding-peer-dependencies-in-javascript-dbdb4ab5a7be)

# yarn workspace

[yarn workspace使用指南🧭](https://zhuanlan.zhihu.com/p/381794854)

