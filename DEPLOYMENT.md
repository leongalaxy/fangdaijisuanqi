# GitHub Pages 部署指南

本指南将帮助您将房贷计算器部署到 GitHub Pages。

## 前置条件

1. 拥有一个 GitHub 账号
2. 已安装 Git
3. 本地项目文件已准备完成

## 部署步骤

### 方法一：通过 GitHub 网页界面部署（推荐新手）

1. **创建新仓库**
   - 访问 https://github.com/new
   - 仓库名称：例如 `fangdai-calculator`
   - 选择 Public 或 Private（Public 可以免费使用 GitHub Pages）
   - 不要勾选 "Initialize this repository with a README"
   - 点击 "Create repository"

2. **上传文件**
   - 在新创建的仓库页面，点击 "uploading an existing file"
   - 将以下文件拖拽到上传区域：
     - `index.html`
     - `favicon.svg`
     - `logo.svg`
     - `README.md`
     - `LICENSE`
   - 在 "Commit changes" 输入框中填写提交信息，例如："Initial commit"
   - 点击 "Commit changes"

3. **启用 GitHub Pages**
   - 进入仓库的 "Settings" 页面
   - 在左侧菜单中找到 "Pages"
   - 在 "Build and deployment" 下，找到 "Source"
   - 选择 "Deploy from a branch"
   - 在 "Branch" 下拉菜单中选择 `main` 分支
   - 点击 "Save"

4. **等待部署完成**
   - 几分钟后，GitHub Pages 会自动部署您的网站
   - 部署完成后，您会在 Pages 页面看到您的网站链接
   - 格式通常是：`https://yourusername.github.io/fangdai-calculator/`

### 方法二：通过 Git 命令行部署（推荐有 Git 经验的用户）

1. **初始化 Git 仓库**
   ```bash
   cd c:\Users\72918\Documents\trae_projects\fangdai
   git init
   ```

2. **添加文件到暂存区**
   ```bash
   git add .
   ```

3. **提交更改**
   ```bash
   git commit -m "Initial commit: 房贷计算器 v1.0.0"
   ```

4. **关联远程仓库**
   ```bash
   git remote add origin https://github.com/yourusername/fangdai-calculator.git
   ```
   （将 `yourusername` 替换为您的 GitHub 用户名，`fangdai-calculator` 替换为您的仓库名）

5. **推送到 GitHub**
   ```bash
   git branch -M main
   git push -u origin main
   ```

6. **启用 GitHub Pages**
   - 访问您的 GitHub 仓库
   - 进入 "Settings" > "Pages"
   - 在 "Source" 下选择 "Deploy from a branch"
   - 选择 `main` 分支，点击 "Save"

7. **访问您的网站**
   - 等待几分钟后，访问：`https://yourusername.github.io/fangdai-calculator/`

## 自定义域名（可选）

如果您想使用自己的域名：

1. 在 GitHub 仓库的 Settings > Pages 中
2. 在 "Custom domain" 中输入您的域名
3. 在您的域名 DNS 设置中添加 CNAME 记录：
   - 主机记录：`www`（或留空）
   - 记录值：`yourusername.github.io`

## 更新网站

当您需要更新网站时：

1. 修改本地文件
2. 提交更改：
   ```bash
   git add .
   git commit -m "Update: 描述您的更改"
   git push
   ```
3. GitHub Pages 会自动重新部署

## 常见问题

### Q: 部署后网站显示 404 错误
A: 请检查：
- 文件是否正确上传
- GitHub Pages 是否已启用
- 仓库名称是否正确

### Q: 更改后网站没有更新
A: GitHub Pages 部署需要几分钟时间，请耐心等待。您可以在仓库的 "Actions" 标签页查看部署状态。

### Q: 如何查看部署日志
A: 访问仓库的 "Actions" 标签页，可以查看部署的详细日志。

### Q: 可以使用自定义域名吗
A: 可以，按照上面的"自定义域名"步骤操作即可。

## 技术支持

如果遇到问题，请：
1. 查看 GitHub Pages 官方文档：https://docs.github.com/en/pages
2. 在本项目的 Issues 中提问

## 注意事项

- GitHub Pages 是免费的，但有一些限制：
  - 每月有 100GB 的带宽限制
  - 每小时有 10 次构建限制
  - 不支持服务器端代码（本项目是纯静态网站，不受影响）

- 确保您的 `index.html` 文件在仓库根目录
- 文件名必须是小写的 `index.html`
