# 上传到 GitHub 指南

> 本文档告诉您如何把这个 skill 作为新项目上传到您的 GitHub。**部署完成后可以删除此文件**。

## 前置准备

确认您已经：
- [ ] 拥有 GitHub 账号
- [ ] 本地安装了 Git（检查命令：`git --version`）
- [ ] 配置了 Git 用户名和邮箱：
  ```bash
  git config --global user.name "您的用户名"
  git config --global user.email "您的邮箱"
  ```

## 方法一：通过 GitHub 网页上传（最简单）

### 步骤 1：创建新仓库
1. 登录 [github.com](https://github.com)
2. 右上角 `+` → `New repository`
3. 填写信息：
   - **Repository name**：`youdie-caishui-skill`（建议保持一致）
   - **Description**：`友蝶财税业务专用 Claude Skill —— 品牌知识库、服务口径、文案规范一键调用`
   - **Public**（公开）
   - ❌ 不要勾选 "Add a README"（我们已经有了）
   - ❌ 不要勾选 "Add .gitignore"（我们已经有了）
   - ❌ 不要勾选 "Choose a license"（我们已经有了）
4. 点击 `Create repository`

### 步骤 2：上传文件
1. 在新建的空仓库页面，点击 `uploading an existing file`
2. 把本 skill 目录下的**所有文件和子目录**拖进去
3. 提交信息写：`feat: 初始化友蝶财税 skill v1.0.0`
4. 点击 `Commit changes`

### 步骤 3：完成
上传完毕后，您的 skill 就在 `https://github.com/您的用户名/youdie-caishui-skill` 了。

---

## 方法二：通过命令行上传（推荐，更规范）

### 步骤 1：在 GitHub 创建空仓库
同方法一的步骤 1。

### 步骤 2：在本地初始化并推送

打开终端，进入本 skill 的根目录：

```bash
cd /path/to/youdie-caishui-skill

# 1. 初始化 git 仓库
git init

# 2. 添加所有文件
git add .

# 3. 首次提交
git commit -m "feat: 初始化友蝶财税 skill v1.0.0

- 包含完整的品牌档案、24 项服务清单、资质荣誉
- 提供品牌调性、文案规范、客户 FAQ
- 提供介绍 PPT、朋友圈文案、合作提案三大模板"

# 4. 绑定远程仓库（替换为您的仓库地址）
git remote add origin https://github.com/您的用户名/youdie-caishui-skill.git

# 5. 重命名主分支为 main（符合现代 GitHub 规范）
git branch -M main

# 6. 推送到 GitHub
git push -u origin main
```

### 步骤 3：验证上传成功
刷新 GitHub 仓库页面，应该能看到所有文件。

---

## 方法三：通过 GitHub CLI（极客选择）

如果您安装了 `gh` 命令行工具：

```bash
cd /path/to/youdie-caishui-skill

git init
git add .
git commit -m "feat: 初始化友蝶财税 skill v1.0.0"

# 一条命令创建仓库并推送（公开）
gh repo create youdie-caishui-skill \
  --public \
  --description "友蝶财税业务专用 Claude Skill" \
  --source=. \
  --push
```

---

## 上传后建议做的事

### 1. 添加 Topics（标签）
在仓库页面右侧齿轮图标设置：
- `claude`
- `claude-skill`
- `ai-agent`
- `chinese`
- `finance`
- `tax`
- `business-automation`

### 2. 设置仓库描述和链接
在 About 区域：
- 描述：`友蝶财税业务专用 Claude Skill - 品牌知识库、服务口径、文案规范`
- 网站：`https://www.kmudee.com`

### 3. 固定到 Profile
如果这是您想展示的项目，可以在您的 GitHub 首页 `Customize your pins` 中固定它。

### 4. 创建第一个 Release
```bash
git tag -a v1.0.0 -m "首个稳定版本"
git push origin v1.0.0
```
然后在 GitHub 的 Releases 页面编辑这个 tag，写上变更日志。

---

## 常见问题

### Q: 推送时提示"权限拒绝"怎么办？
A: 需要配置 SSH key 或 Personal Access Token。简单做法：
- 用 HTTPS 地址，首次推送时会弹出登录窗口
- 或生成 Personal Access Token：GitHub → Settings → Developer settings → Personal access tokens

### Q: 我修改了 skill 内容，怎么同步到 GitHub？
A: 按标准 git 流程：
```bash
git add .
git commit -m "docs: 更新某某内容"
git push
```

### Q: 别人怎么使用这个 skill？
A: 让他们：
```bash
git clone https://github.com/您的用户名/youdie-caishui-skill.git
```
然后按照仓库 README 中的"安装与使用"章节操作。

### Q: 想让 skill 在 Claude 中生效，还需要做什么？
A: 取决于您使用的 Claude 产品：
- **Claude Code**：把 skill 目录放到 `~/.claude/skills/` 下
- **Cowork**：上传到工作空间的 skills 目录
- **Claude.ai**：可以作为 Project 的知识文件上传，或把 SKILL.md 作为 Custom Instructions

---

## 部署完成后

可以删除本文件（GITHUB_DEPLOY.md），它只是部署指引，不属于 skill 本身：

```bash
rm GITHUB_DEPLOY.md
git add .
git commit -m "chore: 清理部署文档"
git push
```
