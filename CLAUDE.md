# CLAUDE.md

玄玄普拉提内容创作工具箱 - 基于 baoyu-skills 定制

## Architecture

单插件结构，暴露 `xuanxuan-skills` 插件，包含以下技能：

| 类别 | Skills |
|------|--------|
| 视觉生成 | xuanxuan-xhs-images, xuanxuan-cover-image, xuanxuan-infographic |
| 内容处理 | xuanxuan-format-markdown, xuanxuan-markdown-to-html, xuanxuan-translate |
| 素材工具 | xuanxuan-youtube-transcript, xuanxuan-compress-image |

## 玄玄定制

### 视觉风格

- **warm**: 温暖亲和，学员案例
- **notion**: 知性专业，知识科普
- **fresh**: 清新自然，健康生活

### 专属预设

- `pilates-knowledge`: 知识科普
- `pilates-tutorial`: 动作教程
- `pilates-story`: 学员案例
- `pilates-beginner`: 新手入门

## 与 pilates-skills 整合

```
pilates-create (策略)
    ↓
xuanxuan-xhs-images (视觉)
    ↓
xuanxuan-markdown-to-html (发布)
```

## Runtime

Bun/Node.js via `bun` or `npx -y bun`

## Based on

[baoyu-skills](https://github.com/JimLiu/baoyu-skills) by Jim Liu
