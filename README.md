# GitHub Actions + Colab 测试

## 📁 文件说明

- `test_simple.ipynb` - 测试用 Colab Notebook
- `.github/workflows/run_colab.yml` - GitHub Actions 配置文件

## ⚙️ 配置步骤

### 步骤 1: 创建 GitHub 仓库

```bash
# 在你的 GitHub 账号下创建一个新仓库
# 例如：colab-test
```

### 步骤 2: 初始化 Git 仓库

```bash
cd /Users/xxb/.openclaw/workspace-bio/colab_test
git init
git add .
git commit -m "Initial commit: Colab test"
```

### 步骤 3: 配置 GitHub 远程

```bash
# 添加你的 GitHub 仓库作为 remote
git remote add origin https://github.com/YOUR_USERNAME/colab-test.git
```

### 步骤 4: 推送代码

```bash
git branch -M main
git push -u origin main
```

### 步骤 5: 配置 Google Cloud 凭证（如果需要访问 Drive）

1. 访问 https://console.cloud.google.com/
2. 创建新项目
3. 启用 Google Drive API
4. 创建服务账号
5. 下载 JSON 密钥文件
6. 在 GitHub 仓库的 Settings → Secrets and variables → Actions 中添加：
   - Name: `GOOGLE_APPLICATION_CREDENTIALS`
   - Value: JSON 密钥文件的内容

### 步骤 6: 触发执行

- **自动触发**: 推送代码到 main 分支
- **手动触发**: Actions → Run Colab Notebook → Run workflow

## 📊 查看结果

- **执行日志**: GitHub 仓库 → Actions → 查看运行日志
- **输出文件**: Actions → 下载 artifacts
- **Drive 结果**: Google Drive → /colab_test_results/test_result.txt

## ⚠️ 注意事项

1. 首次运行需要授权 Google Cloud 访问 Drive
2. Colab 免费额度限制：每次最长 12 小时
3. GitHub Actions 免费额度：每月 2,000 分钟
