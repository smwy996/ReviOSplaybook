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

[![Releases](https://img.shields.io/github/v/release/smwy996/ReviOSplaybook.svg?label=Release)](https://github.com/smwy996/ReviOSplaybook/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/smwy996/ReviOSplaybook/total?label=Total%20downloads)](https://github.com/smwy996/ReviOSplaybook/releases)

</div>

ReviOS 是一个精简化的 Windows 定制版本，注重轻量、稳定，并改善性能、隐私与兼容性。本仓库是其配置方案（playbook）的个人修改版，配合 [AME Wizard](https://amelabs.net) 使用。

### 当前计划

- [x] 界面中文化
- [x] 移除 OEM 信息
- [x] 移除 ReviOS 个性化内容
- [x] 禁用联网环节（包括安装浏览器）

## ✨ 主要特性

- 🎯 使用简单，把配置方案拖进 [AME Wizard](https://amelabs.net) 即可
- 🗑 移除预装软件与不必要的系统组件
- ⚡ 优化性能与隐私设置
- 🔧 使用 [Revision Tool](https://github.com/meetrevision/revision-tool) 进一步定制系统
- 📴 执行过程不联网：不下载外部资源，不调用在线包管理器

## 📴 离线说明

配置方案执行期间不会主动联网，也不会下载任何文件。以下三项因此需要**提前手动准备**：

| 项目 | 说明 |
|---|---|
| Revision Tool | **必做**。需手动放入剧本同目录，否则配置方案会中止（详见下一节） |
| Visual C++ 运行库 | 已跳过安装。如系统缺少，请自行提前安装 |
| 浏览器 | 已跳过安装。请自行下载安装包，在配置方案之外安装 |

`playbook.conf` 中已移除强制联网要求，因此在完全断网的机器上也能执行。

## 🧰 准备 Revision Tool（必做）

配置方案需要 [Revision Tool](https://github.com/meetrevision/revision-tool) 来执行系统组件移除、Defender 切换等操作。自用版不联网下载，需手动放到指定位置。

**步骤：**

1. 在本仓库的 [Releases](../../releases) 页面下载 `RevisionTool-Setup.exe` 附件。
2. 把该文件放在**配置方案所在目录**，即与 `playbook.conf` 同级。
3. 再把它拖入 AME Wizard 执行。

要求目录结构如下（`RevisionTool-Setup.exe` 必须与 `playbook.conf` 同级）：

```
你的工作目录/
├── playbook.conf
├── RevisionTool-Setup.exe      ← 放在这里
└── ...
```

> [!IMPORTANT]
> 如果 `RevisionTool-Setup.exe` 缺失或放错位置，配置方案会在「安装 Revision 工具」这一步中止。这是有意设计的——缺少它会导致后续大量操作静默失效，直接中止比留下半成品系统更安全。

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
2. 按上一节说明，把 `RevisionTool-Setup.exe` 放到配置方案同目录。
3. 启动 AME Wizard，把配置方案拖入界面。
4. 按屏幕提示完成安装。

> [!CAUTION]
> 建议在全新、未改动的 Windows 上执行本配置方案，避免与已装软件和用户数据产生冲突。

## ❓ 常见问题

**配置方案提示找不到 Revision Tool？**

确认 `RevisionTool-Setup.exe` 与 `playbook.conf` 在同一目录，文件名完全一致（区分大小写）。注意它应该放在**配置方案所在目录**，不是解压出来的子目录。

**想用浏览器 / 需要 VCRedist？**

这两项已从配置方案中移除联网下载，需要自行安装。安装时机随意，在配置方案执行前后都可以，不影响其余优化生效。

**执行过程中会联网吗？**

不会。配置方案不包含下载操作，也已移除强制联网要求。但 AME Wizard 自身、以及 Windows 的后续联网行为不受本仓库控制。

## 📝 License

[![License](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

ReviOS Playbook 采用 [Attribution-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/) 许可协议。
