# 12分钟和好 - Render Deploy

这是一个纯静态网页项目（单文件 `index.html`），用于部署到 Render。

## 本地预览

直接打开 `index.html` 即可。

## 本地回归检查

```bash
node scripts/smoke-check.js
```

## 线上部署校验

```bash
./scripts/verify-deploy.sh
# 或指定 URL
./scripts/verify-deploy.sh https://repair-12min.onrender.com
```

## Render 部署

1. 将本目录推送到 GitHub 仓库。
2. 在 Render 里使用 Blueprint，读取 `render.yaml`。
3. 应用后会自动创建一个 Static Web Service。
