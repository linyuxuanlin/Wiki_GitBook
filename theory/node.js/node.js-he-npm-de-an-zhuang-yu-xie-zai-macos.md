# Node.js 和 npm 的安装与卸载（MacOS）

## 安装

[http://nodejs.cn/download/](http://nodejs.cn/download/)

## 卸载

通过 `homebrew` 安装的：

```bash
brew uninstall node
```

通过 `.pkg` 安装包安装的：

```bash
sudo rm -rf /usr/local/{bin/{node,npm},lib/node_modules/npm,lib/node,share/man/*/node.*}
```

