# AppWrap：Claude Desktop 多账号环境管理

AppWrap 是一款 Windows 应用环境管理工具，支持在同一台电脑上为 Claude Desktop 建立多个独立环境。**每个环境使用自己的应用数据目录和登录状态**：为不同账号分别创建环境、分别登录，就可以同时保持登录并并行使用，不必在同一个窗口反复退出和切换账号。

- **Claude Desktop 兼容**：在 AppWrap 中选择已安装的 Claude Desktop，以「普通 Windows 程序」模式运行。
- **多账号独立运行**：把不同账号放到不同环境，在环境列表中分别打开或关闭。
- **独立保存登录数据**：各环境分别保存应用数据。固定使用自己的环境和账号，减少误登、误切换，便于稳定使用。
- **按环境设置代理**：可为不同环境分别配置 SOCKS5；0.5.68 改善了 Claude 自带浏览器在 SOCKS5 环境下打开网页的兼容性。

## 下载与安装

1. 打开 [GitHub Releases](https://github.com/goiihacker/appwrapbox/releases)，在 **Assets** 下下载 `AppWrap-Setup-0.5.68.exe`。也可从 [AppWrap 官网](https://www.appwrapbox.com/Download) 下载。
2. 在 64 位 Windows 上运行安装包，完成安装后打开 AppWrap。如果还没有安装 Claude Desktop，请先安装它。
3. 在 AppWrap 里点击「新建环境」，为第一个账号起名，选择已安装的 Claude Desktop 程序（不要选安装文件），启动类型选择「普通 Windows 程序」。需要代理时再填写该环境的 SOCKS5 设置。
4. 启动环境并登录第一个账号。为其他账号重复创建环境、启动和登录；各窗口可以同时运行。请不要让不同环境共用同一个应用数据目录。

## 7 天免费试用

试用从本机首次运行 AppWrap 开始计算，无需购买即可体验。试用到期且未激活授权时，AppWrap 每隔 15 分钟会自动关闭正在运行的环境和内置浏览器；可在软件的「购买」页面查看授权选项。

试用的是 AppWrap，不包含 Claude 账号或订阅。AppWrap 独立于 Anthropic；请按 Claude 的使用条款使用你的账号。如平台要求身份验证，请按官方指引完成。

---

本仓库仅用于提供安装包和使用说明，不公开 AppWrap 源码。
