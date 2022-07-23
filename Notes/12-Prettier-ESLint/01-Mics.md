# Why EsLint

can do:

- finds errors
- enforces rules
- Fixes errors

Similar to JSLint, JSHint, but the two tools is predefined.EsLint can be customized by your own rules

Agenda

1. installing ESLint CLI
2. Exploring ESLint CLI
3. Run ESLint Against Your Project
   - set up ruleset
   - Resolve errors
4. NPM Script & Git Hooks

> ESlint 被设计为完全可配置的，这意味着你可以关闭每一个规则而只运行基本语法验证，或混合和匹配 ESLint 默认绑定的规则和你的自定义规则，以让 ESLint 更适合你的项目。有两种主要的方式来配置 ESLint：
>
> 1. **Configuration Comments** - 使用 JavaScript 注释把配置信息直接嵌入到一个代码源文件中。
> 2. **Configuration Files** - 使用 JavaScript、JSON 或者 YAML 文件为整个目录（处理你的主目录）和它的子目录指定配置信息。可以配置一个独立的 [`.eslintrc.*`](https://cn.eslint.org/docs/user-guide/configuring#configuration-file-formats) 文件，或者直接在 [`package.json`](https://docs.npmjs.com/files/package.json) 文件里的 `eslintConfig` 字段指定配置，ESLint 会查找和自动读取它们，再者，你可以在[命令行](https://cn.eslint.org/docs/user-guide/command-line-interface)运行时指定一个任意的配置文件。
>
> 如果你在你的主目录（通常 `~/`）有一个配置文件，ESLint 只有在无法找到其他配置文件时才使用它。
>
> 有很多信息可以配置：
>
> - **Environments** - 指定脚本的运行环境。每种环境都有一组特定的预定义全局变量。
> - **Globals** - 脚本在执行期间访问的额外的全局变量。
> - **Rules** - 启用的规则及其各自的错误级别。
>
> 所有这些选项让你可以细粒度地控制 ESLint 如何对待你的代码。

# 不能在～/目录下建立`.eslintrc.*`文件

> **Runtime deprecation warnings for `~/.eslintrc.*` config files**
>
> Personal config files have been deprecated since [v6.7.0](https://eslint.org/blog/2019/11/eslint-v6.7.0-released). ESLint v7.0.0 will start printing runtime deprecation warnings. It will print a warning for the following situations:
>
> 1. When a project does not have a configuration file present and ESLint loads configuration from `~/.eslintrc.*`.
> 2. When a project has a configuration file and ESLint ignored a `~/.eslintrc.*` configuration file. This occurs when the `$HOME` directory is an ancestor directory of the project and the project’s configuration files doesn’t contain `root:true`.
>
> **To address:** Remove `~/.eslintrc.*` configuration files and add a `.eslintrc.*` configuration file to your project. Alternatively, use the `--config` option to use shared config files.
>
> **Related issue(s):** [RFC32](https://github.com/eslint/rfcs/tree/master/designs/2019-deprecating-personal-config/README.md), [#12678](https://github.com/eslint/eslint/pull/12678)

# eslint 执行目录或者文件

```shell
# Run on two files
npx eslint file1.js file2.js

# Run on multiple files
npx eslint lib/**
```