# Xingqi Pan · Minimal Academic Website

为 `anniepan-pumch.github.io` 制作的完整静态学术主页。英文页面，中文维护说明。简洁单栏排版，白色、灰色与深蓝色配色，适配手机与桌面；无需安装依赖、无需构建、无需 API 密钥。

## 文件结构

```text
anniepan-pumch.github.io/
├── index.html          # 页面文字、项目链接、所有内容板块
├── style.css           # 响应式布局、配色、打印样式
├── script.js           # 手机菜单、当前章节提示、年份
├── .nojekyll           # 以普通静态文件发布
├── assets/
│   └── README.md       # 照片、CV 等素材放置说明
└── README.md           # 本说明
```

## 预览

直接双击 `index.html` 即可查看。需要本地服务时，在此文件所在目录运行：

```sh
python3 -m http.server 8000
```

浏览器打开 `http://localhost:8000`。页面不依赖外部字体、图片或脚本，无网络时也能显示；GitHub 链接需要网络。

## 部署到 GitHub Pages（网页操作）

1. 登录 GitHub 账号 `anniepan-pumch`。
2. 创建名称完全一致的公开仓库：`anniepan-pumch.github.io`。如果已经存在，先检查现有内容，再决定是否覆盖。
3. 解压项目，将文件夹**内部所有内容**上传到仓库根目录，确保 `index.html` 位于根目录，不是嵌套在另一个文件夹里。不要只上传 zip。
4. 提交到 `main` 分支。`.nojekyll` 是隐藏文件；若网页上传没有包含它，可在仓库中使用 **Add file → Create new file** 创建名为 `.nojekyll` 的空文件。
5. 进入 **Settings → Pages → Build and deployment**。
6. **Source** 选择 **Deploy from a branch**；**Branch** 选择 `main`，文件夹选择 **/ (root)**，点击 **Save**。
7. 等待发布完成，查看 Pages 设置页提示的站点地址。GitHub 文档说明发布可能需要最多约 10 分钟。
8. 访问 **https://anniepan-pumch.github.io/**。后续提交更改后，GitHub Pages 会重新发布。

不需要 Jekyll 主题、`_config.yml`、npm 或额外的 GitHub Actions 工作流。

官方说明：https://docs.github.com/en/pages/quickstart

## 发布前补充内容

当前页面可以直接发布，但以下内容是明确标注的待补充状态：

| 内容 | 编辑位置 | 操作 |
| --- | --- | --- |
| 论文 | `index.html` 的 `id="publications"` | 替换占位框；只填写核实过的论文题名、作者、期刊、年份、DOI。已提供注释模板。 |
| 教育经历 | `id="education"` | 当前博士学习信息已填写；补充真实起止年份、学位及之前经历。 |
| CV | `id="cv"` | 放入 `assets/cv.pdf`，按该处注释替换状态文字为下载链接，并修改提示文字。 |
| 邮箱 | `id="contact"` | 将待补充文字替换为真实公开学术邮箱的 `mailto:` 链接。 |
| 个人照片（可选） | `assets/README.md` | 页面当前使用文字研究概览；如需照片，按素材说明添加。 |

未虚构具体论文、导师、获奖、学位年份、联系邮箱或 CV 文件。当前身份按用户要求采用 “PhD Candidate in Neurology”。

### 添加 CV 下载

上传真实 PDF 为 `assets/cv.pdf`。在 CV 区块将 `NOT YET AVAILABLE` 所在的 `<span>` 替换为：

```html
<a class="button primary" href="assets/cv.pdf" download="Xingqi-Pan-CV.pdf">Download CV (PDF)</a>
```

将 “A downloadable CV will be available here.” 改为例如 “Download my academic curriculum vitae.”。没有 PDF 时保留当前状态，不会出现失效下载按钮。

### 添加邮箱

将 “Academic email to be added.” 所在段落替换为以下结构，并将两处 `YOUR_CONFIRMED_EMAIL` 都改为真实地址：

```html
<a class="text-link" href="mailto:YOUR_CONFIRMED_EMAIL">YOUR_CONFIRMED_EMAIL</a>
```

### 更新论文

复制 HTML 注释中的 `publication` 结构，填入核实信息，并删除整个 `placeholder-panel` 占位框。不要将示例占位词作为真实论文发布。

### 修改外观

`style.css` 开头的 `:root` 定义了颜色。正文采用系统字体、标题采用 Georgia；无需加载第三方字体。布局断点为 650 像素。包含键盘焦点、跳过导航、手机菜单、减少动画设置和打印样式。禁用 JavaScript 时正文与导航仍可使用。

## 内容来源与边界

个人姓名、在北京协和医院攻读神经病学博士及研究方向来自用户提供的信息。项目链接与简短说明参考以下公开页面（2026-09-17 核对）：

- https://github.com/anniepan-pumch
- https://github.com/anniepan-pumch/brain-ALPS
- https://github.com/anniepan-pumch/TBSS-ICAS
- https://github.com/anniepan-pumch/Multicenter-MRIs
- https://github.com/anniepan-pumch/Useful-brain-analysis-tools

研究方向段落用于概括兴趣，不代表已经取得特定成果。站点未使用医院徽标、虚构照片或未提供的临床数据。

## 常见问题

- **404**：确认仓库名称、根目录的 `index.html`、Pages 的分支与文件夹；查看仓库 Actions 或 Pages 发布状态。
- **更新后仍是旧页面**：等待发布完成后刷新或清除浏览器缓存。
- **样式没有加载**：检查 `style.css` 和 `script.js` 与 `index.html` 同级，文件名大小写一致。
- **更换域名或账号**：同时更新 `index.html` 的 canonical 和 `og:url` 以及 GitHub 链接。

本交付包含站点文件，不代表已经创建 GitHub 仓库或完成线上发布。
