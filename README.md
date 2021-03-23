# 路由器软件中心重置/删除方法（解决一直显示正在更新…）

### 路由器打开 SSH
系统管理 > 系统设置 > 服务，打开 SSH 选择「LAN only」，点选「应用本页设置」。

![2021-03-24-04.27.05.@2x](https://tvax1.sinaimg.cn/large/008eZBHKly1gouhxq2byhj316213wdgr.jpg)

---

### macOS 连接 SSH

1. 打开终端输入 `sudo -i` 按回车键

2. 输入 Mac 管理员密码（不显示任何字符）。

3. 输入 `ssh root@192.168.50.1` 按回车键。

   > 示例：华硕路由器登录地址是 `192.168.50.1`，登录名是 `admin`，则输入 `ssh admin@192.168.50.1`

4. 输入 `yes` 按回车键。

5. 输入路由器登录密码，按回车键。

![](https://tvax1.sinaimg.cn/large/008eZBHKly1goui5d2hl0j310c0f6403.jpg)

---

### Windows 连接 SSH

1. 安装 [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) 软件，打开输入 `192.168.50.1`，点击「open」。

![03winssh1](https://tva2.sinaimg.cn/large/008eZBHKly1gouil010c8j30yg0lvgok.jpg)

2. 输入路由器用户名，按回车键。

   > 示例：路由器登录用户名是 `admin`，则输入`admin`

3. 输入路由器密码（不显示任何字符），按回车键。

![04winssh2](https://tva1.sinaimg.cn/large/008eZBHKly1gouilav0rhj30yg0k2gms.jpg)

---

### 插件提示非法关键词

开启路由器的 SSH 功能，登录并输入以下命令后，再进行离线安装。

```
sed -i 's/\tdetect_package/\t# detect_package/g' /koolshare/scripts/ks_tar_install.sh
```

---

### 重置软件中心

**官改/梅林**：在 SSH 客户端运行 `koolshare-reset` 命令。

**梅林方法二**：

1. 【系统管理 】–【系统设置】内勾选：`Format JFFS partition at next boot` 和 `Enable JFFS custom scripts and configs`，点击「应用本页面设置」，然后重启路由器。

2. 重启路由后，然后将路由器连上网络，进入软件中心将更新到最新。