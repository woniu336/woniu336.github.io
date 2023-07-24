# 66谷歌云第三方 SSH 工具登录与一键重装系统


<!--more-->

## 一，设置 root 密码


1. 先选择从浏览器打开 ssh 连接服务器
2. 切换到 root 账号，输入代码：`sudo -i`
3. 设置 root 密码，输入代码：`passwd`

## 二，开启 SSH 权限

 1. CentOS 和 Debian 通用，输入以下两条命令

```shell
sed -i 's/PermitRootLogin no/PermitRootLogin yes/g' /etc/ssh/sshd_config

sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
```

2. Ubuntu 系统，输入以下两条命令

```shell
sed -i 's/ #PermitRootLogin prohibit-password/PermitRootLogin yes/g' /etc/ssh/sshd_config 

sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
```


 3. 重启服务器 ：
```
reboot
```

以上就是谷歌云设置 ROOT 用户以及允许第三方 SSH 登录教程。


## 三，一键重装脚本


**系统更新**

```shell
apt update -y && apt install -y wget sudo
```


**一键脚本** （ubuntu 20.04）时间半个小时吧，耐心等待就行

```shell
bash <(wget --no-check-certificate -qO- 'https://raw.githubusercontent.com/MoeClub/Note/master/InstallNET.sh') --ip-addr 10.146.0.3 --ip-gate 10.146.0.1 --ip-mask 255.255.255.0 -u 20.04 -v 64 -p 123456 -port 22
```
> **仅适用于谷歌云 (密码：123456 ) SSH 端口: 22**

> 参数修改

- **10.146.0.3** 谷歌云 VPS 内网 IP 谷歌云后台去找
- **10.146.0.1** 谷歌云 VPS 内网 IP 的网关前三位数和 IP 相同第四位数为 1

> 系统参数

**-d 10** 【7、8、9、10，11】Debian

**-u 20.04** 【14.04、16.04、18.04、20.04】Ubuntu



## 四，**系统更新**


```
apt update -y && apt full-upgrade -y && apt install -y curl wget sudo socat
```

---

> 作者: [阿甘](https://github.com/woniu336)  
> URL: https://99bilibili.eu.org/posts/001/  

