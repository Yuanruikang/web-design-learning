# install

```bash
brew install vnm
```

```bash
# 执行
mkdir ～/.nvm
vim ~/.zshrc

#写入
export NVM_DIR="$HOME/.nvm"
[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"  # This loads nvm
[ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm"  # This loads nvm bash_completion
```

# 其他问题

- 如果在macOS上先通过`brew install node`安装了node，为了不相互冲突，需要先卸载掉brew上的node。 
  - 安装具体参考：https://www.runoob.com/w3cnote/nvm-manager-node-versions.html
  - 以及https://github.com/nvm-sh/nvm/issues/1184

* 在使用powerlevel10k时，通过nvm管理node版本，提示行不显示默认的node版本：https://github.com/romkatv/powerlevel10k/issues/373