# 课程通知转待办助手

[![Star](https://img.shields.io/github/stars/Dr1zzy12/notice-to-todo?style=flat-square&label=star&color=f5b301)](https://github.com/Dr1zzy12/notice-to-todo/stargazers)
[![GitHub Pages](https://img.shields.io/badge/demo-online-brightgreen?style=flat-square&logo=github)](https://dr1zzy12.github.io/notice-to-todo/)
[![Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen?style=flat-square)](package.json)
[![Single File](https://img.shields.io/badge/build-single%20html-blue?style=flat-square)](#技术实现)

把一段杂乱的课程/会议通知文本，解析成结构化的待办清单。纯前端单文件应用，打开即用，不装不注册。

**在线试用 → https://dr1zzy12.github.io/notice-to-todo/**

课程群、班级群里那种一大段混着时间地点报名方式的通知，复制粘贴进去，直接出清单。

## 功能

- **粘贴即解析**：课程名、日期时间、地点、截止时间自动抽取
- **原文依据对照**：每条待办可展开查看它来自原文哪一句，减少误判
- **规则引擎兜底**：AI 解析不确定时可一键切回规则引擎
- **导出 .ics**：生成日历文件，可分享 / 下载 / 复制内容，一键进系统日历
- **备份与导入**：全部待办导出为 JSON，换设备或清缓存前先备份
- **撤销与恢复**：误删、误清空可恢复上一次状态
- **可选接入 AI 智能体**：填写自己的 API 配置后启用更强的语义解析，不填也能用

## 快速开始

**在线用**：直接打开 https://dr1zzy12.github.io/notice-to-todo/

**本地用**：

```bash
git clone https://github.com/Dr1zzy12/notice-to-todo.git
cd notice-to-todo
# 方式一：双击 index.html
# 方式二：起个静态服务器（推荐，避免部分浏览器对本地文件的限制）
python -m http.server 8000
```

## 技术实现

- **零依赖**：单个 `index.html`，无 CDN、无框架、无构建步骤、无 npm install
- **数据本地化**：所有待办存在浏览器 `localStorage`，不上传任何服务器
- **双解析引擎**：内置规则引擎（正则 + 时间语义推断）兜底，可选叠加 LLM 语义解析
- **移动端适配**：针对微信内置浏览器处理了号码自动识别、长按菜单、分享面板等行为差异

## 隐私

- 页面本身**不发任何网络请求**（除非你主动配置 AI 接口）
- 待办数据只在你自己的浏览器里，换设备请用「备份」导出 JSON
- 通知文本常含手机号，页面已关闭 iOS 自动识别电话/邮箱的行为

## 部署

纯静态页面，托管在 GitHub Pages：

1. Settings → Pages
2. Source 选 `Deploy from a branch`
3. Branch 选 `main`，目录选 `/ (root)`
4. 保存后访问 `https://dr1zzy12.github.io/notice-to-todo/`

入口文件必须是 `index.html`。仓库已放 `.nojekyll` 跳过 Jekyll 处理。

## 更新版本

```bash
cp 新版本.html index.html
git add -A
git commit -m "chore: 升级到 Vx.y.z"
git push
```

约 30 秒后线上自动生效。

## 版本

当前版本：**V1.30.6**（原型）

## 贡献

欢迎提 Issue 反馈解析不准的通知样例（**请先把手机号、姓名等个人信息打码**），或直接 PR 改进规则引擎。

如果这东西帮你省了事，点个 ⭐ Star 就是最好的支持。

## License

未指定。
