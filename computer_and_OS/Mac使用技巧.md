# Mac 使用技巧

## 手机备份到移动硬盘

正常情况下，iPhone在Mac中是备份到电脑硬盘而不是移动硬盘的，路径`~/Library/Application Support/MobileSync/Backup`；

如果要将手机备份到外部移动硬盘，只需要将这个路径链接到外部硬盘即可（路径自己命名），命令如下：

```shell
ln -s /Volumes/backup/MobileSync/Backup ~/Library/Application\ Support/MobileSync/Backup
```
