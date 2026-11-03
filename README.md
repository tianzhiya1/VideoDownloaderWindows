# VideoDownloader for Windows

独立的 Windows 视频媒体链接提取器，现已加入 yt-dlp 引擎，可解析 YouTube 和 yt-dlp 支持的其他公开视频页面。

## 功能
- 内置 Chromium 浏览器（Qt WebEngine）。
- 监听 MP4 等常见视频文件、HLS M3U8 和 DASH MPD 请求。
- 分析网页 HTML 中公开的媒体直链。
- 新增 **YouTube / yt-dlp 解析**：读取标题并尝试解析可用的视频媒体地址。
- 保留 Bilibili 视频 MP4 解析。
- 候选媒体逐个列出，选择一个后通过复制按钮查看并复制链接。
- Windows 便携 ZIP，无需单独安装 Python。
- 构建时打包 Deno JavaScript runtime，供 yt-dlp 处理 YouTube 播放器脚本挑战。

## Windows 运行
需要 Windows 10/11 64 位与 Python 3.11。

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
python main.py
```

## 使用 YouTube
1. 复制 YouTube 视频页面链接。
2. 粘贴到软件顶部网址栏。
3. 点击“**YouTube / yt-dlp 解析**”。
4. 等待解析，选择识别出的媒体地址，再复制。

## 说明与限制
yt-dlp 会随软件版本更新而更新。YouTube 会调整播放器和访问机制，偶尔可能需要更新版本；并非每个视频都能解析。私密、付费、DRM 保护或受其他访问控制的视频不会被绕过。请只下载你有权保存的内容。某些地区、网络环境或视频本身的限制也可能影响可用性。

## 技术
Python、PySide6、Qt WebEngine、requests、yt-dlp、Deno。
