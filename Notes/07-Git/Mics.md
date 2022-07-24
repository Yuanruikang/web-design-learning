# .gitignore添加文件或目录后不生效

如果需要被忽略的文件或者文件夹文件已经被`add`或者`commit`过，`.gitignore`的规则无效因为`.gitignore`只能作用于未被跟踪的文件（untracked file）。

解决办法🪴：

```
# 去掉git在本地的存储
git rm -r --cached <file_name>

# 然后重新提交，此时会启用.gitignore的规则
git add <file_name>

# 再次commit
git commit -m 'message'
```



