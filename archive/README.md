# 旧客户端历史 / Former client history

这里保存原 `Henry-Hanyue-Shen/yunxiaohe-codex-skill` 公开仓库的完整 Git 历史，供追溯和恢复。**这不是当前安装包。** 新安装请使用[当前 Skill 下载](../docs/skills.md)或[官网](https://yh-intel.cn/releases/)。

This archive preserves the complete Git history of the former public Codex Skill repository. **It is not the current installer.** For new installations, use the [current Skill downloads](../docs/skills.md) or the [official site](https://yh-intel.cn/en/releases/).

## 存档内容 / Contents

- [历史发布 / Historical release](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/tag/legacy-yunxiaohe-codex-skill-20261004)
- [Git bundle](https://github.com/Henry-Hanyue-Shen/yunxiaohe-releases/releases/download/legacy-yunxiaohe-codex-skill-20261004/yunxiaohe-codex-skill-history-20261004.bundle)：1 个分支、4 个标签、8 个提交 / 1 branch, 4 tags, 8 commits
- 原 main / Original main：`905bd5c4a6246d7100eff50893cd3bf75aafdac3`
- 文件大小 / File size：107,758 bytes
- SHA-256：`a8a19da9ad2cee8d7b79cdd3230d64b847b6fb7e3d4d017ae65766e04a8288fa`
- [完整引用与校验记录 / Ref and verification record](yunxiaohe-codex-skill-20261004.json)

历史保留原有 MIT 许可证及版权信息，没有改写提交或标签。Git bundle 不包含机器上的 Git 配置、凭据或工作区文件。这个历史备份与旧仓库在 GitHub 上的 **Archived** 设置是两件事；归档设置由仓库所有者管理。

The original MIT license, attribution, commits and tags are preserved. The bundle excludes machine-local Git configuration, credentials and working-tree files. This history backup is separate from the former repository's GitHub **Archived** setting, which is managed by its owner.

## 恢复历史 / Restore the history

下载并核对 SHA-256 后，在一个新的目录名下运行以下命令。恢复后的代码是历史版本，不应用于当前安装。

After downloading and verifying SHA-256, restore into a new directory with:

```sh
git clone --mirror yunxiaohe-codex-skill-history-20261004.bundle former-client.git
git -C former-client.git fsck --full
git -C former-client.git show-ref
git -C former-client.git rev-list --all --count
```

最后一条命令应返回 `8`。引用应与上面的 JSON 记录一致。当前源码维护与产品发布无需访问旧仓库。

The final command should return `8`, and refs should match the JSON record. Current development and product distribution do not require access to the former repository.
