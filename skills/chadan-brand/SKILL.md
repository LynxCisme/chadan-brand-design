---
name: chadan-brand
description: |
  茶蛋品牌设计规范 skill。只要用户要制作茶蛋品牌相关的任何视觉或文档物料，就必须启用此 skill，包括但不限于：
  - 制作茶蛋 PPT / 幻灯片 / 演示文稿
  - 制作茶蛋 PDF 文档 / 报告
  - 制作茶蛋 HTML 页面 / 网页 / 落地页
  - 制作茶蛋 Word 文档 / 方案
  - 制作茶蛋海报、社交卡片、视觉物料
  - 任何提到「茶蛋」「ChaDan」「ChaDan Land」并需要输出视觉内容的场景
  触发关键词：茶蛋、ChaDan、ChaDan Land、茶蛋品牌、茶蛋风格、按茶蛋规范、用品牌色
---

# 茶蛋 ChaDan Land 品牌规范

你正在为茶蛋品牌制作物料。请严格遵循以下规范，确保每一份输出都体现品牌一致性。

## 随包资源（必须优先使用）

本 Skill 是可移植包。字体、Logo 和辅助图形都位于此 Skill 文件夹内的 `assets/` 目录；先定位本 `SKILL.md` 所在文件夹，再使用下面的相对路径。不得从网络下载、生成、重绘或替换 Logo。

```
assets/
├── fonts/
│   ├── ChillOrganic_Regular.otf
│   ├── ChillOrganic_Medium.otf
│   ├── SourceHanSansCN-Regular.otf
│   ├── SourceHanSansCN-Light.otf
│   └── SourceHanSansCN-Bold.otf
├── logos/
│   ├── chadan-logo-color.png
│   ├── chadan-logo-black.png
│   └── chadan-logo-white.png
└── graphics/
    ├── 辅助图形1.png
    └── 辅助图形2.png
```

---

## 品牌概述

茶蛋（ChaDan Land）是一个职业发展陪伴平台，核心价值是沟通、支持与陪伴。品牌调性：**温暖亲近、专业不距离、简洁有力**，像朋友间的对话，而非机构感的说教。

---

## 色彩系统

| 名称 | Hex | RGB | 使用比例 | 用途 |
|------|-----|-----|---------|------|
| 白色 | `#ffffff` | 255, 255, 255 | **约 80% 页面** | 默认背景，保证页面干净、内容清晰 |
| 米色 Beige | `#f0ebd8` | 240, 235, 216 | 少量使用 | 卡片底、局部留白或轻量分区；不作为默认整页背景 |
| 品牌绿 | `#006b31` | 0, 107, 49 | 少量重点页 | 标题/图形/强调；也可作章节、过渡、强调或引用页整页背景 |
| 品牌黄 | `#ffb233` | 255, 178, 51 | 少量重点页 | 点缀色；也可作章节、过渡、强调或引用页整页背景 |
| 黑色 | `#000000` | 0, 0, 0 | 按需 | 正文、细节线条 |

**背景优先级（必须遵守）：**
- **约 80% 的页面使用白色 `#ffffff` 整页背景。**常规内容页、封面、列表、图表和信息页均优先白底。
- 其余页面只在需要调节节奏或突出信息时，使用品牌绿或品牌黄整页背景：章节页、过渡页、强调页、Quote/引用页。
- 品牌绿背景配白色文字；品牌黄背景配黑色文字。米色只作局部辅助，不作为常规页面底色。

**配色搭配：**
- 白色背景 + 黑色正文 + 品牌绿强调（默认）
- 品牌绿背景 + 白色文字 + 品牌黄点缀
- 品牌黄背景 + 黑色文字 + 品牌绿强调

---

## 字体系统

### 字体对应关系

| 层级 | 字体显示名 | python-pptx 字体名 | CSS 写法 | 用途 |
|------|-----------|-------------------|---------|------|
| **标题** | 寒蝉有机体 Medium | `寒蝉有机体 Medium` | `'ChillOrganic'` | 所有大标题、封面文字 |
| **副标题/小标题** | 寒蝉有机体 Regular | `寒蝉有机体` | `'ChillOrganic'` | 次级标题 |
| **正文** | 思源黑体 Regular | `Source Han Sans CN` | `'Noto Sans SC'` | 正文内容，行距 1.6 |
| **注释说明** | 思源黑体 Light | `Source Han Sans CN Light` | `'Noto Sans SC'` | 字号为正文 60–80% |

> ⚠️ **关键说明**：python-pptx 中设置字体名必须使用上表「python-pptx 字体名」列的精确字符串，否则 PowerPoint 无法识别，会回落到系统默认字体。

### 字体为首次交付的硬性验收项

无论用户是否再次提醒，制作任何茶蛋 PPT、HTML、PDF 或视觉物料时，**首次产出就必须使用品牌字体**：标题使用寒蝉有机体，正文使用思源黑体。不得以系统默认字体、苹方、Arial、微软雅黑或其他替代字体交付。

在开始排版前，必须确认所需字体文件可读取；若字体文件缺失或当前环境无法加载，停止生成并明确说明问题，等待用户决定，**不要静默回落到系统字体**。

交付前必须完成对应格式的核对：
- **PPT：**逐个文字 run 写入精确字体名，并同时设置 East Asian 字体；标题/封面为 `寒蝉有机体 Medium`，小标题为 `寒蝉有机体`，正文为 `Source Han Sans CN`，注释为 `Source Han Sans CN Light`。
- **HTML：**以 `@font-face` 实际加载本地品牌字体；仅写 `font-family: Noto Sans SC` 或依赖浏览器系统字体不算完成。独立交付的 HTML 必须将所需 OTF 放入随附 `fonts/` 目录并用相对路径引用，不能依赖本机绝对路径。
- **PDF：**导出前确认标题和正文分别应用寒蝉有机体与思源黑体；不能以截图、位图文字或系统字体替代。

### 字体文件路径（本地）

```
寒蝉有机体 Regular: `assets/fonts/ChillOrganic_Regular.otf`
寒蝉有机体 Medium:  `assets/fonts/ChillOrganic_Medium.otf`
思源黑体 Regular:   `assets/fonts/SourceHanSansCN-Regular.otf`
思源黑体 Light:     `assets/fonts/SourceHanSansCN-Light.otf`
思源黑体 Bold:      `assets/fonts/SourceHanSansCN-Bold.otf`
```

### 在 PPT（python-pptx）中使用字体

制作 PPT 时，必须先将字体安装到沙箱环境，再用精确字体名写入 PPTX：

```python
import shutil, os
from pathlib import Path

# 第一步：把字体复制到沙箱 fonts 目录（让系统能找到）
# 从包含 SKILL.md 的 chadan-brand 文件夹运行此段代码
SKILL_ROOT = Path.cwd()
ASSETS_DIR = SKILL_ROOT / "assets" / "fonts"
FONT_DIR = os.path.expanduser("~/.local/share/fonts")
os.makedirs(FONT_DIR, exist_ok=True)
font_names = ["ChillOrganic_Regular.otf", "ChillOrganic_Medium.otf",
              "SourceHanSansCN-Regular.otf", "SourceHanSansCN-Light.otf"]
missing = [name for name in font_names if not (ASSETS_DIR / name).is_file()]
if missing:
    raise FileNotFoundError(f"品牌字体缺失：{missing}。不要改用系统字体。")
for fname in font_names:
    shutil.copy(ASSETS_DIR / fname, FONT_DIR)

# 第二步：在 python-pptx 中使用精确字体名
from pptx.util import Pt
from pptx.dml.color import RGBColor

def set_font(run, is_heading=True, size_pt=28, color=(0, 0, 0)):
    if is_heading:
        font_name = "寒蝉有机体 Medium"   # 大标题
    else:
        font_name = "Source Han Sans CN"  # 正文
    run.font.name = font_name
    # 同时写入拉丁和东亚字体，避免中文文字回落到系统默认字体
    rPr = run._element.get_or_add_rPr()
    rPr.set(qn("a:latin"), font_name)
    rPr.set(qn("a:ea"), font_name)
    rPr.set(qn("a:cs"), font_name)
    run.font.size = Pt(size_pt)
    run.font.color.rgb = RGBColor(*color)
```

代码示例还需导入：`from pptx.oxml.ns import qn`。生成完成后，抽查封面标题、正文和注释各至少一处，确认其 XML 中的 `a:latin` 与 `a:ea` 都是上述精确字体名，再交付文件。

### 在 HTML 中使用字体

```css
@font-face {
  font-family: 'ChillOrganic';
  src: url('./fonts/ChillOrganic_Medium.otf') format('opentype');
  font-weight: 500;
}
@font-face {
  font-family: 'ChillOrganic';
  src: url('./fonts/ChillOrganic_Regular.otf') format('opentype');
  font-weight: 400;
}
@font-face {
  font-family: 'SourceHanSansCN';
  src: url('./fonts/SourceHanSansCN-Regular.otf') format('opentype');
  font-weight: 400;
}
@font-face {
  font-family: 'SourceHanSansCN';
  src: url('./fonts/SourceHanSansCN-Light.otf') format('opentype');
  font-weight: 300;
}
h1, h2, h3 {
  font-family: 'ChillOrganic', 'PingFang SC', sans-serif;
  font-weight: 500;
}
body {
  font-family: 'SourceHanSansCN', 'Noto Sans SC', 'Source Han Sans SC', sans-serif;
}
```

> HTML 为独立文件夹交付时，将以上四个 OTF 复制到同级 `fonts/` 目录，并保留相对路径。若只在本机预览，可将 `src` 改为上方列出的绝对路径；两种场景都必须确认浏览器成功加载品牌字体。

---

## Logo 系统

### 品牌层级

茶蛋是**主品牌**，其他均为子账号/子品牌，默认使用茶蛋 Logo：

| 品牌 | 定位 | 默认使用？ |
|------|------|----------|
| 茶蛋 ChaDan Land | 主品牌 | ✅ 所有场合默认使用 |
| Frankly Speaking | 茶蛋旗下英文内容子账号 | 仅该子账号的专属物料 |
| 茶蛋说 | 茶蛋旗下音频播客子账号 | 仅播客相关物料 |
| 小茶和Frank | 个人 IP（Lynx 本人自媒体） | 见下方触发条件 |

### 茶蛋主品牌 Logo（默认使用）

| 版本 | 文件路径 | 使用场景 |
|------|---------|---------|
| 彩色全标 | `assets/logos/chadan-logo-color.png` | 白色/米色等浅色背景 |
| 单色黑色 | `assets/logos/chadan-logo-black.png` | 浅色背景的印刷/低彩场合 |
| 单色白色 | `assets/logos/chadan-logo-white.png` | 深色/品牌绿背景 |

### 子账号 Logo

| 子品牌 | 文件路径 | 触发场景 |
|--------|---------|---------|
| Frankly Speaking | 未随本包提供 | 物料明确为 Frankly Speaking 内容时，向品牌方索取授权文件 |
| 茶蛋说（播客封面） | 未随本包提供 | 播客封面、茶蛋说相关内容时，向品牌方索取授权文件 |

### 个人 IP Logo：小茶和Frank（谨慎使用）

**文件路径：** 未随本包提供；如有明确授权，由品牌方单独提供。

**仅在用户明确指定以下场景时使用**，其余情况一律使用茶蛋主品牌 Logo：
- 「个人自媒体」「个人 IP」
- 「@小茶和Frank」（小红书 / 公众号 / 视频号等任何平台）
- 「个人 IP @小茶和Frank」
- 「自媒体 IP @小茶和Frank」

### Logo 使用铁律（严格执行，无例外）

**放置规则：**
- Logo 必须**等比缩放**，绝对不允许单独改变宽度或高度
- 在 python-pptx 中插入 Logo 时，必须根据图片原始宽高比计算尺寸：

```python
from PIL import Image
from pptx.util import Inches

def add_logo_proportional(slide, logo_path, left, top, width_inches):
    """按比例插入 Logo，防止变形"""
    img = Image.open(logo_path)
    w_px, h_px = img.size
    aspect = h_px / w_px
    width = Inches(width_inches)
    height = int(width * aspect)  # 严格按原始比例计算高度
    slide.shapes.add_picture(logo_path, left, top, width=width, height=height)
```

**禁止行为：**
- ❌ 不可旋转、倾斜 Logo
- ❌ 不可拉伸或压缩（只能等比缩放）
- ❌ 不可镜像
- ❌ 不可裁剪 Logo 图形本体（辅助留白可裁）
- ❌ 不可在深色/品牌色背景上使用彩色版
- ❌ 不可在图案/渐变背景上使用彩色版

---

## 辅助图形

| 图形 | 路径 | 描述 |
|------|------|------|
| 辅助图形1 | `assets/graphics/辅助图形1.png` | 黄色C弧 + 绿色D弧，角落装饰 |
| 辅助图形2 | `assets/graphics/辅助图形2.png` | 绿色有机流线，源自D字母 |

放置在页面/幻灯片角落（左上+右下对角），同样必须等比缩放，勿遮挡文字和 Logo。

---

## 各类物料规范

### PPT 幻灯片
- 比例：16:9
- 背景：白色 `#ffffff`（默认，约 80% 页面）。米色 `#f0ebd8` 仅作局部卡片、分区或留白，不作默认整页底色。
- 章节页、过渡页、强调页、Quote/引用页可使用品牌绿 `#006b31` 整页背景配白色文字，或品牌黄 `#ffb233` 整页背景配黑色文字。
- 封面标题：寒蝉有机体 Medium（python-pptx 字体名：`寒蝉有机体 Medium`），颜色 `#006b31` 或黑色
- 正文：思源黑体 Regular（python-pptx 字体名：`Source Han Sans CN`），`#000000`
- 字体：首次交付前按“字体为首次交付的硬性验收项”完成字体文件、East Asian 字体字段和抽查验证；不可使用系统默认字体。
- 强调色块/线条：品牌绿 `#006b31`
- 点缀：品牌黄 `#ffb233`
- Logo：彩色全标，右下角（等比缩放插入）
- 辅助图形：角落装饰，等比缩放

### PDF 文档
- 背景：白色 `#ffffff`（默认）；米色 `#f0ebd8` 仅作局部辅助
- 标题：寒蝉有机体 Medium，18–24pt，`#006b31`
- 正文：思源黑体 Regular，10–12pt，`#000000`，行距 1.6
- 注释：思源黑体 Light，8–10pt，`#555555`

### HTML 页面
- 主背景：白色 `#ffffff`（默认）；米色 `#f0ebd8` 仅作局部区块或卡片辅助底色
- 卡片背景：`#ffffff`
- 主文字：`#000000`
- 链接/强调：`#006b31`
- 按钮：背景 `#006b31`，文字 `#ffffff`；hover `#ffb233`
- 圆角：8–16px（呼应品牌有机感）
- 标题字体：ChillOrganic（从本地路径加载，见字体部分 CSS）
- 正文字体：SourceHanSansCN（从本地字体文件加载；Noto Sans SC 仅作最后备用字体）
- 字体：首次交付时确认浏览器网络面板或渲染结果已实际加载 `ChillOrganic` 与 `SourceHanSansCN`，不可依赖系统默认字体。
- 章节、过渡、强调或 Quote/引用区块可使用品牌绿背景配白字，或品牌黄背景配黑字；不得因此将普通内容区改为米色整页背景

---

## 品牌指南

本包的 `SKILL.md` 是可直接执行的完整品牌规则；不要依赖同事电脑上的本机绝对路径。
