# 📔 极简日记本

一个完全跑在浏览器里的极简日记本：随手记录 → AI 总结 → 复盘 → 待办。

- 纯前端，单文件 `index.html`，不依赖任何后端
- 数据存浏览器 `localStorage`，隐私 100% 在你这边
- 支持 PWA：iOS / Android 都可以「添加到主屏幕」当原生 App 用
- 可选接入 OpenAI 兼容的 API（GPT-4o / DeepSeek / Moonshot / Claude 中转…），没填也能用本地规则版

---

## 🚀 三种使用方式

### 方式 1：本地直接打开（最简单）

双击 `index.html` 即可使用。
⚠️ 注意：直接双击 `file://` 打开 PWA 离线缓存会失效（浏览器安全限制），但核心功能完全可用。

### 方式 2：部署到 GitHub Pages（推荐，能放桌面）

1. 在 GitHub 新建一个仓库，比如 `daily-journal`
2. 把这个目录里所有文件上传到根目录
3. 进入仓库 **Settings → Pages → Source** 选 `Deploy from a branch` → 选 `main` / `(root)`
4. 等 1-2 分钟，会得到一个网址：`https://你的用户名.github.io/daily-journal/`
5. 手机浏览器打开这个网址 → 浏览器菜单 → **添加到主屏幕** → 完成，桌面上就有图标了

### 方式 3：部署到 CloudStudio / Vercel / Netlify

把整个目录拖上去就行，都能直接生成 https 链接。

### 方式 4：本地起个静态服务（开发用）

```bash
# 在本目录执行
python3 -m http.server 8080
# 然后浏览器打开 http://localhost:8080
```

---

## ✨ 功能

| 模块 | 干什么 |
|---|---|
| 🏠 **首页** | 展示今日日期 + 统计卡片（今日记录 / 待办 / 连续天数） |
| ✏️ **记录** | 自由记录每天发生的事，可加标签（工作 / 学习 / 生活 / 情绪 / 想法 / 会议） |
| ✨ **总结** | 一键生成「今日要点」+「复盘」按点列出（4 种颜色、6 种图标） |
| ✅ **待办** | 添加 / 勾选 / 编辑 / 标记重要 |
| ⚙️ **设置** | 配置 AI / 导出导入数据 / 清空 |

---

## 🤖 接入 AI（可选）

1. 进入 **设置** 页面
2. 填入：
   - **API Base URL**：例如
     - OpenAI：`https://api.openai.com/v1`
     - DeepSeek：`https://api.deepseek.com/v1`
     - Moonshot（月之暗面）：`https://api.moonshot.cn/v1`
     - 任意兼容 OpenAI Chat Completion 协议的中转服务
   - **API Key**：你的 sk-xxx
   - **模型**：例如 `gpt-4o-mini` / `deepseek-chat` / `moonshot-v1-8k`
3. 保存后回到 **总结** 页，点「生成今日总结 + 复盘」

> 没填也能用 — 走本地规则引擎（基于关键词分类），效果够用、完全离线。

---

## 💾 数据 & 隐私

- 所有数据 **只存在你的浏览器 localStorage**，没有任何后端
- 设置里可以一键 **导出 JSON 备份** / **导入恢复**
- 建议定期导出备份；换浏览器或清缓存不会丢

---

## 🛠 文件结构

```
daily-journal/
├── index.html              # 主应用（HTML + CSS + JS 全在这里）
├── manifest.webmanifest    # PWA 配置
├── sw.js                   # Service Worker（离线缓存）
├── icon.svg                # 应用图标（矢量）
├── icon-192.png            # PWA 192 图标
├── icon-512.png            # PWA 512 图标
└── README.md               # 本文件
```

---

## 🎨 风格来源

参考了「日记本」App 的极简黑白风格，自己微调成更适合每日复盘的信息密度。

---

## 📜 License

MIT — 随便用。
