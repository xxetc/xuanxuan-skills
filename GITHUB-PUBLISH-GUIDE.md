# xuanxuan-skills 发布指南

## 发布步骤

### 1. 创建 GitHub 仓库

**选项 A: 公共仓库（推荐，开源共享）**
```bash
cd ~/xuanxuan-skills
gh repo create xuanxuan-skills --public \
  --description "玄玄普拉提内容创作工具箱 - 基于 baoyu-skills 定制"
```

**选项 B: 私有仓库（仅自己使用）**
```bash
cd ~/xuanxuan-skills
gh repo create xuanxuan-skills --private \
  --description "玄玄普拉提内容创作工具箱"
```

### 2. 推送代码

```bash
cd ~/xuanxuan-skills
git remote add origin https://github.com/YOUR_USERNAME/xuanxuan-skills.git
git branch -M main
git push -u origin main
```

### 3. 验证发布

```bash
# 检查远程仓库
git remote -v

# 检查推送状态
git status
```

## 安装方式

### 方式1: 通过 npx 安装

```bash
npx skills add YOUR_USERNAME/xuanxuan-skills
```

### 方式2: 通过 OpenClaw 插件市场

在 Claude Code 中：
```
/plugin marketplace add YOUR_USERNAME/xuanxuan-skills
/plugin install xuanxuan-skills@xuanxuan-skills
```

### 方式3: 本地路径安装（开发调试）

```bash
# 在 ~/.claude/settings.json 中添加
{
  "extraKnownMarketplaces": {
    "xuanxuan-local": {
      "source": "directory",
      "path": "/Users/zhangxuanxuan/xuanxuan-skills"
    }
  }
}
```

## 更新版本

```bash
# 修改版本号
vim .claude-plugin/marketplace.json

# 提交并推送
git add .
git commit -m "Bump version to 1.0.1"
git push
```

## 文件清单

已准备好的文件：
- ✅ `.claude-plugin/marketplace.json` - 插件配置
- ✅ `README.md` - 项目说明
- ✅ `CLAUDE.md` - Claude Code 配置说明
- ✅ `skills/xuanxuan-*/SKILL.md` - 8个技能
- ✅ Git 仓库已初始化

## 下一步

发布完成后：
1. 更新 Napo/Sabre 配置中的 homepage 链接
2. 测试安装流程
3. 创建第一个测试案例
