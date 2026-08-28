# 一照知运 · FaceFates

> 拍照算命 · 面相五行趣味测算
> Snap a selfie — get a Chinese face-reading destiny report.

🌐 **在线体验 / Live:** https://dabowen-jun.github.io/facefates/

---

## 项目简介 / Overview

把传统中国相术（面相、五行、紫微斗数）做成「拍照即测算」的轻量体验。
拍一张自拍或上传照片，即可得到一份包含五行强弱、紫微主星、十神格局、四化飞星、长生十二神的完整命盘，
以及对**财运 · 事业 · 家庭 · 人际 · 仕途**五个维度的深度解读。

**English:** FaceFates turns traditional Chinese physiognomy (面相) into a one-tap experience.
Upload a selfie and receive a full destiny report — Five Elements (Wu Xing) balance, one of the
14 Ziwei major stars, the Ten Gods pattern, Four Transformations and the 12 Life Stages — with
commentary across wealth, career, family, relationships and status.

---

## 核心特性 / Features

| | 特性 | 说明 |
|---|---|---|
| 📸 | **照片驱动** | 从照片真实像素提取特征（亮度 / 冷暖 / 肤色占比 / 对比度 / 锐度），不同照片给出不同结果，拒绝"千人一面" |
| 🔒 | **隐私优先** | 全部分析在浏览器本地完成（Canvas `getImageData`）。**照片永不上传**，无后端、无账号、无追踪 |
| 🎲 | **可复现** | 确定性 PRNG（mulberry32）由照片特征播种：同一张照片结果稳定，换照片结果不同；「换一卦」可换排列 |
| 🌏 | **中英双语** | 完整 zh / en i18n，一键切换，含英文专属版式适配 |
| 📱 | **PWA** | 可「添加到主屏幕」，全屏运行、独立图标、**支持离线** |
| 📄 | **导出分享** | PDF 导出（带「面相 · 五行」水印）+ 可截图传播的命盘分享卡 |
| 🔗 | **一键分享** | 微信（引导蒙层）/ 微博 / QQ / X / Facebook + 系统原生分享 |

---

## 技术栈 / Tech

- **单文件 HTML** — 无构建、无框架、零运行时依赖
- **PWA** — `manifest.json` + Service Worker（stale-while-revalidate 离线缓存）
- **图像分析** — 原生 Canvas `getImageData`，本地完成
- **命格生成** — mulberry32 确定性 PRNG，由照片特征播种
- **托管** — GitHub Pages（免费 HTTPS，满足摄像头 `getUserMedia` 的安全上下文要求）

---

## 命理依据 / Classical Sources

《麻衣神相》· 《神相全编》· 紫微斗数十四正曜 · 子平八字十神 · 钦天四化 · 长生十二神

---

## 目录结构 / Structure

```
index.html            # 主应用（单文件，含全部逻辑）
manifest.json         # PWA 清单
sw.js                 # Service Worker（离线缓存）
icon-192.png          # PWA 图标 192×192
icon-512.png          # PWA 图标 512×512
apple-touch-icon.png  # iOS 主屏幕图标 180×180
share-cover.png       # 社交分享图 1200×630
PROMO-COPY-EN.md      # 英文推广文案包（社媒 / PH / 广告 / SEO / LinkedIn）
```

---

## 本地运行 / Run Locally

直接双击 `index.html` 即可（部分浏览器需 HTTP 环境才能调用摄像头）：

```bash
python -m http.server 8000
# 打开 http://localhost:8000
```

> 注：PWA 与 Service Worker 需 `http://` 或 `https://` 环境，`file://` 下自动跳过注册。

---

## 免责声明 / Disclaimer

本项目为中华传统文化的趣味演绎与娱乐工具，**不构成任何预测、建议或决策依据**。
命运掌握在自己手中，娱乐仅供参考。

This project is a playful interpretation of Chinese cultural heritage.
**For entertainment purposes only** — it does not predict or guarantee any outcome.
