# upgrade_file_convert_tool

安装包与自动更新分发仓（源码与 CI 在自建 Gitea，本仓只放 Releases）。

## 安装

### Windows

下载 Release 中的 `*_x64_zh-CN.msi` 双击安装。应用内可自动更新（更新时有一次 UAC 确认）。

### Linux（AppImage）

```bash
sudo apt install libfuse2        # Debian/Ubuntu 首次需要；Arch 用 sudo pacman -S fuse2
bash install-appimage.sh upgrade_file_convert_tool_X.Y.Z_amd64.AppImage
```

安装后应用内自动更新（原地替换 `~/Applications/upgrade_file_convert_tool.AppImage`）。
也可用 Gear Lever / AppImageLauncher 等工具管理。

## 自动更新

客户端启动时检查 `releases/latest/download/latest.json`，有新版本会弹窗提示，
确认后自动下载安装并重启。更新包经 minisign 签名，本仓被篡改也无法通过校验。
