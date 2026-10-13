<h1 align="center">

ReviOS Playbook 修改自用版

---

<img src="images/github-banner.png" alt="image" width="900">

</h1>

> [!CAUTION]
> 本项目是基于 ReviOS Playbook 修改的个人自用版本，并非官方发行版，目前尚未经过完整测试，不保证适用于所有 Windows 10/11 版本、硬件或使用环境。配置方案会修改系统组件、注册表、服务及安全设置，可能造成数据丢失、功能异常、系统无法启动或需要重装 Windows。
>
> 使用前请务必备份重要数据，并建议创建完整系统镜像、恢复介质或其他可靠的回滚方案。优先在虚拟机、测试设备或全新安装的系统中验证。继续使用即表示你已了解相关风险，所有后果由使用者自行承担。

> [!NOTE]
> 已测试环境仅限虚拟机（VM）：Microsoft Windows 11 专业版 25H2，操作系统版本 `26200.6584`，测试通过。其他 Windows 版本、系统版本号及实体机环境尚未验证。

<div align="center">

[![Releases](https://img.shields.io/github/v/release/meetrevision/playbook.svg?label=Release)](https://github.com/meetrevision/playbook/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/meetrevision/playbook/total?label=Total%20downloads)](https://github.com/meetrevision/playbook/releases)

</div>

ReviOS 是一个精简化的 Windows 定制版本，注重轻量、稳定，并改善性能、隐私与兼容性。本仓库是其配置方案（playbook）的个人修改版，配合 [AME Wizard](https://amelabs.net) 使用。

### 当前计划

- [x] 界面中文化
- [x] 移除 OEM 信息
- [x] 移除 ReviOS 个性化内容
- [ ] 禁用联网环节（包括安装浏览器）——待定

## ✨ 主要特性

- 🎯 使用简单，把配置方案拖进 [AME Wizard](https://amelabs.net) 即可
- 🗑 移除预装软件与不必要的系统组件
- ⚡ 优化性能与隐私设置
- 🔧 集成 [Revision Tool](https://github.com/meetrevision/revision-tool) 以便进一步定制系统

## 💻 系统要求

配置方案支持以下 Windows 版本的 ARM64 和 AMD64 版本：

- Windows 10 21H2 `19044`（含 LTSC）
- Windows 10 22H2 `19045`
- Windows 11 23H2 `22631`
- Windows 11 24H2 `26100`（含 LTSC）
- Windows 11 25H2 `26200`
- Windows 11 26H1 `28000`
- Windows 11 26H2 `26300`

其他版本号未经验证，可能无法正常工作。

⚠️ ISO 注入功能仅支持 Windows 11 的 ISO。

## 🚀 使用步骤

1. 下载 [AME Wizard](https://amelabs.net) 和本仓库的配置方案。
2. 启动 AME Wizard，把配置方案拖入界面。
3. 按屏幕提示完成安装。

> [!CAUTION]
> 建议在全新、未改动的 Windows 上执行本配置方案，避免与已装软件和用户数据产生冲突。

## 📝 License

[![License](https://img.shields.io/static/v1?label=LICENSE&message=CC%20BY-SA&logo=creativecommons)](https://creativecommons.org/licenses/by-sa/4.0/)

ReviOS Playbook is licensed under [Attribution-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/).
ReviOS Playbook 采用 [Attribution-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/) 许可协议。
