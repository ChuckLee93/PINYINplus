# PINYINplus — 汉字拼音标注插件 / Pinyin Annotator for KOReader

仿 Kindle「生字注音」功能：在中文页面每个汉字的**上方叠加拼音**，并可按**常用度等级**控制只给较生僻的字注音。实测支持 EPUB / DOCX / HTML（建议 EPUB）；其它格式未测试，可能显示不出拼音。

Mimics Kindle's "生字注音" (ruby annotation): overlays **pinyin above each character** on Chinese pages, with **rarity-level control** so only uncommon characters get annotated. Tested with EPUB / DOCX / HTML (EPUB recommended); other formats untested.

> ⚠️ 本插件完全免费、开源（GPL-3.0），官方渠道永远免费，直接来本仓库免费下载即可。近期有人在小红书等平台售卖本插件，请注意甄别，不要付费。
> ⚠️ This plugin is completely free and open-source (GPL-3.0). If anyone tries to sell it to you, it's a scam — always get it free from this repo.

效果示意 / Sample (pinyin above each character, only rarer ones annotated per level):

```
  zhōng  guó   rén   mín   xǐ  huān   dú   shū
   中    国    人    民    喜   欢    读   书
```

---

## ✨ 功能 / Features

- **逐字拼音**：用 crengine 取得当前页每个字的坐标，在屏幕上叠加带声调拼音（ā á ǎ à）。
  Per-character pinyin with tones, drawn onto the current page via crengine coordinates.
- **分级注音（核心）**：按汉字常用度分 1–5 级（「标注等级」菜单调节；越高注音越多；默认 2 = 生僻字）。常用度排名来自《通用规范汉字表》国家规定字表顺序。
  Leveled annotation (core): 5 rarity levels, default 2; rank from the national *通用规范汉字表*.
- **多音字词组辨音（v6.0+）**：结合上下文 2–6 字词组判断多音字读音（银行 háng / 行走 xíng），最长匹配优先；纯查表，不影响翻页速度。
  Polyphone disambiguation via context phrases (v6.0+); pure lookup, zero impact on page-turn speed.
- **生词本词组注音（v6.0+）**：查词时加入 KOReader 官方「生词本」的词，整词出现才注音；单字入本则处处注音；删改自动同步。
  Vocabulary-book integration (v6.0+): words added to KOReader's vocab builder get annotated only when the whole word appears.
- **默认读音修正（v6.0+）**：修正 kTGHZ2013 数据源把罕见读音排前的 430 字（行 háng→xíng、重 chóng→zhòng 等）。
  Default-pronunciation fixes (v6.0+) for 430 chars.
- **可调样式**：拼音字号、颜色（黑/深灰）。
  Adjustable size & color (black/dark grey).
- **自动重绘**：翻页后自动重新标注；关闭时清除。
  Auto re-render after page turn; clears when off.
- **数据全**：内置 8105 个汉字（通用规范汉字表全量，含扩展区字符）的「拼音 + 排名」，可自行追加自定义字。
  Full built-in data: 8105 chars (pinyin + rank), extensible.

## 📦 安装 / Installation

1. 把 `pinyin.koplugin` 整个文件夹复制到 Kindle 的 `koreader/plugins/` 下
   Copy the whole `pinyin.koplugin` folder into `koreader/plugins/`.
2. 重启 KOReader — Restart KOReader.
3. 打开中文书籍 → 顶部菜单 → 齿轮（设置）→ 注音相关菜单项调节等级/样式
   Open a Chinese book → top menu → gear (settings) → adjust level/style.

> 对外版本号 v2.0（内部迭代号 6.4）。PDF 支持有限，详见 `pinyin.koplugin/README.md`。
> Public version v2.0 (internal iteration 6.4). PDF support is limited; see `pinyin.koplugin/README.md`.

## 📜 许可证 / License

GPL-3.0（见 `pinyin.koplugin/LICENSE`）。
GPL-3.0 (see `pinyin.koplugin/LICENSE`).

## 🙏 原作者与鸣谢 / Original Authors & Credits

- **原作者 / Original author**: **zhouwt**（`config.lua` 署名 `Copyright (C) 2026 zhouwt`，GPL-3.0）
- **自用修改版 / Personal modified build**: 在此之上针对性能与体验优化（生僻字扩展、词组辨音、生词本联动等）

感谢原作者 zhouwt 的创作。本仓库为自用修改版，功能与行为差异见 `使用说明.txt`。
Thanks to the original author zhouwt. This repo is a personally-modified build; see `使用说明.txt` for what changed.
