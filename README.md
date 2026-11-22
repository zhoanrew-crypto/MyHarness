# PocketHarness Android 工程

本工程将移动端 AI Agent Harness 应用封装为原生 Android App（Kotlin + WebView），并已放开局域网/本机 `http://` 明文通信与跨域限制，安装 APK 后可直接在手机上连接：
- 本机 Termux 运行的 Ollama（`http://127.0.0.1:11434/v1`）
- 局域网电脑运行的 Ollama / LM Studio / vLLM（例如 `http://192.168.1.100:11434/v1`）
- 各类云端 OpenAI 兼容 HTTPS API（DeepSeek、OpenAI、OpenRouter、硅基流动等）

## 方式一：使用 Android Studio 本地打包 APK（推荐）
1. 解压 `PocketHarness-Android.zip`。
2. 打开 **Android Studio**，选择 **Open** 并选中解压后的文件夹，等待 Gradle 自动同步完成。
3. 点击顶部菜单 **Build → Build Bundle(s) / APK(s) → Build APK(s)**。
4. 构建完成后，在 `app/build/outputs/apk/debug/app-debug.apk` 获取安装包，传到手机安装即可。

## 方式二：无需本地环境，用 GitHub Actions 云端自动构建 APK
1. 在 GitHub 创建一个新仓库，将解压后的全部文件上传（保留 `.github/workflows/build-apk.yml`）。
2. 进入仓库的 **Actions** 页面，等待 **Build Android APK** 自动运行完成（约 2 分钟）。
3. 在构建结果的 **Artifacts** 区域下载 `PocketHarness-debug-apk`，解压后即可得到 `app-debug.apk`。
