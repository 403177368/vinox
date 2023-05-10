---
description: vscode
---

# vscode

## Vetur

```
vscode中开启vetur扩展的这两个选项，可以一定程度上对vue template中的变量进行类型检测。

How to get type-checking-for-vue-template-support from vetur: 
  Access Extensions => Vetur => Extension Settings:
  Enable these options:
    Vetur › Experimental: Template Interpolation Service
    Vetur › Validation: Template Props
  Vetur author's blog post about these features:
    https://blog.matsu.io/vue-prop-type-validation
    Type checking for object-typed-props of child component is not supported by vetur yet.
```

## Eslint插件的使用

```
1 在vscode中安装eslint插件。该插件将会在编辑器中标注出不符合eslint规范的代码。
2 vscode中打开Command Palette，使用如下这条命令可自动修复当前文件中不符合eslint规范的代码。
  ESLint: Fix all auto-fixable Problems
3 启用保存文件时自动修复：
  右键 => Command Palette... => Preferences: Open Settings (JSON)
  追加以下配置：
```

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

1. 在vscode中安装stylelint扩展。
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
