# 云小鹤本地运行时 r7 / YunXiaoHe local runtime r7

**安装包公开下载，使用需要 YH 账号。 / Public downloads; a YH account is required to use the runtime.**

这是官网 `20261003-r7` 数据治理运行时的 GitHub 下载源，Windows／Linux 文件与原发行版逐字节相同。只调整下载方式，没有更改 RISA、特征工程、模型选择或计算代码。源码仓库仍保持私有。

- Windows x64：176,736,079 bytes，未签名便携运行时。
- Linux x86_64：270,337,722 bytes，需要 glibc 2.39+。
- 请核对本 Release 附带的 `SHA256SUMS.txt`。
- 从[官网安装 Skill](https://yh-intel.cn/releases/#data-governance)，或解压运行时后执行 `login`。登录使用 YH 账号签发的 key，模型 key 仍由自己的 Harness 管理。

These are byte-identical copies of the official `20261003-r7` data runtime. Only the download path changes; RISA, feature engineering, model selection and computation are unchanged. The source repository remains private.

Verify the attached `SHA256SUMS.txt`. Install the Skill through the [official guide](https://yh-intel.cn/en/releases/#data-governance), or extract the runtime and run `login`. Use your own YH account-issued key. Your harness retains the model-provider key.

The archives retain their customer and third-party licenses. This release contains neither desktop GUI packages nor a macOS candidate.
