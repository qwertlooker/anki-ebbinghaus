# Anki + 艾宾浩斯记忆网页

这是一个可直接部署的单页 HTML 版本，支持：

- Anki 风格复习
- 艾宾浩斯遗忘曲线对比
- 粘贴单词自动制卡
- 本地缓存 + Redis 双写同步
- 每晚 20:30 记忆快照
- 移动端 / 桌面端自适配

## 直接运行

直接打开 `index.html` 即可本地使用。

## 推荐 Redis

建议使用 **Upstash Redis REST**：

- 页面内填写 `Redis REST URL`
- 页面内填写 `Redis REST Token`
- 可自定义 `Redis Key`

## 部署方式

适合部署到：

- Vercel Static
- Netlify
- Cloudflare Pages
- GitHub Pages

## Vercel

仓库已包含 `vercel.json`，导入到 Vercel 后按静态站点部署即可。

## 注意事项

1. 页面打开时会自动尝试本地与 Redis 同步。
2. 新增、编辑、评分、删除前后会执行同步流程。
3. 20:30 快照在页面打开状态下准时记录；若当时页面未打开，会在下次打开后补记。
4. 由于 Redis Token 放在浏览器端，适合个人或小范围使用；公开多人环境建议增加 serverless 代理层。
5. 默认单词词典接口为 `https://api.dictionaryapi.dev/api/v2/entries/en/<word>`。
