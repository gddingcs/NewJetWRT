# JetWRT

使用GitHub Actions编译的OpenWRT for NanoPi R2S

![Build R2S JetWRT](https://github.com/KaneGreen/NewJetWRT/workflows/Build%20R2S%20JetWRT/badge.svg?branch=JetWRT&event=push)

本项目采用的源码: 
* https://github.com/fanck0605/friendlywrt-lean
* https://github.com/fanck0605/kernel-rockchip

### NanoPi R2S说明
1. 采用[fanck0605](https://github.com/fanck0605/nanopi-r2s)的方式编译R2S固件。
2. 默认管理地址：`192.168.2.1`；用户名：`root`；密码：`password`。
3. 支持Aria2、diskman、Docker、frpc/frps、samba、ssr-plus、ttyd、WireGuard、ZeroTier等。
4. 去掉全部广告拦截、网易云音乐解锁、transmission、多拨。
5. 添加了SFTP支持，可以使用SFTP协议传输文件。
6. 包含3个主题：argon、bootstrap、material。
7. 其他系统工具：htop、iperf3、nano、python3、screen、stress、zstd等。

## 特色
* 完美的 Flow Offload 支持，不与 PPPoE 冲突，降低 CPU 负载
* 使用 [Lean's OpenWrt]，并 merge 了 [FriendlyWrt]
    - 包含大部分 [Lean's OpenWrt] 的特性（网络相关的内核功能已经正常啦！）
    - 可以支持 [FriendlyWrt] 所支持的机型
* 开启了 [Full Cone NAT](https://github.com/Chion82/netfilter-full-cone-nat)，对游戏用户支持更佳
* 支持 IPv6，可以访问最新 IPv6 规范的互联网。
    - 需要关闭 *网络* -> *DHCP/DNS* -> *高级设置* -> *禁止解析 IPv6 DNS 记录*
* 默认 WAN 和 LAN 互换，LAN 口是原生千兆网卡，更加稳定

## 用法
1. Fork 到自己的账号下
2. 进入 Actions 界面，启用 Github Actions
3. 在 `more_packages` 文件中，自定义所需要的软件包
    - 比如需要 `luci-app-uhttpd`， 那么只要在文件中添加一行 `CONFIG_PACKAGE_luci-app-uhttpd=y`

## 注意
1. 产品发布初期，官方代码每天都在变，遇到无法编译时，请过来查看 `.yml` 与 `config` 最新异动。
2. `cifsd` 与 `samba` 有冲突，只能二选一。(`cifsd` 暂时无法工作，可能是永久的)
3. 本版本现在采用的是`samba36`。

## 特别感谢
（排名不分先后）
* [fanck0605](https://github.com/fanck0605/nanopi-r2s)
* [klever1988](https://github.com/klever1988/nanopi-openwrt)
* [ardanzhu](https://github.com/ardanzhu/Opwrt_Actions)
* [soffchen](https://github.com/soffchen/NanoPi-R2S)
* [Lean](https://github.com/coolsnowwolf/lede)
* [Chion82](https://github.com/Chion82/netfilter-full-cone-nat)
* [FriendlyWrt]

## 参考
* [使用Github的Actions功能在线编译NanoPi-R1S固件（包含H5和H3）](https://totoro.site/index.php/archives/70/)
* [skytotwo/NanoPi-R1S-Build-By-Actions](https://github.com/skytotwo/NanoPi-R1S-Build-By-Actions)
* [yangliu/NanoPi-R2S](https://github.com/yangliu/NanoPi-R2S)
* [maxming2333/NanoPi-R2S](https://github.com/maxming2333/NanoPi-R2S)

### License
[GPL-3.0](./LICENSE)

[Lean's OpenWrt]: https://github.com/coolsnowwolf/lede
[FriendlyWrt]: https://github.com/friendlyarm/friendlywrt
