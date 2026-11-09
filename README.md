# 创作者工作台 · 个人品牌站

这是一个静态单页站，用于放在公众号/小红书/视频号主页的「链接」位置，集中展示：

- 个人定位与简介
- 6 篇正在写的内容
- 3 个可下载产品：创作者工作台模板 zip、AI 落地自查清单 PDF、AI 落地 90 分钟诊断服务说明 PDF

## 可部署包

`creator-workbench-site-v0.1.zip` 已包含 `index.html`、assets、downloads 和部署说明，可直接上传 GitHub Pages / Cloudflare Pages。

## 线上地址

https://striveh.github.io/creator-workbench-site/

## 本地预览

```bash
cd /Users/huangqingxi/workspace/creater/site
python3 -m http.server 8080
# 浏览器打开 http://127.0.0.1:8080
```

## 文件

```
site/
├── index.html       # 单页站
├── assets/          # 6 篇文章封面
├── articles/        # 6 篇本地文章预览（站点包内自带）
├── products/        # 3 个产品详情页
├── downloads/       # 可下载的 zip / PDF（含服务说明）
├── site-cover.png   # 预览截图
├── robots.txt       # 搜索引擎抓取规则
├── sitemap.xml      # 站点地图
├── 404.html         # 自定义 404
├── creator-workbench-site-v0.1.zip # 可直接上传静态托管的站点包
└── README.md
```

## 部署建议

1. 推荐 GitHub Pages / Cloudflare Pages / Vercel 任选一个静态托管；
2. 上传整个 `site/` 目录即可，`downloads/` 里的两个文件会随站点一起可下载；
3. 6 个文章卡片已指向 `articles/<slug>/index.html`，站点包自带文章页；正式发布后可以把它们替换成公众号文章链接；
4. 如果需要域名，建议使用自己的名字或品牌名，不要用第三方的免费子域名作为长期主站。

## 注意

- 页面里的「回复清单/工作台领取」需要先在公众号后台配置关键词自动回复；
- 不用虚构阅读量、粉丝数、销量；页面上的「30」是公众号后台真实的发表次数，「6」是当前内容项目数。
