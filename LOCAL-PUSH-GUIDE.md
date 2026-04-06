# 本地推送指南

## 仓库状态

- ✅ GitHub 仓库已创建: https://github.com/xxetc/xuanxuan-skills
- ✅ 本地代码已提交
- ❌ 网络问题导致自动推送失败

## 手动推送步骤

当网络恢复后，执行：

```bash
cd ~/xuanxuan-skills
git push -u origin main
```

或者如果推送失败，尝试：

```bash
cd ~/xuanxuan-skills
git push --force -u origin main
```

## 验证推送

```bash
# 检查远程仓库
git remote -v

# 检查推送状态
git status

# 查看 GitHub 页面
open https://github.com/xxetc/xuanxuan-skills
```

## 安装测试

推送成功后，测试安装：

```bash
# 方式1: npx
npx skills add xxetc/xuanxuan-skills

# 方式2: OpenClaw
/plugin marketplace add xxetc/xuanxuan-skills
/plugin install xuanxuan-skills@xuanxuan-skills
```
