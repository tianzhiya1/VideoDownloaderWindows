# VideoDownloader for Windows

Windows 视频链接提取工具。输入视频网页后，软件使用 yt-dlp 或内置浏览器解析出媒体直链；复制链接后，使用 Chrome、Edge 等浏览器自行下载。**软件本身不下载视频文件。**

## 功能
- 内置 Chromium 浏览器，可监听网页播放器公开请求的 MP4、M3U8、MPD 等媒体地址。
- 使用 yt-dlp 解析 YouTube 及其他支持网站的视频直链。
- 解析后显示候选媒体地址，选择并复制到浏览器。
- 支持从本机 Chrome、Edge、Firefox、Brave 读取 YouTube 登录 Cookie，或导入 Netscape 格式 cookies.txt。
- 保留 Bilibili 公开视频链接解析。
- Windows 便携 ZIP，无需单独安装 Python、Deno 或 FFmpeg。

## 使用方法
1. 将视频网页地址粘贴到顶部输入框。
2. 点击“解析视频并获取下载链接”。
3. 等待解析完成，在右侧选择媒体地址。
4. 点击“复制所选视频链接”，复制后粘贴到 Chrome、Edge 等浏览器地址栏，或在浏览器中打开链接。
5. 如果网站提供的是 M3U8/MPD 播放清单，浏览器可能不会像 MP4 那样直接保存；这类链接需要支持相应流格式的下载工具或播放器。

## YouTube 登录验证
如果 YouTube 提示“Sign in to confirm you're not a bot”，可选择已登录 YouTube 的 Chrome、Edge、Firefox 或 Brave，让 yt-dlp 读取本机浏览器 Cookie；使用前请完全退出对应浏览器。也可导入 Netscape 格式 cookies.txt。Cookie 是账号凭据，请勿分享或上传。Cookie 导入不保证解决所有验证，YouTube 仍可能要求额外验证或 PO Token。

## 开发运行
需要 Windows 10/11 64 位与 Python 3.11。

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
python main.py
```

## 限制
直链可能有时效、来源页或请求头要求；部分网站会返回分离的音视频流，或加密/动态播放清单，因此不保证所有链接都能直接在浏览器下载。软件不会绕过 DRM、付费墙、私密内容或其他访问控制。请只提取和保存你有权访问的内容。
