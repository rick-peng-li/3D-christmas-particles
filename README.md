# 🎄 圣诞树手势互动项目 (Gesture Christmas Tree)

这是一个基于 Three.js 和 MediaPipe 的前端单文件应用，实现了一个可以通过手势控制的 3D 粒子圣诞树。

## ✨ 项目特色

*   **视觉效果**：哑光绿、金属金与圣诞红的主色调，配合电影级辉光效果（Bloom），营造高级节日氛围。
*   **手势控制**：
    *   ✊ **握拳 (Fist)**：粒子聚合成圣诞树形状。
    *   🖐 **张开手掌 (Open Hand)**：粒子向四周扩散（爆炸效果）。
    *   无手势：默认恢复为圣诞树形状。
*   **照片云**：支持上传本地照片，照片会作为粒子加入到圣诞树中。
*   **技术栈**：HTML5, CSS3, JavaScript (ES Modules), Three.js, MediaPipe Hands。

## 🚀 启动指南

您可以选择 Docker 启动或直接打开文件运行。

### 方式一：Docker 启动 (推荐)

1.  **前置要求**：安装 [Docker](https://www.docker.com/) 和 Docker Compose。
2.  **启动命令**：在项目根目录下运行：

    ```bash
    docker-compose up -d --build
    ```

3.  **访问项目**：浏览器访问 **http://localhost:3000**

### 方式二：直接打开

由于本项目是单文件应用，且依赖通过 CDN 加载，您也可以直接运行：

1.  找到 `frontend` 目录下的 `index.html` 文件。
2.  直接双击打开，或将其拖入浏览器中。

**注意**：
*   部分浏览器出于安全策略，可能会限制 `file://` 协议下的摄像头访问权限。
*   如果遇到摄像头无法打开的情况，建议使用 VS Code 的 **Live Server** 插件启动，或使用 Python 启动简易服务器：
    ```bash
    # 在 frontend 目录下
    python -m http.server 3000
    ```

### 注意事项

*   首次打开可能需要几秒钟加载 AI 模型。
*   请务必允许浏览器使用 **摄像头权限** 以启用手势控制。

## 📁 目录结构

```
.
├── frontend/
│   └── index.html      # 核心代码（HTML+JS+CSS）
├── Dockerfile          # 镜像构建文件
├── docker-compose.yml  # Docker 编排文件
├── .dockerignore       # Docker 忽略文件
├── .gitignore          # Git 忽略文件
└── README.md           # 项目说明文档
```

## 🛠️ 交互说明

1.  **摄像头权限**：进入页面后，请允许摄像头访问权限。
2.  **手势识别**：将手举起到摄像头视野内。
    *   握紧拳头，树木会更加紧凑（或保持树形）。
    *   张开五指，树木粒子会飞散开来。
3.  **上传照片**：点击左上角的 "UPLOAD PHOTOS" 按钮，选择本地图片，它们将飞入场景中成为圣诞树的一部分。
