# iPhone备份到移动硬盘

Mac电脑本来硬盘就小，如果再备份iPhone中的内容进去，那就容不下了。但还是有办法的，将iPhone备份到移动硬盘就成了<sup>[1]</sup>。

1. 默认的备份路径为/Library/Application Support/MobileSync/Backup，找到并删除backup文件夹。
2. 在需要备份的外置硬盘根目录新建MobileSync文件夹，然后在MobileSync文件夹里新建Backup文件夹。
3. 打开终端，输入以下命令：`shellln -s /Volumes/外置硬盘名称/MobileSync/Backup ~/Library/Application\ Support/MobileSync/Backup`，因为我的硬盘名是`backup`，于是命令就是：

   ```shell
   ln -s /Volumes/backup/MobileSync/Backup ~/Library/Application\ Support/MobileSync/Backup
   ```

   执行命令后，可以看到，在目录`~/Library/Application Support/MobileSync/`下，生成一个文件夹快捷方式`Backup`，指向`/Volumes/backup/MobileSync/Backup`.
4. 然后就可以插入iPhone进行备份了，点击`Back Up Now`，马上就可以看到`/Volumes/backup/MobileSync/Backup`下生成了备份文件，开始执行备份动作了。

参考及引用：

[1] MAC下修改iTunes备份文件路径 <https://www.feng.com/post/11063540>
