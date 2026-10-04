# 云小鹤运行时下载 / YunXiaoHe runtime downloads

[中文](#中文) · [English](#english) · [官网下载与安装 / Get started](https://yh-intel.cn/releases/#data-governance)

## 从这里开始 / Start here

| 你要找的内容 / What you need | 入口 / Location |
| --- | --- |
| 新对话安装指令、账号登录、手动下载 / Copy-paste instructions, sign-in and manual downloads | [中英文安装指南 / Installation guide](docs/install.md) |
| Windows / Linux 数据运行时 / Data runtimes | [GitHub Release](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/tag/yunxiaohe-local-20261003-r7) |
| 通用、数据治理、供应链 Skill / General, data and supply-chain Skills | [官网产品入口 / Product selector](https://yh-intel.cn/releases/) |
| r7 版本范围 / What r7 includes | [版本说明 / Release notes](release-notes.md) |
| 文件校验 / Verify downloads | [SHA256SUMS.txt](SHA256SUMS.txt) |

当前安装器 / Current installer: **CLI 1.4.1** · 数据运行时 / Data runtime: **20261003-r7**。
已安装 Skill 的用户请先更新 Skill，才能使用新的 GitHub 下载、进度显示和断点续传。
Update an existing Skill first to get GitHub downloads, progress reporting and resume support.

仓库只存放客户文档和校验文件；安装包在 Releases 附件中。私有源码、账号数据和测试记录不在这里。
This repository holds customer documentation and checksums; binaries are Release assets. It does not contain private source, account data or internal test records.

## 中文

这里提供云小鹤数据治理 Agent 的本地运行时，供 Codex、DSH 和其他智能体使用。安装包可以直接下载，不需要 GitHub 账号；处理数据和运行模型仍需要有效且具有相应产品权限的 **YH 账号**。

| 平台 | 下载 | 环境要求 |
| --- | --- | --- |
| Windows x64 | [ZIP 安装包](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/download/yunxiaohe-local-20261003-r7/YunXiaoHe-Local-Runtime-windows-x64-20261003-r7.zip) | x64 Windows，未签名便携运行时 |
| Linux x86_64 | [tar.gz 安装包](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/download/yunxiaohe-local-20261003-r7/YunXiaoHe-Local-Runtime-linux-x64-20261003-r7.tar.gz) | Ubuntu 24.04 或兼容 glibc 2.39+ 的系统 |

可以按照[数据治理 Skill 指南](https://yh-intel.cn/releases/yunxiaohe-local/client/docs/data-skill.md)安装独立数据 Skill，或按本仓库的[安装指南](docs/install.md)安装通用云小鹤 Skill。CLI 1.4.1 会选择对应的运行时，优先从 GitHub 下载，显示进度并检查文件摘要。GitHub 连接失败时会改用官网下载，YH key 不会发给 GitHub。已经更新 Skill 的用户可在其目录中运行：

```sh
python scripts/yxh.py login
python scripts/yxh.py runtime install
python scripts/yxh.py runtime doctor
```

Windows 可用 `py -3`，Linux 可用 `python3`。YH key 在终端的隐藏提示中输入，不要发到聊天里。模型与模型服务商 key 继续由你的 Codex、DSH 或其他 Harness 管理；数据计算在本机执行。

手动下载时，请使用本仓库的 [SHA256SUMS.txt](SHA256SUMS.txt) 校验文件，解压后运行 `yxh-runtime.exe login`（Windows）或 `./yxh-runtime login`（Linux）。`doctor` 可以在登录前检查组件；数据处理与模型复用会先检查账号权限。

当前运行时版本为 `20261003-r7`。这是数据治理运行时，不是桌面 GUI 或供应链安装包。供应链产品请从[官网](https://yh-intel.cn/releases/#supply-chain)选择对应入口。

安装包使用其中附带的 YH 客户许可，第三方组件保留各自许可。公开下载不改变使用时的账号要求，也不授予单独分发 RISA SDK 的许可。

## English

Download the local runtime for **YunXiaoHe - Data Governance Agent**, used by Codex, DSH and other agent harnesses. Downloads are public and do not require a GitHub account. Data operations and model reuse require an active **YH account with product access**.

The table above links to Windows x64 and Linux x86_64 packages. Linux requires Ubuntu 24.04 or compatible glibc 2.39+. Windows ships as an unsigned portable archive.

Choose the independent [Data Governance Skill](https://yh-intel.cn/releases/yunxiaohe-local/client/docs/data-skill.md#english) or follow this repository's [installation guide](docs/install.md) for the general YunXiaoHe Skill. After updating the Skill, run the three commands above from its directory. CLI 1.4.1 selects the runtime, downloads from GitHub first with official-site fallback, and verifies its checksum. Your YH key is never sent to GitHub. Your harness keeps its model-provider key and makes model calls directly; computation runs on your computer.

For manual downloads, verify [SHA256SUMS.txt](SHA256SUMS.txt), extract the archive and run `yxh-runtime.exe login` on Windows or `./yxh-runtime login` on Linux. Read-only `doctor` works without signing in; data operations and model reuse check your YH account first.

Runtime `20261003-r7` is the data component, not a desktop GUI or supply-chain package. See the [official product page](https://yh-intel.cn/en/releases/) for the other options.

The bundled YH customer license and third-party licenses continue to apply. Public availability does not remove account requirements or grant permission to redistribute the standalone RISA SDK.

YH Intelligence Technology, Co., Ltd. · [bot@yh-intel.com](mailto:bot@yh-intel.com)
