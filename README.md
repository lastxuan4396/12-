# 12分钟和好 - Render Deploy

这是一个纯静态网页项目（单文件 `index.html`），用于部署到 Render。

## 已实现能力（核心）

- 双人协作房间（同浏览器多标签实时同步）
- 冲突强度分流（强度 >= 4 自动进入 60 秒降温）
- 步骤质量评分 + 低分改写建议 + 风险句替代建议
- 提醒系统（`.ics` 日历下载 + 浏览器提醒）
- 分享增强（文本卡片 + PNG 图卡 + PDF 导出）
- 数据复盘（7/30 天趋势、复发场景、优先优化步骤）
- 安全兜底（检测攻击/威胁/极端表达并触发降温或安全退出）
- 客户端错误监控（本地日志 + 可选 webhook 告警）

## 本地预览

直接打开 `index.html` 即可。

## 本地回归检查

```bash
node scripts/smoke-check.js
```

## 浏览器自动回归（已内置）

首次准备：

```bash
npm install
npx playwright install chromium
```

执行一键本地回归（含结构检查 + Playwright 自动点流程 + 本地部署校验）：

```bash
npm test
```

## 线上部署校验

```bash
./scripts/verify-deploy.sh
# 或指定 URL
./scripts/verify-deploy.sh https://repair-12min.onrender.com
```

## CI

仓库包含 GitHub Actions 工作流：

- `.github/workflows/ci.yml`
- 在 push / PR 时自动执行 `npm test`

## Render 部署

1. 将本目录推送到 GitHub 仓库。
2. 在 Render 里使用 Blueprint，读取 `render.yaml`。
3. 应用后会自动创建一个 Static Web Service。
