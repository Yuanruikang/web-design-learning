# npm fund

[Source](https://stackoverflow.com/questions/58972251/what-does-x-packages-are-looking-for-funding-mean-when-running-npm-install)

> When you run `npm update` in the command prompt, when it is done it will recommend you type a new command called `npm fund`.
>
> **When you run `npm fund` it will list all the modules and packages you have installed that were created by companies or organizations that need \*money\* for their IT projects.** You will see a list of webpages where you can send them money. So "funds" means "Angular packages you installed that could use some money from you as an option to help support their businesses".
>
> It's basically a list of the modules you have that need contributions or donations of money to their projects and which list websites where you can enter a credit card to help pay for them.

# 版本号

[Source](https://www.runoob.com/nodejs/nodejs-npm.html#:~:text=npm%20%E6%9D%A5%E5%AE%89%E8%A3%85%E3%80%82-,%E7%89%88%E6%9C%AC%E5%8F%B7,%E7%89%88%E6%9C%AC%E5%8F%B7%E8%8C%83%E5%9B%B4%E6%8C%87%E5%AE%9A%E6%96%B9%E5%BC%8F%E5%8F%AF%E4%BB%A5%E6%9F%A5%E7%9C%8B%E5%AE%98%E6%96%B9%E6%96%87%E6%A1%A3%E3%80%82,-NPM%20%E5%B8%B8%E7%94%A8%E5%91%BD%E4%BB%A4)

> 使用NPM下载和发布代码时都会接触到版本号。NPM使用语义版本号来管理代码，这里简单介绍一下。
>
> 语义版本号分为X.Y.Z三位，分别代表主版本号、次版本号和补丁版本号。当代码变更时，版本号按以下原则更新。
>
> - 如果只是修复bug，需要更新Z位。
>- 如果是新增了功能，但是向下兼容，需要更新Y位。
> - 如果有大变动，向下不兼容，需要更新X位。
> 
> 版本号有了这个保证后，在申明第三方包依赖时，除了可依赖于一个固定版本号外，还可依赖于某个范围的版本号。例如"argv": "0.0.x"表示依赖于0.0.x系列的最新版argv。
>
> NPM支持的所有版本号范围指定方式可以查看[官方文档](https://npmjs.org/doc/files/package.json.html#dependencies)。

# extraneous

[Source](https://sebhastian.com/npm-err-extraneous/)

> The npm error `extraneous` means that there are installed packages in your `node_modules/` folder that is not listed on your `package.json` file.
>
> The `npm list` command looks into your `package.json` file and the `node_modules/` folder to list the packages installed there.
>
> When a package is not listed in the `package.json` file, it will be marked as `extraneous`.
>
> In npm version 4 and below, you need to add the `--save` option when running `npm install` to save it in the `package.json` file. This is why it’s common to see a package marked as `extraneous` in the past.
>
> Since npm version 5, the `npm install` command will automatically list the package in the `package.json` file without adding the `--save` option.
>
> To resolve `extraneous` errors in the `npm list` output, you need to add the packages in your `package.json` file.
>
> You need to make sure that you’re using the latest version of `npm` first:
>
> ```sh
> npm install -g npm@latest
> ```
>
> Once the upgrade is done, run the `npm list` command again to see if the `extraneous` error is still there.
>
> If you see the error, remove all packages installed in your `node_modules/` folder:
>
> ```sh
> rm -rf node_modules
> ```
>
> Then run the `npm install` command to install the dependencies again.