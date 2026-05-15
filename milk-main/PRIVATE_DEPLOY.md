# 私人部署

目标：用户只拿到一个网址，用自己的邮箱验证码进入网站。

推荐方案：Cloudflare Pages + Cloudflare Access。

1. 把本目录作为静态网站部署到 Cloudflare Pages，入口文件是 `index.html`。
2. 给 Pages 项目绑定域名，例如 `chat.example.com`。
3. 进入 Cloudflare Zero Trust，给 `chat.example.com` 新建 Access Application。
4. 登录方式选 One-time PIN。
5. Policy 只允许用户邮箱，例如 `user@example.com`。
6. 把网址发给用户。用户打开后输入邮箱，收验证码，进入网站。

不要用前端密码框当安全方案。前端代码会被浏览器下载，懂一点的人可以绕过。

站内数据主要存在用户当前浏览器里。换设备或清浏览器数据前，要先在“数据管理”里导出备份，再到新设备导入。
