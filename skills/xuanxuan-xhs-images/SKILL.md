---
name: xuanxuan-xhs-images
description: 玄玄普拉提小红书图文生成器。基于 baoyu-skills 定制，专为普拉提内容优化。支持玄玄专属视觉风格（warm/notion/fresh），自动匹配普拉提内容类型。当用户说"生成小红书图片"、"做小红书配图"、"普拉提图文"、"内容可视化"时触发。
version: 1.0.0
metadata:
  openclaw:
    homepage: https://github.com/yourname/xuanxuan-skills#xuanxuan-xhs-images
    based_on: baoyu-skills by Jim Liu
---

# 玄玄小红书图文生成器

专为普拉提内容设计的小红书图文生成工具。基于 baoyu-skills 的强大功能，定制玄玄专属视觉风格。

## Usage

```bash
# Auto-select style and layout based on content
/xuanxuan-xhs-images posts/pilates/article.md

# Specify style (玄玄推荐：warm/notion/fresh)
/xuanxuan-xhs-images posts/pilates/article.md --style warm

# Specify layout
/xuanxuan-xhs-images posts/pilates/article.md --layout flow

# 玄玄专属预设
/xuanxuan-xhs-images posts/pilates/article.md --preset pilates-knowledge

# Direct content input
/xuanxuan-xhs-images
[paste content]

# Non-interactive (for scheduled tasks / automation)
/xuanxuan-xhs-images posts/pilates/article.md --yes
/xuanxuan-xhs-images posts/pilates/article.md --yes --preset pilates-knowledge
```

## Options

| Option | Description |
|--------|-------------|
| `--style <name>` | Visual style (see Style Gallery) |
| `--layout <name>` | Information layout (see Layout Gallery) |
| `--preset <name>` | Style + layout shorthand (see [Style Presets](references/style-presets.md)) |
| `--yes` | Non-interactive mode: skip all confirmations. Uses EXTEND.md preferences if found, otherwise uses defaults (no watermark, auto style/layout). Auto-confirms recommended plan (Path A). Suitable for scheduled tasks and automation. |

## 玄玄专属 Style × Layout 系统

| Dimension | Controls | 玄玄专属选项 |
|-----------|----------|-------------|
| **Style** | 视觉美学 | **warm** (温暖亲和)、**notion** (知性专业)、**fresh** (清新自然) |
| **Layout** | 信息结构 | sparse (留白)、balanced (平衡)、flow (流程)、list (清单) |

Style × Layout can be freely combined. Example: `--style notion --layout dense` creates an intellectual-looking knowledge card with high information density.

Or use presets: `--preset knowledge-card` → style + layout in one flag. See [Style Presets](references/style-presets.md).

## Style Gallery

| Style | Description |
|-------|-------------|
| `warm` (**玄玄默认**) | 温暖、亲和、专业。米色/浅棕/暖白色调，柔和线条，手绘感图标。适合普拉提生活分享、情感内容、初学者引导 |
| `notion` | 知性、专业、可信。黑白灰+单强调色，简洁几何线条，线性图标。适合普拉提知识科普、专业讲解、干货内容 |
| `fresh` | 清新、自然、健康。薄荷绿/天空蓝/白色，流畅有机线条，植物元素。适合健康生活、运动场景、自然主题 |

Detailed style definitions: `references/presets/<style>.md`

## 玄玄专属 Preset 画廊

Quick-start presets for Pilates content. Use `--preset <name>` or recommend during Step 2.

**普拉提知识科普**:

| Preset | Style | Layout | Best For |
|--------|-------|--------|----------|
| `pilates-knowledge` | notion | balanced | 普拉提知识卡、概念科普（核心/呼吸/体态） |
| `pilates-checklist` | notion | list | 训练清单、注意事项、必备动作 |
| `pilates-tutorial` | warm | flow | 动作分解、训练流程、步骤教程 |
| `pilates-concept` | notion | sparse | 核心概念、原理解释（核心稳定/脊柱中立） |

**普拉提生活分享**:

| Preset | Style | Layout | Best For |
|--------|-------|--------|----------|
| `pilates-story` | warm | balanced | 练习心得、身体变化故事、学员案例 |
| `pilates-lifestyle` | fresh | flow | 健康生活、日常练习、运动习惯 |
| `pilates-beginner` | warm | list | 新手入门、零基础指南、避坑提醒 |

**普拉提专业内容**:

| Preset | Style | Layout | Best For |
|--------|-------|--------|----------|
| `pilates-anatomy` | notion | dense | 解剖知识、肌肉说明、专业干货 |
| `pilates-compare` | fresh | comparison | 动作对比（正确vs错误）、普拉提vs瑜伽 |
| `pilates-warning` | warm | list | 常见误区、错误动作、避坑指南 |

Full preset definitions: [references/style-presets.md](references/style-presets.md)

## 玄玄视觉 DNA

基于 pilates-tacit 捕获的隐性知识，玄玄的视觉风格核心：

- **色调**: 温暖、亲和、专业（暖白/米色/浅棕）
- **线条**: 柔和、有机、流动感（呼应普拉提的流畅动作）
- **元素**: 清晰的身体线条、呼吸感、核心稳定感
- **情绪**: 专业但不冰冷，权威但不距离
- **字体**: 简洁现代，易读性强

## 普拉提内容自动匹配

| Content Signals | 玄玄推荐 Style | Layout | Preset |
|-----------------|---------------|--------|--------|
| 核心/呼吸/体态知识 | `notion` | balanced/dense | `pilates-knowledge` |
| 动作教程/分解步骤 | `warm` | flow | `pilates-tutorial` |
| 学员案例/变化故事 | `warm` | balanced | `pilates-story` |
| 新手入门/零基础 | `warm` | list | `pilates-beginner` |
| 健康生活/日常练习 | `fresh` | flow | `pilates-lifestyle` |
| 解剖/肌肉/专业干货 | `notion` | dense | `pilates-anatomy` |
| 动作对比/正误说明 | `fresh` | comparison | `pilates-compare` |
| 常见误区/避坑 | `warm` | list | `pilates-warning` |

## Layout Gallery

| Layout | Description |
|--------|-------------|
| `sparse` (Default) | Minimal information, maximum impact (1-2 points) |
| `balanced` | Standard content layout (3-4 points) |
| `dense` | High information density, knowledge card style (5-8 points) |
| `list` | Enumeration and ranking format (4-7 items) |
| `comparison` | Side-by-side contrast layout |
| `flow` | Process and timeline layout (3-6 steps) |
| `mindmap` | Center radial mind map layout (4-8 branches) |
| `quadrant` | Four-quadrant / circular section layout |

Detailed layout definitions: `references/elements/canvas.md`

## Auto Selection

| Content Signals | Style | Layout | Recommended Preset |
|-----------------|-------|--------|--------------------|
| Beauty, fashion, cute, girl, pink | `cute` | sparse/balanced | `cute-share`, `girly` |
| Health, nature, clean, fresh, organic | `fresh` | balanced/flow | `product-review`, `nature-flow` |
| Life, story, emotion, feeling, warm | `warm` | balanced | `cozy-story` |
| Warning, important, must, critical | `bold` | list/comparison | `warning`, `versus` |
| Professional, business, elegant, simple | `minimal` | sparse/balanced | `clean-quote`, `pro-summary` |
| Classic, vintage, old, traditional | `retro` | balanced | `throwback`, `retro-ranking` |
| Fun, exciting, wow, amazing | `pop` | sparse/list | `hype`, `pop-facts` |
| Knowledge, concept, productivity, SaaS | `notion` | dense/list | `knowledge-card`, `checklist` |
| Education, tutorial, learning, teaching, classroom | `chalkboard` | balanced/dense | `tutorial`, `classroom` |
| Notes, handwritten, study guide, knowledge, realistic, photo | `study-notes` | dense/list/mindmap | `study-guide` |
| Movie, album, concert, poster, opinion, editorial, dramatic, cinematic | `screen-print` | sparse/comparison | `poster`, `editorial`, `cinematic` |

## Outline Strategies

Three differentiated outline strategies for different content goals:

### Strategy A: Story-Driven (故事驱动型)

| Aspect | Description |
|--------|-------------|
| **Concept** | Personal experience as main thread, emotional resonance first |
| **Features** | Start from pain point, show before/after change, strong authenticity |
| **Best for** | Reviews, personal shares, transformation stories |
| **Structure** | Hook → Problem → Discovery → Experience → Conclusion |

### Strategy B: Information-Dense (信息密集型)

| Aspect | Description |
|--------|-------------|
| **Concept** | Value-first, efficient information delivery |
| **Features** | Clear structure, explicit points, professional credibility |
| **Best for** | Tutorials, comparisons, product reviews, checklists |
| **Structure** | Core conclusion → Info card → Pros/Cons → Recommendation |

### Strategy C: Visual-First (视觉优先型)

| Aspect | Description |
|--------|-------------|
| **Concept** | Visual impact as core, minimal text |
| **Features** | Large images, atmospheric, instant appeal |
| **Best for** | High-aesthetic products, lifestyle, mood-based content |
| **Structure** | Hero image → Detail shots → Lifestyle scene → CTA |

## File Structure

Each session creates an independent directory named by content slug:

```
xhs-images/{topic-slug}/
├── source-{slug}.{ext}             # Source files (text, images, etc.)
├── analysis.md                     # Deep analysis + questions asked
├── outline-strategy-a.md           # Strategy A: Story-driven
├── outline-strategy-b.md           # Strategy B: Information-dense
├── outline-strategy-c.md           # Strategy C: Visual-first
├── outline.md                      # Final selected/merged outline
├── prompts/
│   ├── 01-cover-[slug].md
│   ├── 02-content-[slug].md
│   └── ...
├── 01-cover-[slug].png
├── 02-content-[slug].png
└── NN-ending-[slug].png
```

**Slug Generation**:
1. Extract main topic from content (2-4 words, kebab-case)
2. Example: "AI工具推荐" → `ai-tools-recommend`

**Conflict Resolution**:
If `xhs-images/{topic-slug}/` already exists:
- Append timestamp: `{topic-slug}-YYYYMMDD-HHMMSS`
- Example: `ai-tools` exists → `ai-tools-20260118-143052`

**Source Files**:
Copy all sources with naming `source-{slug}.{ext}`:
- `source-article.md`, `source-photo.jpg`, etc.
- Multiple sources supported: text, images, files from conversation

## Workflow

### Progress Checklist

Copy and track progress:

```
XHS Infographic Progress:
- [ ] Step 0: Check preferences (EXTEND.md) ⛔ BLOCKING (--yes: use defaults if not found)
  - [ ] Found → load preferences → continue
  - [ ] Not found → run first-time setup → MUST complete before Step 1 (--yes: skip setup, use defaults)
- [ ] Step 1: Analyze content → analysis.md
- [ ] Step 2: Smart Confirm ⚠️ REQUIRED (--yes: auto-confirm Path A)
  - [ ] Path A: Quick confirm → generate recommended outline
  - [ ] Path B: Customize → adjust then generate outline
  - [ ] Path C: Detailed → 3 outlines → second confirm → generate outline
- [ ] Step 3: Generate images (sequential)
- [ ] Step 4: Completion report
```

### Flow

```
Input → [--yes?] ─┬─ Yes → [Step 0: Load or defaults] → Analyze → Auto-confirm → Generate → Complete
                   │
                   └─ No → [Step 0: Preferences] ─┬─ Found → Continue
                                                   │
                                                   └─ Not found → First-Time Setup ⛔ BLOCKING
                                                                  │
                                                                  └─ Complete setup → Save EXTEND.md → Continue
                                                                                                          │
                    ┌─────────────────────────────────────────────────────────────────────────────────────┘
                    ↓
            Analyze → [Smart Confirm] ─┬─ Quick: confirm recommended → outline.md → Generate → Complete
                                       │
                                       ├─ Customize: adjust options → outline.md → Generate → Complete
                                       │
                                       └─ Detailed: 3 outlines → [Confirm 2] → outline.md → Generate → Complete
```

### Step 0: Load Preferences (EXTEND.md) ⛔ BLOCKING

**Purpose**: Load user preferences or run first-time setup.

**`--yes` mode**: If EXTEND.md found → load it. If not found → use built-in defaults (no watermark, style/layout auto-select, language from content). Do NOT run first-time setup, do NOT create EXTEND.md, do NOT ask any questions. Proceed directly to Step 1.

**CRITICAL** (interactive mode only): If EXTEND.md not found, MUST complete first-time setup before ANY other questions or steps. Do NOT proceed to content analysis, do NOT ask about style, do NOT ask about layout — ONLY complete the preferences setup first.

Check EXTEND.md existence (priority order):

```bash
# macOS, Linux, WSL, Git Bash
test -f .xuanxuan-skills/xuanxuan-xhs-images/EXTEND.md && echo "project"
test -f "${XDG_CONFIG_HOME:-$HOME/.config}/xuanxuan-skills/xuanxuan-xhs-images/EXTEND.md" && echo "xdg"
test -f "$HOME/.xuanxuan-skills/xuanxuan-xhs-images/EXTEND.md" && echo "user"
```

```powershell
# PowerShell (Windows)
if (Test-Path .xuanxuan-skills/xuanxuan-xhs-images/EXTEND.md) { "project" }
$xdg = if ($env:XDG_CONFIG_HOME) { $env:XDG_CONFIG_HOME } else { "$HOME/.config" }
if (Test-Path "$xdg/xuanxuan-skills/xuanxuan-xhs-images/EXTEND.md") { "xdg" }
if (Test-Path "$HOME/.xuanxuan-skills/xuanxuan-xhs-images/EXTEND.md") { "user" }
```

┌────────────────────────────────────────────────────┬───────────────────┐
│                        Path                        │     Location      │
├────────────────────────────────────────────────────┼───────────────────┤
│ .xuanxuan-skills/xuanxuan-xhs-images/EXTEND.md           │ Project directory │
├────────────────────────────────────────────────────┼───────────────────┤
│ $HOME/.xuanxuan-skills/xuanxuan-xhs-images/EXTEND.md     │ User home         │
└────────────────────────────────────────────────────┴───────────────────┘

┌───────────┬─────────────────────────────────────────────────────────────────────────────────────────────────────┐
│  Result   │                                              Action                                              │
├───────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ Found     │ Read, parse, display summary → Continue to Step 1                                                 │
├───────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ Not found │ ⛔ BLOCKING: Run first-time setup ONLY (see below) → Complete and save EXTEND.md → Then Step 1    │
└───────────┴─────────────────────────────────────────────────────────────────────────────────────────────────────┘

**First-Time Setup** (when EXTEND.md not found):

**Language**: Use user's input language or saved language preference.

Use AskUserQuestion with ALL questions in ONE call. See `references/config/first-time-setup.md` for question details.

**EXTEND.md Supports**: Watermark | Preferred style/layout | Custom style definitions | Language preference

Schema: `references/config/preferences-schema.md`

### Step 1: Analyze Content → `analysis.md`

Read source content, save it if needed, and perform deep analysis.

**Actions**:
1. **Save source content** (if not already a file):
   - If user provides a file path: use as-is
   - If user pastes content: save to `source.md` in target directory
   - **Backup rule**: If `source.md` exists, rename to `source-backup-YYYYMMDD-HHMMSS.md`
2. Read source content
3. **Deep analysis** following `references/workflows/analysis-framework.md`:
   - Content type classification (种草/干货/测评/教程/避坑...)
   - Hook analysis (爆款标题潜力)
   - Target audience identification
   - Engagement potential (收藏/分享/评论)
   - Visual opportunity mapping
   - Swipe flow design
4. Detect source language
5. Determine recommended image count (2-10)
6. **Auto-recommend** best strategy + style + layout based on content signals
7. **Save to `analysis.md`**

### Step 2: Smart Confirm ⚠️

**Purpose**: Present auto-recommended plan, let user confirm or adjust.

**`--yes` mode**: Skip this entire step. Use auto-recommended strategy + style + layout from Step 1 analysis (or `--style`/`--layout`/`--preset` if provided). Generate outline directly using Path A logic → save to `outline.md` → proceed to Step 3. No AskUserQuestion calls.

**Interactive mode**: Do NOT skip.

**Auto-Recommendation Logic**:
1. Use Auto Selection table to match content signals → best strategy + style + layout
2. Infer optimal image count from content density
3. Load style's default elements from preset

**Display** (analysis summary + recommended plan):

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📋 内容分析
  主题：[topic] | 类型：[content_type]
  要点：[key points summary]
  受众：[target audience]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🎨 推荐方案（自动匹配）
  策略：[A/B/C] [strategy name]（[reason]）
  风格：[style] · 布局：[layout] · 预设：[preset]
  图片：[N]张（封面+[N-2]内容+结尾）
  元素：[background] / [decorations] / [emphasis]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Use AskUserQuestion** with single question:

| Option | Description |
|--------|-------------|
| 1. ✅ 确认，直接生成（推荐） | Trust auto-recommendation, proceed immediately |
| 2. 🎛️ 自定义调整 | Modify strategy/style/layout/count in one step |
| 3. 📋 详细模式 | Generate 3 outlines, then choose (two confirmations) |

#### Path A: Quick Confirm (Option 1)

Generate single outline using recommended strategy + style → save to `outline.md` → Step 3.

#### Path B: Customize (Option 2)

**Use AskUserQuestion** with adjustable options (leave blank = keep recommended):

1. **策略风格**: Current: [strategy + style]. Options: A Story-Driven(warm) | B Information-Dense(notion) | C Visual-First(screen-print). Or specify style directly: cute/fresh/warm/bold/minimal/retro/pop/notion/chalkboard/study-notes/screen-print. Or use preset: knowledge-card / checklist / tutorial / poster / cinematic / etc.
2. **布局**: Current: [layout]. Options: sparse | balanced | dense | list | comparison | flow | mindmap | quadrant
3. **图片数量**: Current: [N]. Range: 2-10
4. **补充说明**（可选）: Selling point emphasis, audience adjustment, color preference, etc.

**After response**: Generate single outline with user's choices → save to `outline.md` → Step 3.

#### Path C: Detailed Mode (Option 3)

Full two-confirmation flow for maximum control:

**Step 2a: Content Understanding**

**Use AskUserQuestion** for:
1. Core selling point (multiSelect: true)
2. Target audience
3. Style preference: Authentic sharing / Professional review / Aesthetic mood / Auto
4. Additional context (optional)

**After response**: Update `analysis.md`.

**Step 2b: Generate 3 Outline Variants**

| Strategy | Filename | Outline | Recommended Style |
|----------|----------|---------|-------------------|
| A | `outline-strategy-a.md` | Story-driven: emotional, before/after | warm, cute, fresh |
| B | `outline-strategy-b.md` | Information-dense: structured, factual | notion, minimal, chalkboard |
| C | `outline-strategy-c.md` | Visual-first: atmospheric, minimal text | bold, pop, retro, screen-print |

**Outline format** (YAML front matter + content):
```yaml
---
strategy: a  # a, b, or c
name: Story-Driven
style: warm  # recommended style for this strategy
style_reason: "Warm tones enhance emotional storytelling and personal connection"
elements:  # from style preset, can be customized
  background: solid-pastel
  decorations: [clouds, stars-sparkles]
  emphasis: star-burst
  typography: highlight
layout: balanced  # primary layout
image_count: 5
---

## P1 Cover
**Type**: cover
**Hook**: "入冬后脸不干了🥹终于找到对的面霜"
**Visual**: Product hero shot with cozy winter atmosphere
**Layout**: sparse

## P2 Problem
**Type**: pain-point
**Message**: Previous struggles with dry skin
**Visual**: Before state, relatable scenario
**Layout**: balanced

...
```

**Differentiation requirements**:
- Each strategy MUST have different outline structure AND different recommended style
- Adapt page count: A typically 4-6, B typically 3-5, C typically 3-4
- Include `style_reason` explaining why this style fits the strategy

Reference: `references/workflows/outline-template.md`

**Step 2c: Outline & Style Selection**

**Use AskUserQuestion** with three questions:

**Q1: Outline Strategy**: A / B / C / Combine (specify pages from each)

**Q2: Visual Style**: Use recommended | Select preset | Select style | Custom description

**Q3: Visual Elements**: Use defaults (Recommended) | Adjust background | Adjust decorations | Custom

**After response**: Save selected/merged outline to `outline.md` with confirmed style and elements → Step 3.

### Step 3: Generate Images

With confirmed outline + style + layout:

**Visual Consistency — Reference Image Chain**:
To ensure character/style consistency across all images in a series:
1. **Generate image 1 (cover) FIRST** — without `--ref`
2. **Use image 1 as `--ref` for ALL remaining images** (2, 3, ..., N)
   - This anchors the character design, color rendering, and illustration style
   - Command pattern: `--ref <path-to-image-01.png>` added to every subsequent generation

This is critical for styles that use recurring characters, mascots, or illustration elements. Image 1 becomes the visual anchor for the entire series.

**For each image (cover + content + ending)**:
1. Save prompt to `prompts/NN-{type}-[slug].md` (in user's preferred language)
   - **Backup rule**: If prompt file exists, rename to `prompts/NN-{type}-[slug]-backup-YYYYMMDD-HHMMSS.md`
2. Generate image:
   - **Image 1**: Generate without `--ref` (this establishes the visual anchor)
   - **Images 2+**: Generate with `--ref <image-01-path>` for consistency
   - **Backup rule**: If image file exists, rename to `NN-{type}-[slug]-backup-YYYYMMDD-HHMMSS.png`
3. Report progress after each generation

**Watermark Application** (if enabled in preferences):
Add to each image generation prompt:
```
Include a subtle watermark "[content]" positioned at [position].
The watermark should be legible but not distracting from the main content.
```
Reference: `references/config/watermark-guide.md`

**Image Generation Skill Selection**:
- Check available image generation skills
- If multiple skills available: ask user preference (interactive) or use first available skill (`--yes` mode)

**Session Management**:
If image generation skill supports `--sessionId`:
1. Generate unique session ID: `xhs-{topic-slug}-{timestamp}`
2. Use same session ID for all images
3. Combined with reference image chain, ensures maximum visual consistency

### Step 4: Completion Report

```
Xiaohongshu Infographic Series Complete!

Topic: [topic]
Mode: [Quick / Custom / Detailed]
Strategy: [A/B/C/Combined]
Style: [style name]
Layout: [layout name or "varies"]
Location: [directory path]
Images: N total

✓ analysis.md
✓ outline.md
✓ outline-strategy-a/b/c.md (detailed mode only)

Files:
- 01-cover-[slug].png ✓ Cover (sparse)
- 02-content-[slug].png ✓ Content (balanced)
- 03-content-[slug].png ✓ Content (dense)
- 04-ending-[slug].png ✓ Ending (sparse)
```

## Image Modification

| Action | Steps |
|--------|-------|
| **Edit** | **Update prompt file FIRST** → Regenerate with same session ID |
| **Add** | Specify position → Create prompt → Generate → Renumber subsequent files (NN+1) → Update outline |
| **Delete** | Remove files → Renumber subsequent (NN-1) → Update outline |

**IMPORTANT**: When updating images, ALWAYS update the prompt file (`prompts/NN-{type}-[slug].md`) FIRST before regenerating. This ensures changes are documented and reproducible.

## Content Breakdown Principles

1. **Cover (Image 1)**: Hook + visual impact → `sparse` layout
2. **Content (Middle)**: Core value per image → `balanced`/`dense`/`list`/`comparison`/`flow`
3. **Ending (Last)**: CTA / summary → `sparse` or `balanced`

**Style × Layout Matrix** (✓✓ = highly recommended, ✓ = works well):

| | sparse | balanced | dense | list | comparison | flow | mindmap | quadrant |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| cute | ✓✓ | ✓✓ | ✓ | ✓✓ | ✓ | ✓ | ✓ | ✓ |
| fresh | ✓✓ | ✓✓ | ✓ | ✓ | ✓ | ✓✓ | ✓ | ✓ |
| warm | ✓✓ | ✓✓ | ✓ | ✓ | ✓✓ | ✓ | ✓ | ✓ |
| bold | ✓✓ | ✓ | ✓ | ✓✓ | ✓✓ | ✓ | ✓ | ✓✓ |
| minimal | ✓✓ | ✓✓ | ✓✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| retro | ✓✓ | ✓✓ | ✓ | ✓✓ | ✓ | ✓ | ✓ | ✓ |
| pop | ✓✓ | ✓✓ | ✓ | ✓✓ | ✓✓ | ✓ | ✓ | ✓ |
| notion | ✓✓ | ✓✓ | ✓✓ | ✓✓ | ✓✓ | ✓✓ | ✓✓ | ✓✓ |
| chalkboard | ✓✓ | ✓✓ | ✓✓ | ✓✓ | ✓ | ✓✓ | ✓✓ | ✓ |
| study-notes | ✗ | ✓ | ✓✓ | ✓✓ | ✓ | ✓ | ✓✓ | ✓ |
| screen-print | ✓✓ | ✓✓ | ✗ | ✓ | ✓✓ | ✓ | ✗ | ✓✓ |

## References

Detailed templates in `references/` directory:

**Elements** (Visual building blocks):
- `elements/canvas.md` - Aspect ratios, safe zones, grid layouts
- `elements/image-effects.md` - Cutout, stroke, filters
- `elements/typography.md` - Decorated text (花字), tags, text direction
- `elements/decorations.md` - Emphasis marks, backgrounds, doodles, frames

**Presets** (Style presets):
- `presets/<name>.md` - Element combination definitions (cute, notion, warm...)
- `style-presets.md` - Preset shortcuts (style + layout combos)

**Workflows** (Process guides):
- `workflows/analysis-framework.md` - Content analysis framework
- `workflows/outline-template.md` - Outline template with layout guide
- `workflows/prompt-assembly.md` - Prompt assembly guide

**Config** (Settings):
- `config/preferences-schema.md` - EXTEND.md schema
- `config/first-time-setup.md` - First-time setup flow
- `config/watermark-guide.md` - Watermark configuration

## Notes

- Auto-retry once on failure | Cartoon alternatives for sensitive figures
- Use confirmed language preference | Maintain style consistency
- **Smart Confirm required** (Step 2) - do not skip; detailed mode uses two sub-confirmations

## Extension Support

Custom configurations via EXTEND.md. See **Step 0** for paths and supported options.
