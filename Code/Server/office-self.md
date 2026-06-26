# Office-self (10.1.15.9)

## 为什么要用 paramiko

本机（Windows + winget）装不了 sshpass。统一用 Python paramiko 登录。

## 登录代码


## 工作流约定

- **只查看**：直接 `exec_command + cat`
- **要修改**：先 SFTP 下载到本地临时目录，本地编辑，再 SFTP 上传回去。**禁止在远程 shell 里用 sed/cat 直接改文件**。
