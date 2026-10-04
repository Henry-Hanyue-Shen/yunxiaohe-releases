# Skill 与智能体接入 / Skills and agent integration

[中文](#中文) · [English](#english) · [返回下载首页 / Downloads](../README.md)

## 中文

在[官网产品页](https://yh-intel.cn/releases/)选择产品和你使用的智能体，复制安装指令即可。三个 Skill 都可以公开下载；使用云小鹤服务和授权的本地组件时，仍需要自己的 YH 账号。模型调用使用当前 Harness 的模型与凭据，不经过 YH 转发。

### 选择下载包

| 用途 | 下载 |
| --- | --- |
| 通用云小鹤 Agent | [yunxiaohe-client.zip](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/download/yunxiaohe-skills-1.4.1/yunxiaohe-client.zip) |
| 本地表格、特征工程与建模 | [yxh-data-governance-skill.zip](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/download/yunxiaohe-skills-1.4.1/yxh-data-governance-skill.zip) |
| 供应链分析与方案比较 | [yxh-supply-chain-skill.zip](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/download/yunxiaohe-skills-1.4.1/yxh-supply-chain-skill.zip) |
| DSH 适配器、公开 CLI 与接入文档 | [yunxiaohe-client-source.zip](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/download/yunxiaohe-skills-1.4.1/yunxiaohe-client-source.zip) |

文件摘要见 [Skill 1.4.1 SHA256SUMS.txt](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/download/yunxiaohe-skills-1.4.1/SHA256SUMS.txt)。官网提供相同的三个 Skill 包，可在 GitHub 无法连接时使用。

### 在 Codex、DSH 或其他 Harness 中使用

- **Codex 或支持 SKILL.md 的智能体**：下载所选 Skill ZIP，解压后将其中整个 Skill 目录安装到 Harness 的技能目录。不要只复制 SKILL.md；脚本与参考文件也需要保留。然后开启新对话，按[安装指南](install.md)登录和检查组件。
- **DSH 原生插件**：下载客户端源码包并解压，按其中 `docs/agent-integration.md` 配置 `adapters/dsh/`。路径指向你实际解压的位置，不需要克隆旧仓库。
- **其他智能体或 xworker**：同一源码包中的 `docs/agent-integration.md` 说明 CLI、任务状态和工具结果的接入方式；[官网也可逐文件查看](https://yh-intel.cn/releases/yunxiaohe-local/client/docs/agent-integration.md)。

YH key 只在本机终端的隐藏输入提示中填写，不要贴进对话。不要把模型服务商 key 交给 YH。数据运行时和供应链原生 App 是独立组件，Skill ZIP 不包含它们；安装指令会说明对应的获取方式。

## English

Choose a product and harness on the [official product page](https://yh-intel.cn/en/releases/) and copy its installation instructions. The table above links to the three public Skill packages and the public client source archive. The official site serves the same three Skill ZIPs as a fallback. Verify files against the release's SHA256SUMS.txt.

- **Codex or another SKILL.md-compatible agent:** install the complete extracted Skill directory, including scripts and references, into your harness's Skill directory. Start a fresh conversation and follow the [installation guide](install.md).
- **DSH native plugin:** extract the client source archive and follow its `docs/agent-integration.md` to configure `adapters/dsh/`. Use the actual extraction path; cloning the old repository is not required.
- **Other agents or xworker:** the same guide documents CLI calls, task status and tool results. It is also [available on the official site](https://yh-intel.cn/releases/yunxiaohe-local/client/docs/agent-integration.md).

Using YH services and licensed local components requires your own YH account. Enter the YH key only in a hidden local terminal prompt, not in chat. Your harness keeps its model-provider credentials and makes model calls directly. Data runtimes and the native supply-chain App are separate downloads, not part of the Skill ZIPs.
