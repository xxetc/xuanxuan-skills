# xuanxuan-skills

玄玄普拉提内容创作工具箱 - 基于 [baoyu-skills](https://github.com/JimLiu/baoyu-skills) 定制

## 安装

### 通用安装（Codex / Claude Code / skills CLI）

```bash
npx skills add xxetc/xuanxuan-skills
```

### Hermes

如果你希望 Hermes 在后续会话里也能自动发现并按需调用这些 skills，安装后再执行：

```bash
python3 ~/.hermes/scripts/refresh_skill_snapshot.py
```

如果你已经安装了我提供的包装命令，也可以直接：

```bash
hermes-skills-add xxetc/xuanxuan-skills
```

### Claude Code
```
/plugin marketplace add xxetc/xuanxuan-skills
/plugin install xuanxuan-skills@xuanxuan-skills
```

## 可用 Skills

### 视觉生成

| Skill | 功能 | 使用场景 |
|-------|------|----------|
| `xuanxuan-xhs-images` | 小红书图文生成 | 普拉提知识科普、动作教程 |
| `xuanxuan-cover-image` | 封面图生成 | 公众号、视频号封面 |
| `xuanxuan-infographic` | 信息图生成 | 专业内容可视化 |

### 内容处理

| Skill | 功能 | 使用场景 |
|-------|------|----------|
| `xuanxuan-format-markdown` | Markdown 格式化 | 文章排版标准化 |
| `xuanxuan-markdown-to-html` | 转 HTML | 公众号发布 |
| `xuanxuan-translate` | 翻译 | 外文内容搬运 |
| `xuanxuan-youtube-transcript` | YouTube 字幕下载 | 外文学习素材 |
| `xuanxuan-compress-image` | 图片压缩 | 发布前优化 |

## 玄玄专属特性

### 1. 普拉提内容优化

小红书图文生成器针对普拉提内容优化：

- **warm 风格**: 温暖亲和，适合学员案例、练习心得
- **notion 风格**: 知性专业，适合知识科普、解剖干货
- **fresh 风格**: 清新自然，适合健康生活、日常练习

### 2. 专属预设

```bash
# 知识科普
/xuanxuan-xhs-images article.md --preset pilates-knowledge

# 动作教程
/xuanxuan-xhs-images article.md --preset pilates-tutorial

# 学员案例
/xuanxuan-xhs-images article.md --preset pilates-story

# 新手入门
/xuanxuan-xhs-images article.md --preset pilates-beginner
```

### 3. 与 pilates-skills 整合

```
pilates-create (策略层)
    ↓
xuanxuan-xhs-images (视觉层)
    ↓
xuanxuan-markdown-to-html (发布层)
```

完整工作流：
1. `/pilates-create` - 内容策略与诊断
2. `/xuanxuan-xhs-images` - 生成配图
3. `/xuanxuan-markdown-to-html` - 排版发布

## 基于 baoyu-skills

本项目基于 [baoyu-skills](https://github.com/JimLiu/baoyu-skills) 修改，保留其核心架构：

- Bun/Node.js 运行时
- TypeScript 脚本
- 图像生成 API 支持

主要定制：
- 视觉风格调整为普拉提/健康领域
- 预设配置玄玄专属
- 移除不相关的技能（漫画、幻灯片等）

## 配置

### API Keys

在 `~/.xuanxuan-skills/.env` 中配置：

```bash
# OpenAI (图像生成)
OPENAI_API_KEY=sk-xxx

# 其他可选
AZURE_OPENAI_API_KEY=xxx
GOOGLE_API_KEY=xxx
```

## License

MIT-0 (保留 baoyu-skills 原许可证)
