# osxutil

## 访达：复制文件路径

将访达（Finder）选中的文件或文件夹路径复制到剪贴板。多选时每个路径占一行，当前用户主目录缩写为 `~`，例如 `~/.codex/config.toml`。主目录之外的路径保留绝对路径。

### 安装到另一台 Mac

1. 下载本仓库的 ZIP 并解压，或克隆仓库。保留整个 [复制文件路径.workflow](复制文件路径.workflow)。
2. 在解压后的仓库目录打开「终端」，运行以下命令。工作流安装到当前用户的服务目录；已有同名工作流时会更新。

   ```sh
   mkdir -p "$HOME/Library/Services" &&
     ditto "复制文件路径.workflow" "$HOME/Library/Services/复制文件路径.workflow" &&
     /System/Library/CoreServices/pbs -update
   ```

### 使用与验证

在访达选中一个或多个文件，右键选择 **服务 → 复制文件路径**，再用 `⌘V` 粘贴到文本编辑器。可以先选一个主目录下的文件确认路径以 `~/` 开头，再选两个文件确认输出为两行。

如果右键菜单里没有这一项，打开 **系统设置 → 键盘 → 键盘快捷键 → 服务**，勾选「复制文件路径」后再试。参见 [Apple《在 Mac 上的 App 中使用服务》](https://support.apple.com/zh-cn/guide/mac-help/use-services-in-apps-mchlp1012/mac)。

已在 macOS 26.6.2 验证单选和多选。卸载时，将 `~/Library/Services/复制文件路径.workflow` 移到废纸篓即可。
