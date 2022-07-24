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