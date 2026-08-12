# SL Printer Skill

用于校园内网打印机自动识别、驱动安装和打印队列配置的 Codex Skill。

支持的打印机：

- FUJIFILM Apeos C2060
- HP Color LaserJet Pro MFP M281fdw

支持 Windows 10/11 和 macOS 11–15、26。用户通常只需要提供打印机 IPv4 地址。

## 下载

完整 Skill 包含厂商驱动，体积超过 GitHub 普通文件的 100 MB 限制。

请从仓库右侧 **Releases** 下载：

👉 [下载 install-school-printer.zip](https://github.com/SamanthaSimba/SL-Printer-Skill/releases/download/v0.1.0-dev/install-school-printer.zip)

不要使用 `Code -> Download ZIP`，那个只会下载源代码，不包含本次发布的完整驱动包。

## 安装 Skill

1. 下载 `install-school-printer.zip`。
2. 解压 ZIP 文件。
3. 将解压后的完整 `install-school-printer` 文件夹复制到对应目录。

Windows：

```text
%USERPROFILE%\.codex\skills\install-school-printer\
```

macOS：

```text
~/.codex/skills/install-school-printer/
```

目录结构必须类似：

```text
install-school-printer/
├── SKILL.md
├── agents/
├── assets/
├── scripts/
└── references/
```

不能只复制 `SKILL.md`，驱动位于 `assets/`，安装脚本位于 `scripts/`。

## 使用 Skill

重新打开 Codex，在对话中输入：

```text
使用 $install-school-printer 安装打印机，IP 是 192.168.1.100
```

Skill 会先探测打印机型号并执行 dry-run。确认识别结果和安装计划后，才会请求管理员权限并修改系统。

默认不会打印测试页，也不会删除已有打印机或打印任务。

## 文件校验

```text
文件：`install-school-printer.zip`
大小：`276,319,260` 字节（约 276 MB）
SHA-256：3CDB1F5E10269BFFBBC2817F2B159365C9E4B44DA1EB411779D181033C947B7A
```

Windows PowerShell 校验命令：

```powershell
Get-FileHash .\install-school-printer.zip -Algorithm SHA256
```

macOS 校验命令：

```bash
shasum -a 256 install-school-printer.zip
```

## 当前状态

这是 `v0.1.0-dev` 开发版：

- Windows 静态测试、驱动哈希与签名校验、型号识别和 dry-run 已通过。
- macOS 脚本和静态校验已完成。
- macOS 尚未完成真实 Mac 构建、签名和打印机实机认证。
- 无代码签名证书，Windows SmartScreen 或 macOS Gatekeeper 可能显示安全警告。

遇到错误时，请先查看 Skill 内的 `references/troubleshooting.md`。
