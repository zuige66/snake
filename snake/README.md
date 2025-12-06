# RetroBit OS (复古比特操作系统)

这是一个基于 Web 的 8-bit 复古游戏机模拟器，内置迷你操作系统、经典小游戏、音乐可视化工具以及由 Google Gemini 驱动的 AI 终端。

## ✨ 功能特性

*   **📺 复古 CRT 视觉效果**: 包含扫描线、屏幕闪烁、晕影和屏幕弯曲效果，沉浸式体验 80 年代显示器风格。
*   **🚀 系统启动序列**: 模拟真实的 BIOS 自检和系统加载过程。
*   **🐍 贪吃蛇游戏**: 经典的贪吃蛇玩法，带有复古音效和计分板。
*   **🎵 音乐播放器**: 带有星空背景和动态波形可视化的 Synthwave 风格音乐播放界面。
*   **🤖 AI 终端 (Oracle)**: 集成 Google Gemini API 的智能对话终端，扮演一个 1989 年的复古机器人助手。

## 🛠️ 技术栈

*   **前端框架**: React 19
*   **样式库**: Tailwind CSS
*   **构建工具**: Vite
*   **AI 模型**: Google Gemini 2.5 Flash (`gemini-2.5-flash`)
*   **字体**: 'Press Start 2P' (像素字体), 'VT323' (终端字体)

## 🚀 如何运行 (本地)

如果您下载了代码并在本地运行，请确保您已创建了所有必要的文件。

1.  **检查文件**:
    确保项目根目录下包含 `package.json`, `vite.config.ts`, `index.html` 以及 `index.tsx` 等文件。

2.  **配置环境**:
    在项目根目录创建一个 `.env` 文件，并添加您的 API Key：
    ```
    API_KEY=您的_GOOGLE_GEMINI_API_KEY
    ```

3.  **安装依赖**:
    ```bash
    npm install
    ```

4.  **启动项目**:
    ```bash
    npm start
    ```

5.  **访问**:
    浏览器打开终端显示的本地地址 (通常是 http://localhost:5173)。

## ☁️ 如何部署 (发布到互联网)

推荐使用 **Vercel** 进行免费部署。

1.  **上传代码**: 将项目代码推送到 GitHub。
2.  **导入项目**: 在 Vercel 面板中导入你的 GitHub 仓库。
3.  **设置环境变量**:
    *   在 Vercel 的部署设置页面 (Configure Project)，展开 **Environment Variables**。
    *   添加一个新的变量：
        *   **Key**: `API_KEY`
        *   **Value**: 您的 Google Gemini API Key
4.  **点击 Deploy**: 等待构建完成，即可获得访问链接。

**⚠️ 安全提示**:
由于这是一个纯前端应用，API Key 会包含在构建后的代码中。建议在 Google Cloud Console 中对您的 API Key 设置 **HTTP referrers 限制**，仅允许您部署的域名（如 `https://your-app.vercel.app/*`）使用该 Key。

## ❓ 常见问题 (Troubleshooting)

### 报错: `npm error code ENOENT` / `Could not read package.json`
**原因**: 您的文件夹中缺少 `package.json` 文件。
**解决**: 请确保您手动创建了 `package.json` 文件，并将项目代码中的 `package.json` 内容完整复制进去。`npm` 需要这个文件来管理项目依赖。

### 报错: `vite is not recognized`
**原因**: 依赖没有安装成功。
**解决**: 请先运行 `npm install`。

### AI 终端回复 "OFFLINE MODE"
**原因**: 没有检测到 API Key，或者 `.env` 文件配置不正确。
**解决**: 检查 `.env` 文件是否存在，且 `API_KEY` 是否填写正确。如果没有 Key，系统将运行在离线模拟模式。

---

© 1989 RETROBIT SYSTEMS LTD.