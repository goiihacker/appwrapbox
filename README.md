# AppWrap：Claude Desktop 多账号环境管理

AppWrap 是一款 Windows 应用环境管理工具，支持在同一台电脑上为 Claude Desktop 建立多个独立环境。**每个环境使用自己的应用数据目录和登录状态**：为不同账号分别创建环境、分别登录，就可以同时保持登录并并行使用，不必在同一个窗口反复退出和切换账号。

- **Claude Desktop 兼容**：在 AppWrap 中选择已安装的 Claude Desktop，以「普通 Windows 程序」模式运行。
- **多账号独立运行**：把不同账号放到不同环境，在环境列表中分别打开或关闭。
- **独立保存登录数据**：各环境分别保存应用数据。固定使用自己的环境和账号，减少误登、误切换，便于稳定使用。
- **按环境设置代理**：可为不同环境分别配置 SOCKS5；0.5.68 改善了 Claude 自带浏览器在 SOCKS5 环境下打开网页的兼容性。

## 网络与隐私保护

每个环境独立管理网络代理、语言、地区和时区。以下是 **v0.5.68** 中的具体保护，开启后仅对相应的 AppWrap 环境生效，不修改 Windows 的全局设置。

- **IPv4 出口**：配置 SOCKS5 后，Claude Desktop 在受管路径上的 IPv4 TCP 连接经该环境的代理转发。设置中可以查看探测到的出口 IP。
- **IPv6**：应用环境默认开启「限制 IPv6」，阻止受管的 IPv6 连接，并从支持的网络查询中排除宿主的 IPv6 地址和路由；宿主的 IPv6 不受影响。
- **WebRTC**：AppWrap 内置 Chromium 禁用 QUIC，并限制 WebRTC 使用未经过代理的 UDP，降低直接联网暴露宿主网络地址的风险。Claude 自带的浏览器面板是独立组件，不等同于 AppWrap 内置 Chromium。
- **DNS**：Claude Desktop 在「普通 Windows 程序」模式下启用 SOCKS5 时，受管的 IPv4 域名查询经代理发出。解析服务器不可达时会尝试备用服务器；解析失败不回退到 Windows 的 DNS。「覆盖网卡 DNS」是独立开关，用来控制应用查询网卡配置时看到的 DNS 地址。
- **语言、区域和时区**：界面语言、区域格式和国家/地区可按出口 IP 自动设置，也可手动填写或沿用 Windows 设置；时区单独配置。支持的应用查询返回环境配置，不改变宿主输入法。
- **字体列表**：独立开关默认开启。部分普通 Windows 应用枚举字体时，不显示选定的简体中文补充字体，例如宋体、楷体、仿宋、等线和黑体。字体不卸载，仍可用于中文显示和文档排版；这项设置不应用于 AppWrap 内置 Chromium。
- **本地网络信息**：可限制环境内的 Wi-Fi／BSSID 查询，并在支持的查询中减少指定虚拟网卡的信息暴露，不关闭宿主的网卡或网络服务。

这些保护的范围取决于启动模式和环境设置；Windows 系统流量和 AppWrap 未管理的进程不在此范围内。

## 下载与安装

1. 打开 [GitHub Releases](https://github.com/goiihacker/appwrapbox/releases)，在 **Assets** 下下载 [AppWrap-Setup-0.5.68.exe](https://github.com/goiihacker/appwrapbox/releases/download/v0.5.68/AppWrap-Setup-0.5.68.exe)。也可从 [AppWrap 官网](https://www.appwrapbox.com/Download) 下载。
2. 在 64 位 Windows 上运行安装包，完成安装后打开 AppWrap。如果还没有安装 Claude Desktop，请先安装它。
3. 在 AppWrap 里点击「新建环境」，为第一个账号起名，选择已安装的 Claude Desktop 程序（不要选安装文件），启动类型选择「普通 Windows 程序」。需要代理时再填写该环境的 SOCKS5 设置。
4. 启动环境并登录第一个账号。为其他账号重复创建环境、启动和登录；各窗口可以同时运行。请不要让不同环境共用同一个应用数据目录。

## 7 天免费试用

试用从本机首次运行 AppWrap 开始计算，无需购买即可体验。试用到期且未激活授权时，AppWrap 每隔 15 分钟会自动关闭正在运行的环境和内置浏览器；可在软件的「购买」页面查看授权选项。

试用的是 AppWrap，不包含 Claude 账号或订阅。AppWrap 独立于 Anthropic；请按 Claude 的使用条款使用你的账号。如平台要求身份验证，请按官方指引完成。

## 售后支持

**AppWrap 官方售后 QQ 群：`187471475`**

安装、环境配置、试用、授权和故障反馈，都可以在群里咨询。用手机 QQ 扫描下方二维码，或搜索群号加入。

<img src="https://github.com/user-attachments/assets/998e093e-79dc-4397-9eca-e7b3a0b2fed2" width="320" alt="AppWrap 官方售后 QQ 群二维码，群号 187471475" />

---

本仓库仅用于提供安装包和使用说明，不公开 AppWrap 源码。
