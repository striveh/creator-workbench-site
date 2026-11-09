# 个人品牌站 · 部署说明

**当前线上地址：** https://striveh.github.io/creator-workbench-site/ （GitHub Pages）

## 方案 A：GitHub Pages（最快）

前提：本机 `gh` 已登录 GitHub（当前已登录账号 `striveh`）。

```bash
cd /Users/huangqingxi/workspace/creater/site
gh repo create creator-workbench-site --public --source=. --remote=origin --push
```

（如果当前目录还不是 git 仓库，先 `git init && git add . && git commit -m "creator workbench site v0.1"`。）

然后到 GitHub 仓库 → Settings → Pages → Build and deployment → Source 选 `Deploy from a branch`，Branch 选 `main` / 根目录，保存。几分钟后得到：

`https://<你的GitHub用户名>.github.io/creator-workbench-site/`

> 注意：`site/index.html` 里文章卡片链接指向本地 `../content/...` 预览文件，部署到 GitHub Pages 时这些链接会失效。正式对外前，把 6 个文章卡片换成公众号文章链接（发布后替换），或把文章预览页复制进 `site/articles/`。

## 方案 B：Cloudflare Pages

1. 登录 Cloudflare Dashboard → Workers & Pages → Create → Pages → Upload assets；
2. 把整个 `site/` 目录拖进去；
3. 设置项目名，例如 `creator-workbench`；
4. 得到 `https://creator-workbench.pages.dev`。

## 方案 C：Netlify / Vercel

同样上传 `site/` 目录或连接 GitHub 仓库，构建命令留空，输出目录设为 `site`。

## 自定义域名

推荐用 `你的名字.com` 或 `你的品牌.com`。在托管平台绑定域名后，按平台提示配置 DNS。不要长期依赖免费子域名作为主站。

## 上线前检查

- [ ] 6 个文章卡片换成真实公众号文章链接（或把本地预览页复制进 `site/articles/`）
- [ ] 产品下载链接可点击：`downloads/creator-workbench-template-v0.1.zip`、`downloads/AI落地自查清单-v0.1.pdf`、`downloads/AI落地90分钟诊断-服务说明.pdf`
- [ ] 微信公众号/关键词回复配置好，再写“回复领取”
- [ ] 移动端打开检查：导航、按钮、文章卡片、下载
- [ ] 加统计（可选）：Cloudflare Web Analytics、Umami 或 Vercel Analytics，不要装侵入式追踪
- [ ] 隐私说明：如收集邮箱/联系方式，补一行隐私政策

## 本地预览

```bash
cd site
python3 -m http.server 8080
```
