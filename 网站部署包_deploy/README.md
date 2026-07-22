# 房昊成 作品集网站

个人作品集网站，已配置可直接部署到 GitHub Pages 或 Cloudflare Pages。

## 📁 文件结构

```
deploy/
├── index.html          # 主页面
├── 404.html            # SPA路由兜底页（index.html的副本）
├── _redirects          # Cloudflare Pages SPA路由规则
├── .gitignore
├── README.md           # 本文件
├── assets/
│   ├── index-DOZskezo.js   # React应用主JS
│   └── index-B58ziSA7.css  # 样式表
└── manus-storage/      # 所有图片资源（70个文件）
```

## 🚀 部署方法

### 方法一：Cloudflare Pages（推荐，免费+全球CDN）

#### 第1步：上传代码到 GitHub

1. 登录 GitHub（没有账号就注册一个）
2. 点击右上角 **+** → **New repository**
3. 填写仓库名称（如 `portfolio-website`），选择 **Public**，点击 **Create repository**
4. 在你的电脑上安装 [Git](https://git-scm.com/downloads)
5. 打开终端（Windows用Git Bash），执行以下命令：

```bash
# 进入deploy目录
cd "deploy文件夹的完整路径"

# 初始化git仓库
git init
git add .
git commit -m "初始提交：房昊成作品集网站"

# 把下面的 YOUR_USERNAME 和 YOUR_REPO 换成你的GitHub用户名和仓库名
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

#### 第2步：在 Cloudflare Pages 部署

1. 打开 [Cloudflare Pages](https://pages.cloudflare.com/)，点击 **Sign up**（免费注册）
2. 登录后点击 **Create a project** → **Connect to Git**
3. 授权 GitHub，选择你刚创建的仓库
4. 部署设置：
   - **Framework preset**: 选 `None`
   - **Build command**: 留空
   - **Build output directory**: 填 `/`（斜杠，表示根目录）
5. 点击 **Save and Deploy**
6. 等待1-2分钟，部署完成后会给你一个网址：
   `https://你的项目名.pages.dev`
7. **别人用这个网址就能访问你的网站了！**

#### 第3步（可选）：绑定自定义域名

在Cloudflare Pages项目设置 → Custom domains → 添加你自己的域名

---

### 方法二：GitHub Pages（备选方案）

1. 把代码上传到GitHub仓库（同方法一第1步）
2. 进入仓库 **Settings** → **Pages**
3. **Source** 选 `Deploy from a branch`
4. **Branch** 选 `main`，文件夹选 `/ (root)`
5. 点击 **Save**
6. 等待几分钟后访问：
   `https://YOUR_USERNAME.github.io/YOUR_REPO/`

⚠️ 注意：GitHub Pages 默认不支持SPA路由（作品详情页可能打不开），
已通过 `_redirects` 和 `404.html` 尽量兼容，但 Cloudflare Pages 效果更好。

---

## ✅ 网站功能

- 中英文双语切换（右上角 EN/中 按钮）
- 首页打字机动画效果
- 个人简介 + 实习经历 + 工具链展示
- 5个作品详情页（点击作品卡片进入）
- 联系方式展示
- 响应式设计（支持手机/平板/电脑）

## 📝 后续更新

如需修改内容，编辑 `assets/index-DOZskezo.js` 中的数据，
然后重新 push 到 GitHub，Cloudflare Pages 会自动重新部署。
