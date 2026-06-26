# Office-self (10.1.15.9)

## 为什么要用 paramiko

本机（Windows + winget）装不了 sshpass。统一用 Python paramiko 登录。

## 登录代码

```python
import paramiko

c = paramiko.SSHClient()
c.set_missing_host_key_policy(paramiko.AutoAddPolicy())
c.connect('10.1.15.9', port=22, username='linzy',
          password='REDACTED', timeout=15)
stdin, stdout, stderr = c.exec_command('uname -a')
print(stdout.read().decode())
```

## SFTP 文件传输（改服务器文件的推荐工作流）

```python
# 下载到本地 → 本地编辑 → 推回原路径
sftp = c.open_sftp()
sftp.get('/remote/path/file', 'D:/local/tmp/file')
sftp.put('D:/local/tmp/file', '/remote/path/file')
sftp.close()
```

## 同机其他账号

| 账号 | 密码 |
|------|------|
| Office-admin (REDACTED) | REDACTED |
| REDACTED (REDACTED) | REDACTED |
| REDACTED (REDACTED) | REDACTED |

完整密码见 `C:\Users\ldm\.ssh\config` 的 `#key` 注释。

## 工作流约定

- **只查看**：直接 `exec_command + cat`
- **要修改**：先 SFTP 下载到本地临时目录，本地编辑，再 SFTP 上传回去。**禁止在远程 shell 里用 sed/cat 直接改文件**。
