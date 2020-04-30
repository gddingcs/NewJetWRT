# 此编译版变更日志
### 2020/04/29 beta 5
* 更新[上游](https://github.com/fanck0605/nanopi-r2s/tree/94325fbc5505e8966f373280d3cea2244f968ce4)。

### 2020/04/28 beta 4
* 移除vim-full，保留vim-fuller。

### 2020/04/27 beta 3
构建失败。

### 2020/04/27 beta 2
* 更新[上游](https://github.com/fanck0605/nanopi-r2s/tree/762dec2e8fec14832fe2a91bdab95f31ffb418ad)。

### 2020/04/27 beta 1
已取消。

------

# 上游变更日志
## 20200430(v2.2.0)
- 添加 CPU 信息显示(频率,温度)
- 支持部分 usb 网卡(没设备测试)
- 添加 UnblockNeteaseMusic
- 添加在线 ipk 安装
- 添加 ttyd 在线终端
- 内核更新到 `5.4.36`

## 20200429
- 尝试修复 PPPoE 拨号的问题

## 20200427(v2.1.0)
- 貌似修复了某些情况下 `UDPBlocked` 的问题
- 内核更新到 `5.4.35`

## 20200426(v2.0.1)
- 重新添加 Net Data
- SSH 只监听 lan 口
- 同步上游源码

## 20200426(v2.0.0)
- 支持 Flow Offloading
- 可能修复了 Firewall 崩溃的问题(不是采用脚本监控，是真的不崩溃了)
- 添加 File Browser
- 移除 Net Data(占资源，污染日志)
- 同步上游源码

## 20200413(v1.2.0)
- 默认主题设置为 Argon
- 默认开启 UPnP
- 关闭 *自动挂载未配置的磁盘分区*
- 同步上游源码
