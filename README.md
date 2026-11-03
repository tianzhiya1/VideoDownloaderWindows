# VideoDownloader for Windows

独立的 Windows 视频媒体链接提取器。它使用内置浏览器识别网页公开请求的媒体地址，并允许逐个查看和复制链接。

## 功能
- 内置 Chromium 浏览器（Qt WebEngine）。
- 监听 MP4 等常见视频文件、HLS M3U8 和 DASH MPD 请求。
- 分析网页 HTML 中公开的媒体直链。
- 在公开 API 允许时尝试解析 Bilibili 视频 MP4 地址。
- 候选媒体逐个列出，选择一个后通过唯一的复制按钮查看并复制链接。
- 不自动打开外部浏览器，也不把 MP3 转换功能混入本软件。

## Windows 运行
需要 Windows 10/11 64 位与 Python 3.11。

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
python main.py
```

## 说明与限制
本软件提取网页公开请求到的媒体 URL，不保证所有网站都能识别。需要特殊 Cookie、登录会话、请求头、反爬验证、blob 地址或 DRM 的媒体可能无法使用。本软件不会绕过 DRM、付费墙、登录要求或其他访问控制。请只处理你有权下载的媒体。
