#Linux系统笔记

##Linux系统核心目录结构
- `/bin`:存放最常用的基础命令（如ls，cp，mkdir等）
- `/etc`:存放系统的配置文件。
- `/home`:用户家目录
- `/root`:管理员的家目录
- `/var`:存放变化的文件，如：日志文件。

##Linux系统终端常用指令

上下键可以翻阅历史命令

- `sudo`:临时获取最高权限，安装软件，改系统文件
sudo apt类
sudo apt install 软件名（安装软件）
sudo apt remove 软件名（卸载软件）

###一、查看类

####1.关于系统
- `pwd`:直接查看当前位置
- `stat -f`:查看本机块大小
- `df -h`:查看磁盘剩余空间
- `tree`:以树形展示文件夹结构
- `htop`:查看电脑进程
- `top`:查看占用cpu内存
按q退出（可用于排查机器人程序卡死，cpu占用过高，后台进程排查必备）

- `whoami`:查看当前登录用户名
kang@kang:~/rm_preview$ whoami
kang

- `uname -a`:查看当前系统内核版本
kang@kang:~/rm_preview$ uname -a
Linux kang 7.0.0-38-generic #38-Ubuntu SMP PREEMPT_DYNAMIC Fri Sep  4 09:10:14 UTC 2026 x86_64 GNU/Linux


####2.查看文件
- `cat`:一次性查看整个文件,将整个文件打在终端上(要加文件名，不加会读取并打印你的输入）
（Ctrl+D结束输入）（Ctrl+c强制终止）

- `bat`——————交互式查看文件，对语法有高亮

- `head/tail`——看开头、看结尾
tail ~ n 10 ~/.bash_history>>"要写入的文件"读取最后十行写入

- `less`:分页查看文件内容（适合长文件，按`q`退出）。

- `grep`:在文本中搜索特定字符串（如`grep"error" log.txt`）。

- `wc`：统计文件的字数和行数（`wc -w`统计单词数，`wc -l`统计行数，`wc -m`多适用于字符，汉字）

- `ls`———————查看当前文件夹里的文件
- `ls -l`————查看详细信息（权限、大小、修改时间)
- `ls -al`———显示所有文件（含隐藏文件。Linux中以.开头的是隐藏文件）
例：
kang@kang:~/rm_preview$ ls -l
total 8（代表所有文件占用的磁盘块总和即总共占用4kb磁盘）
-rw-rw-r-- 1 kang kang    0 Oct 16 12:58 log.txt
drwxrwxr-x 2 kang kang 4096 Oct 16 13:03 test_folder
drwxrwxr-x 2 kang kang 4096 Oct 16 20:02 终端指令

kang@kang:~/rm_preview$ ls -al
total 16
drwxrwxr-x  4 kang kang 4096 Oct 16 13:16 .
drwxr-x--- 17 kang kang 4096 Oct 16 13:15 ..
-rw-rw-r--  1 kang kang    0 Oct 16 12:58 log.txt
drwxrwxr-x  2 kang kang 4096 Oct 16 13:03 test_folder
drwxrwxr-x  2 kang kang 4096 Oct 16 20:02 终端指令


###二、创建类
- `mkdir/mkdir -p`:创建文件夹
kang@kang:~$ mkdir rm_preview（mkdir是创建空文件夹）

- `touch`：创建文件(如:md,txt)
kang@kang:~/rm_preview$ touch log.txt（touch是创建空文件，没办法cd进入）
kang@kang:~/rm_preview$ touch note.md

- `cp`:制作副本
cp 原文件名    副本文件名
kang@kang:~/rm_preview$ cp log.txt log_backup.txt（制作log.txt的副本）

###三、索引类
- `cd`:cd 要去的地方
kang@kang:~$ cd rm_preview（cd是去哪里）
（如cd ~是去家目录，注意～和~的区别。cd ..是退一级）


###四、修改移动类
- `mv`:mv 旧文件名 新文件名或移动到的文件夹
kang@kang:~/rm_preview$ mv note.md readme.md（重命名note.md为read.md)
kang@kang:~/rm_preview$ mv readme.md test_folder（移动到test_folder)


###五、删除类
- `rm`：删除文件
kang@kang:~/rm_preview$ rm iog_backup.txt(删除空文件）
rm后面接多个文件名，会同时删除
rm -i（建议使用）（删除前会询问，避免误删）
rm -I(多个文件才提示，少量不提示）
rm -f(强制删除）

- `rmdir`:删除文件夹
kang@kang:~/rm_preview$ rmdir test_folder(删除空文件夹）

###六、重定向与管道符
- `>`:**覆盖**重定向（把左边的命令的输出，写入到右边的文件中，完全覆盖原文件内容）
- `|`:**管道符**（把左边的命令输出，作为右边命令的输入。如：`ls -l | grep ".md`只显示.md文件)




