---
description: vscode
---

# vscode

保存文件时自动修复：

右键 => Command Palette... => Preferences: Open Settings (JSON)

追加以下配置：

```json
{
  "eslint.validate": [
    "javascript",
    {
      "language": "vue",
      "autoFix": true
    },
    {
      "language": "html",
      "autoFix": true
    }
  ],
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.fixAll.stylelint": true
  }
}
```

## Stylelint插件的使用

1. vscode中安装stylelint扩展。
2. 右键 => Command Palette... => stylelint: Fix all auto-fixable Problems 可自动修复代码。
3. 开启保存文件时自动修复：\
   右键 => Command Palette... => Preferences: Open Settings (JSON)\
   追加以下配置：

```json
{
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.fixAll.stylelint": true
  }
}
```

## CssPeek

使用'@/'开头的路径引用文件时，把仓库文件夹放入Vscode workspace中，可获得自动提示。
