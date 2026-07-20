# Codex Skin Studio

Windows 桌面主题客户端，可为 Microsoft Store 版 OpenAI Codex 应用背景皮肤。

本仓库当前用于发布 Windows 安装包与版本说明。

## 下载

前往 [Releases](https://github.com/gengyj-g/Codex-Skin-Studio/releases) 下载最新的
`Codex-Skin-Studio-0.1.0-Setup.exe`。当前安装包未进行商业代码签名，Windows 可能显示
“未知发布者”提示。请只从本仓库的 Releases 页面下载。

## 功能

- 4 套离线预设主题与实时 Codex 窗口预览
- 导入 PNG、JPEG、WebP 图片，限制 16 MB / 5000 万像素
- 调节明暗、背景焦点、文字安全区和界面外观
- 一键应用、暂停、继续和恢复官方外观
- 使用本机回环 CDP，不修改 `WindowsApps`、`app.asar` 或应用签名

## 开发

```powershell
npm install
npm run dev
```

## 构建 Windows 安装包

```powershell
npm run build
```

安装包输出到 `release/`。首次实际应用主题前需要完全退出 Codex；之后客户端会通过受验证的本地引擎重新打开 Codex。

## 安全边界

- 只支持当前用户已注册的官方 `OpenAI.Codex` Store 包。
- 调试端口只绑定 `127.0.0.1`。
- 用户图片只复制到 `%LOCALAPPDATA%\CodexDreamSkin`。
- 不读取或修改 API Key、Base URL、模型供应商和对话内容。

## 来源

CDP 运行时基于 [Fei-Away/Codex-Dream-Skin](https://github.com/Fei-Away/Codex-Dream-Skin) 的 Windows 实现集成。预设照片来自 Unsplash，详见 `ATTRIBUTIONS.md`。

## 许可证

本项目原创代码采用 [MIT License](LICENSE)。第三方代码与图片不属于该 MIT 授权范围，
仍受各自条款约束，具体见 [ATTRIBUTIONS.md](ATTRIBUTIONS.md)。上游项目在本项目取用时没有
提供明确的根目录许可证；公开分发前应向上游作者确认授权。
