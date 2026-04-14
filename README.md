# Y-Tools

一个开发者工具集合，支持网页端和桌面端。

## 功能

- **YAML/Properties 转换**：YAML 与 Properties 格式互转
- **JSON 工具**：格式化、压缩、转义、去转义、快照对比
- **SQL 工具**：格式化、压缩、分析 SQL 语句
- **文件对比**：对比两个文本文件，高亮显示差异
- **时间戳转换**：Unix 时间戳与日期时间互转

## 使用方式

### 网页端

直接访问部署在 Vercel 的网页版本，或者本地运行：

```bash
# 使用 Python 简单服务器
python3 -m http.server 8080

# 或使用 Node.js 服务器
npx serve .
```

然后访问 http://localhost:8080

### 桌面应用

#### 开发环境

```bash
# 安装依赖
npm install

# 运行开发版本
npm run tauri:dev
```

#### 构建桌面应用

```bash
# 构建生产版本
npm run tauri:build
```

构建完成后，安装包位于 `src-tauri/target/release/bundle/` 目录下。

## 自动构建

项目配置了 GitHub Actions 自动构建流程：

1. 当你推送一个新的 tag（如 `v0.1.0`）时，会自动触发构建
2. 构建完成后，会在 GitHub Releases 创建一个 draft release
3. 包含 macOS、Windows、Linux 三个平台的安装包

### 发布新版本

```bash
# 创建并推送 tag
git tag v0.1.0
git push origin v0.1.0
```

## 技术栈

- **前端**：原生 HTML/CSS/JavaScript
- **桌面框架**：Tauri (Rust)
- **部署**：Vercel (网页端) + GitHub Releases (桌面端)

## 项目结构

```
y-tools-1/
├── index.html              # 前端页面
├── package.json            # Node.js 配置
├── vercel.json             # Vercel 部署配置
├── src-tauri/              # Tauri 后端
│   ├── src/
│   │   └── main.rs         # Rust 主程序
│   ├── Cargo.toml          # Rust 配置
│   ├── tauri.conf.json     # Tauri 配置
│   └── icons/              # 应用图标
└── .github/
    └── workflows/
        └── build-desktop.yml  # GitHub Actions 配置
```

## 开发要求

- Node.js 18+
- Rust (stable)
- 系统依赖：
  - macOS: Xcode Command Line Tools
  - Windows: Microsoft Visual Studio C++ Build Tools
  - Linux: GTK 3, WebKit2GTK

## License

MIT
