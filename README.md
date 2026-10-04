# 云小鹤运行时下载 / YunXiaoHe runtime downloads

[中文](#中文) · [English](#english) · [官网下载与安装 / Get started](https://yh-intel.cn/releases/#data-governance)

## 中文

这里提供云小鹤数据治理 Agent 的本地运行时，供 Codex、DSH 和其他智能体使用。安装包可以直接下载，不需要 GitHub 账号；处理数据和运行模型仍需要有效且具有相应产品权限的 **YH 账号**。

| 平台 | 下载 | 环境要求 |
| --- | --- | --- |
| Windows x64 | [ZIP 安装包](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/download/yunxiaohe-local-20261003-r7/YunXiaoHe-Local-Runtime-windows-x64-20261003-r7.zip) | x64 Windows，未签名便携运行时 |
| Linux x86_64 | [tar.gz 安装包](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/download/yunxiaohe-local-20261003-r7/YunXiaoHe-Local-Runtime-linux-x64-20261003-r7.tar.gz) | Ubuntu 24.04 或兼容 glibc 2.39+ 的系统 |

通常只需按照[官网安装说明](https://yh-intel.cn/releases/yunxiaohe-local/client/docs/data-skill.md)安装数据治理 Skill。安装器会选择对应的运行时，显示进度并检查文件摘要。已经装好 Skill 的用户可在其目录中运行：

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

Start with the [official Skill guide](https://yh-intel.cn/releases/yunxiaohe-local/client/docs/data-skill.md#english), then run the three commands above from the installed Skill directory. The installer selects the runtime and verifies its checksum. Your harness keeps its model-provider key and makes model calls directly; computation runs on your computer.

For manual downloads, verify [SHA256SUMS.txt](SHA256SUMS.txt), extract the archive and run `yxh-runtime.exe login` on Windows or `./yxh-runtime login` on Linux. Read-only `doctor` works without signing in; data operations and model reuse check your YH account first.

Runtime `20261003-r7` is the data component, not a desktop GUI or supply-chain package. See the [official product page](https://yh-intel.cn/en/releases/) for the other options.

The bundled YH customer license and third-party licenses continue to apply. Public availability does not remove account requirements or grant permission to redistribute the standalone RISA SDK.

YH Intelligence Technology, Co., Ltd. · [bot@yh-intel.com](mailto:bot@yh-intel.com)
