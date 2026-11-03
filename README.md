# VideoDownloader for Windows

独立的 Windows 视频下载与媒体链接提取工具，已加入 yt-dlp，可下载 YouTube 和 yt-dlp 支持的公开视频页面。

## 功能
- 内置 Chromium 浏览器（Qt WebEngine）。
- 监听 MP4、HLS M3U8 和 DASH MPD 等网页媒体请求。
- 分析网页 HTML 中公开的媒体直链。
- 新增 **YouTube / yt-dlp 解析**：读取标题并尝试解析可用媒体地址。
- 新增 **下载视频**：后台下载、进度显示、最高尝试 1080p，并使用内置 FFmpeg 合并音视频。
- 保留 Bilibili 视频 MP4 解析。
- Windows 便携 ZIP，无需单独安装 Python、Deno 或 FFmpeg。

## 使用 YouTube

- 下载按钮旁可选择“不读取登录 Cookie”、Chrome、Edge 或 Firefox。若 YouTube 提示验证机器人，请先在所选浏览器中登录 YouTube，再选择对应浏览器重试。读取的是本机浏览器 Cookie，不会上传到 GitHub。使用 Chrome/Edge 时建议先完全退出浏览器，避免 Cookie 数据库被锁定。
1. 复制 YouTube 视频页面链接并粘贴到软件顶部网址栏。
2. 点击“**YouTube / yt-dlp 解析**”可识别视频媒体地址。
3. 点击“**下载视频**”可直接下载并合并音视频。
4. 文件默认保存在 Windows“下载”目录下的 `VideoDownloader` 文件夹。

## 开发运行
需要 Windows 10/11 64 位与 Python 3.11。

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
python main.py
```

## 说明与限制
yt-dlp 和 YouTube 播放器会持续更新，偶尔可能需要升级软件。视频是否可用还受地区、网络、年龄、账号权限及平台策略影响。软件不会绕过 DRM、付费墙、私密内容或其他访问控制。请只下载你有权保存的内容。
