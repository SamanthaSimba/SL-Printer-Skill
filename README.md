# SL Printer Skill

校园 FUJIFILM Apeos C2060 与 HP Color LaserJet Pro MFP M281fdw 自动安装 Skill。

## 下载

完整 Skill 包含厂商驱动，体积超过 GitHub 普通文件的 100 MB 限制。请从仓库右侧 **Releases** 下载 `install-school-printer.zip`，不要使用 `Code -> Download ZIP`。

当前发布为开发版：Windows 静态测试、驱动哈希与签名校验、型号识别和 dry-run 已通过；macOS 尚未完成真实 Mac 构建与真机认证。

## 文件校验

```text
文件：install-school-printer.zip
大小：276M 字节
SHA-256：3CDB1F5E10269BFFBBC2817F2B159365C9E4B44DA1EB411779D181033C947B7A
```
解压后需要保留完整的 `install-school-printer/` 目录，不能只复制 `SKILL.md`。

不能直接把 ZIP 丢给 Codex 就使用。当前这个文件是一个 Codex Skill，需要先解压并放到 Codex 的 Skill 目录。
Windows：
%USERPROFILE%\.codex\skills\install-school-printer\
macOS：
~/.codex/skills/install-school-printer/
解压后目录结构必须类似：
install-school-printer/
├── SKILL.md
├── agents/
├── assets/
├── scripts/
└── references/
然后重新打开 Codex，在对话中输入：
使用 $install-school-printer 安装打印机，IP 是 192.168.1.100(例)
不要只复制 SKILL.md，因为驱动和脚本都在 assets/、scripts/ 中。
另外要注意：当前 ZIP 是 Codex Skill，不是独立的“双击安装程序”。

