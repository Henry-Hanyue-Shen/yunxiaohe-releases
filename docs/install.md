# 云小鹤本地版 / YunXiaoHe Local

Official release: **CLI 1.4.1 · runtime 20261003-r7**

官网 / Official page: https://yh-intel.cn/releases/yunxiaohe-local/

[运行时版本与验证 / Runtime release and validation](https://yh-intel.cn/releases/yunxiaohe-local/client/docs/release-20261003-r7.md)

**数据运行时可公开下载，使用仍需有效的 YH 账号。** 安装器优先从 GitHub 下载，连接失败时回退官网；模型调用与模型 key 仍由你自己的 Harness 管理。

**Data runtimes are public downloads; use requires an active YH account.** The installer uses GitHub first and the official site as fallback. Your harness keeps its model-provider key and makes model calls directly.

已有用户：先更新 Skill，再运行 `runtime install` 与 `runtime doctor`。
Existing users: update the Skill first, then run `runtime install` and `runtime doctor`.

## 给新对话的安装指令 / Instruction for a new conversation

```text
请阅读 https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/blob/main/docs/install.md，
安装最新版云小鹤 Skill 和适合这台电脑的本地数据运行时。
使用指南中的安装器，优先从 GitHub 下载；下载中断后用 runtime install 续传，不要并行重复安装。
继续使用当前会话的模型。使用运行时需要 YH 账号；需要登录时让我在终端隐藏输入 key，不要发到聊天里。
安装后运行 runtime doctor，告诉我结果，再等我选择数据文件。
```

```text
Read https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/blob/main/docs/install.md
and install the latest YunXiaoHe Skill and the local data runtime for this computer.
Use the guide's installer with GitHub as the first download source. Resume interruptions
with runtime install; do not start parallel installers. Keep this session's model.
Using the runtime requires a YH account. If sign-in is needed, let me enter my key
at a hidden terminal prompt, not in chat. Run runtime doctor, report the result,
and wait for me to choose the data files.
```

## 中文：在 Codex 中使用

你需要一个已开通「云小鹤」和「本地应用下载」的 YH 账号，以及
Windows x64 或 Linux x86_64 电脑。Linux 在 Ubuntu 24.04 验证，需要 glibc 2.39
或兼容环境；不适用于更早的 glibc。macOS 和 ARM 不在此版本支持范围内。
安装 CLI 使用 Python 3.10 或更新版本；运行时附带自身的数据处理依赖。
Windows 运行时是未签名的便携压缩包，不是已签名安装器。

1. 在 https://yh-intel.cn/client/api-keys 创建自己的 **YH API key**。
   这把 key 负责 YH 账号授权，不是模型服务商 key。
2. 下载公开 Skill：https://yh-intel.cn/releases/yunxiaohe-local/yunxiaohe-client.zip 。
   也可使用[新发布仓库的 GitHub 下载](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/download/yunxiaohe-skills-1.4.1/yunxiaohe-client.zip)，两处提供相同的 Skill 包。
   解压后，将其中的 `yunxiaohe-client` 文件夹安装到你的 Harness 所用的 Skill 目录。
   也可以让 Codex 按本指南下载并安装这个公开 ZIP，无需访问 GitHub 或私有仓库。
   Skill 没有出现时，重新打开 Codex。
3. 在已安装的 `yunxiaohe-client` 目录中打开终端，运行：

   ```sh
   python scripts/yxh.py login
   python scripts/yxh.py runtime install
   python scripts/yxh.py runtime doctor
   ```

   Windows 也可用 `py -3`，Linux 可用 `python3` 替换上述命令前缀。
   只在 `login` 的隐藏输入提示中输入 YH key，**不要把 key 发进聊天、写进命令参数或日志**。
   CLI 1.4.1 先向官网验证账号并获取对应平台的发行清单，再从 GitHub 下载公开运行时。
   GitHub 连接失败时改用官网下载；YH key 不会发给 GitHub。
   安装器显示大小和速度，支持断点续传，核对大小与 SHA-256 后才安装。
   如果返回未授权，请在客户中心检查账号权限；不要使用他人的 key。
4. 新开一个本地项目对话，告诉 Codex 使用 `$yunxiaohe-client`，指定数据文件和目标。
   例如：

   > 请用云小鹤分析 sales.csv，检查缺失值，按地区汇总销售额，并解释差异。
   > 保留原始文件。

   或者：

   > 请用 RISA 为 train.csv 的 target 列建模，优先准确率，保存模型和验证结果，
   > 并预测 predict.csv。

下载中断时，等待当前安装命令结束后重跑 `runtime install`，会接着已有进度继续。
CLI 1.4.1 连续 30 秒没有收到数据时会重连，一次安装最多尝试 6 次；不要同时启动多个安装器。

### 单独下载数据运行时

也可以直接从 [GitHub Release](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/tag/yunxiaohe-local-20261003-r7)
下载 Windows ZIP 或 Linux tar.gz，无需 GitHub 或 YH 登录。
按 Release 内的 `SHA256SUMS.txt` 校验并解压后，运行 `yxh-runtime.exe login`（Windows）
或 `./yxh-runtime login`（Linux），输入自己的 YH key。下载不等于开通使用权限。
这个 Release 提供数据计算运行时，不包含桌面 GUI 或供应链原生安装包。

模型由当前 Codex／DSH／其他 Harness 自己调用，保持你原有的模型与账户配置。
模型服务商 key 不需要交给 YH。表格处理、特征工程、训练和预测在本机运行；
发送给模型的上下文仍遵循你在 Harness 中的授权与设置。

### 给智能体和其他 Harness

使用同一 CLI，无需另写 RISA 训练脚本。
路径由用户明确选择。先读取精简概要，再根据目标提交计划：

```sh
python scripts/yxh.py data prepare --file sales.csv --output .yh-results
python scripts/yxh.py data execute --file sales.csv --output .yh-results --plans plans.json
```

建模默认使用准确率优先策略、特征工程和五折训练侧交叉验证。
以本地执行返回的验证指标为准，保留切分、特征和模型产物。
下次遇到新数据，可以复用保存的完整交付目录直接预测，不必重新训练。
详细命令见公开 Skill 内的
[本地数据指南](https://yh-intel.cn/releases/yunxiaohe-local/client/yunxiaohe-client/references/local-data.md)。
需要比较用量时，用相同任务、模型、数据与质量要求做独立对照，并保留真实 Token 记录。

DSH 与多智能体接入说明：
https://yh-intel.cn/releases/yunxiaohe-local/client/docs/agent-integration.md

### 账号 API 与公开下载

- 根地址：`https://yh-intel.cn/client/yunxiaohe/skill/v1/`
- `GET architecture`：账号验证后的本地执行架构，不创建远端 worker。
- `GET runtime/releases`：已获本地下载权限的平台列表、版本、文件大小与 SHA-256。
- `GET runtime/download/windows-x64` 或 `GET runtime/download/linux-x64`：账号验证后的下载入口；CLI 1.4.1 可请求 GitHub 公开镜像跳转。
- API 使用 `Authorization: Bearer <YH account key>`；不接受浏览器 Cookie 代替 key。
- 上述 API 每次请求核对账号与权限；GitHub Release 本身可公开下载，不需要 YH key。
- CLI 每次数据操作重新检查账号；DSH 常驻数据会话在空闲满一小时后重新验证。
  `runtime doctor` 只检查本地组件，不验证账号登录。

公开 Skill ZIP 包含客户接入代码和文档；原生数据运行时在 GitHub Release 单独提供。
停用账号或 key 会阻止新的数据操作，不会撤销公开文件的下载资格。

---

## English: use it in Codex

You need a YH account with **YunXiaoHe** and **local application download** access,
and a Windows x64 or Linux x86_64 computer. Linux is tested on Ubuntu 24.04 and
requires glibc 2.39 or a compatible environment; earlier glibc is not supported.
This release does not support macOS or ARM. The small installer CLI needs Python 3.10 or later. The runtime includes
its own data-processing dependencies.
The Windows runtime is an unsigned portable archive, not a signed installer.

1. Create your own **YH API key** at https://yh-intel.cn/client/api-keys .
   This key authorizes your YH account; it is not your model-provider key.
2. Download https://yh-intel.cn/releases/yunxiaohe-local/yunxiaohe-client.zip .
   The [new release repository's GitHub download](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/download/yunxiaohe-skills-1.4.1/yunxiaohe-client.zip) provides the same Skill package.
   Extract it and install the `yunxiaohe-client` folder in your harness's Skill
   directory. You can ask Codex to download and install this public ZIP using
   this guide; no GitHub or private-repository access is needed.
   Reopen Codex if the Skill does not appear.
3. Open a terminal in the installed `yunxiaohe-client` directory and run:

   ```sh
   python scripts/yxh.py login
   python scripts/yxh.py runtime install
   python scripts/yxh.py runtime doctor
   ```

   On Windows, `py -3` also works; on Linux, replace `python` with `python3` if needed. Enter your YH key only
   at the hidden login prompt, **never in chat, a command argument or a log**.
   CLI 1.4.1 authenticates with the official catalog, then downloads the public
   platform archive from GitHub, falling back to the official site if needed.
   It never sends your YH key to GitHub. It displays progress, resumes interrupted
   transfers, and verifies archive size and SHA-256 before installation.
   If access is denied, check your account grants in the client center; do not
   use someone else's key.
4. Start a new local project conversation, request `$yunxiaohe-client`, and name
   the input and goal. For example:

   > Use YunXiaoHe to analyze sales.csv: check missing values, summarize sales
   > by region, and explain the differences. Preserve the original file.

   Or:

   > Use RISA to model the target column in train.csv, prioritizing predictive
   > quality. Save the model and validation results, then predict predict.csv.

If a download is interrupted, let the current command finish and rerun `runtime install`
to continue the saved transfer. CLI 1.4.1 reconnects after 30 seconds without data,
with up to six attempts per invocation. Run one installer at a time.

### Download the data runtime separately

The [GitHub Release](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/tag/yunxiaohe-local-20261003-r7)
provides Windows ZIP and Linux tar.gz downloads without GitHub or YH sign-in.
Verify `SHA256SUMS.txt`, extract the archive, then run `yxh-runtime.exe login`
(Windows) or `./yxh-runtime login` (Linux) with your own YH key. Downloading does
not grant product access. These are data-computation runtimes, not desktop GUI
or supply-chain native packages.

Your Codex, DSH or other harness continues to call its own configured model.
Do not send model-provider credentials to YH. Table processing, feature
engineering, training and inference run locally; context sent to the model
still follows your harness settings and authorization.

### Other agents and harnesses

Call the same CLI. Select files explicitly, read a compact profile and submit
a plan. There is no need to write a separate RISA training script.

```sh
python scripts/yxh.py data prepare --file sales.csv --output .yh-results
python scripts/yxh.py data execute --file sales.csv --output .yh-results --plans plans.json
```

The modeling default is predictive-quality-first selection with feature
engineering and five-fold training-side cross-validation. Use the returned
validation results and preserve the split, feature and model artifacts.
Reuse the complete saved delivery directory to predict on another table without
retraining. The bundled
[local data guide](https://yh-intel.cn/releases/yunxiaohe-local/client/yunxiaohe-client/references/local-data.md)
includes the replay command.
Token comparisons require independent runs of the same task, model, data and
quality requirements, with actual provider usage receipts.

DSH and multi-agent integration:
https://yh-intel.cn/releases/yunxiaohe-local/client/docs/agent-integration.md

### Account API and public downloads

Base: `https://yh-intel.cn/client/yunxiaohe/skill/v1/`

- `GET architecture`: authenticated local-execution architecture; creates no remote worker.
- `GET runtime/releases`: entitled platforms, version, size, SHA-256 and relative download path.
- `GET runtime/download/windows-x64` or `GET runtime/download/linux-x64`: authenticated download entry; CLI 1.4.1 can request a redirect to the public GitHub mirror.
- Use `Authorization: Bearer <YH account key>`; browser cookies are not API credentials.
- These API requests recheck account, key and product access. The GitHub Release itself is public and needs no YH key.
- The CLI rechecks access on each data operation; long-lived DSH data sessions recheck after an idle hour.
  `runtime doctor` checks local components, not account access.

The public Skill ZIP contains customer integration code and documentation.
Native data runtimes are separate GitHub Release assets. Disabling an account
or key prevents new data operations; it does not revoke access to public files.

YH Intelligence Technology, Co., Ltd.
