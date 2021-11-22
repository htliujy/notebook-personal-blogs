# gitignore的使用技巧

.gitignore是什么文件？

如果要排除git中的文件夹`/foo`，但又要包含其子文件夹`/foo/bar`，应该怎么做<sub>[1]</sub>？

```.gitignore
# exclude everything except directory foo/bar
/*
!/foo
/foo/*
!/foo/bar
```

## 参考及引用

[1] .gitignore排除文件夹，但包括特定的子文件夹. <https://qastack.cn/programming/5533050/gitignore-exclude-folder-but-include-specific-subfolder>
