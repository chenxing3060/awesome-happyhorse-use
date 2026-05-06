# HappyHorse 1.0 系列模型使用指南

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![English](https://img.shields.io/badge/docs-English-blue)](README.md)

> 本文档持续更新中，欢迎通过 Issue 或 PR 贡献你的使用技巧和案例。

---

## 🌟 模型亮点速览

**HappyHorse 1.0** 是一款基于原生多模态架构的新一代 AI 视频生成模型，支持音视频协同生成。产品深度适配广告营销、电商展示、短剧制作与社交媒体创意等内容生产场景，提供从**智能生成**到**精细编辑**的一体化创作工作流。本次模型的亮点如下：

- **画面够专业**：电影级光影与质感，直出可用
- **镜头够流畅**：运镜稳定、转场自然，告别生硬切换
- **人物够真实**：表情细腻、动作自然，拒绝"恐怖谷"效应
- **叙事够清晰**：中近景表现力强，适合剧情与对话场景
- **创作够自由**：风格多样、参数可调，满足差异化需求

HappyHorse 1.0 致力于为创作者与企业提供稳定、高效、可控的视频生产解决方案，持续赋能专业内容创作流程。

> 🎉 **百炼现已支持体验 HappyHorse 1.0 系列模型**

---

## 📖 模型详情信息

| 模型名称 | 模型能力 | 输入输出 | 计费单价 |
| --- | --- | --- | --- |
| `happyhorse-1.0-t2v` | 输入文本提示词生成物理真实、运动流畅的视频内容。 | 文字 → 视频 | 720P：¥0.9/秒<br>1080P：¥1.6/秒<br>免费额度：10秒 |
| `happyhorse-1.0-i2v` | 以首帧图片为基础，支持通过文本描述进行引导，生成物理真实、运动流畅的视频。 | 图片 + 文字 → 视频 | |
| `happyhorse-1.0-r2v` | 支持传入多张参考图像，通过文本提示词描述场景，将图像中的主体角色融合生成一段流畅的视频。 | 参考图片 + 文字 → 视频 | |
| `happyhorse-1.0-video-edit` | 支持输入视频与参考图，结合文本指令完成风格变换、局部替换等编辑任务。 | 视频 + 文字（+ 参考图）→ 视频 | |

> ⚠️ 注：HappyHorse 原生支持 **7 种语言**——中文（普通话）、粤语、英语、日语、韩语、德语、法语

---

## 🎬 模型 Case Demo

> **HappyHorse 创作手册**：[《HappyHorse 1.0 创作指南》](https://alidocs.dingtalk.com/i/nodes/14lgGw3P8vxjwogPCp6oqM91V5daZ90D?utm_scene=person_space)

### T2V 文生视频

文生视频模型，只需要用户输入一段提示词即可生成。prompt 即正向提示词，用来描述视频中所包含的画面内容和运动过程，描述越准确、越丰富，生成视频的质量越高。

**提示词公式 = 场景 + 主体 + 运动 + 音频**

- **场景**：场景是主体所处的环境，包含背景、前景，可以是物理存在的真实空间或想象出来的虚构场景。
- **主体**：主体是视频内容的主要表现对象，可以是人、动物、植物、物品或非物理真实存在的想象物体。
- **运动**：运动包含主体的具体运动和非主体的运动状态，可以是静止、小幅度运动、大幅度运动、局部运动或整体动势。

| Input (Text) 输入文字 | Output Video 输出视频 |
| --- | --- |
| 动漫风格，国风2d风格... | [▶️ 点击播放](https://github.com/chenxing3060/awesome-happyhorse-use/blob/main/videos/t2v_01_guofeng_girl.mp4) |

| 全景，新海诚风格... | [🎬 t2v_02_makoto_shinkai.mp4](videos/README.md#t2v-文生视频) |
| 主题与动作：一场电影般的武术对决... | [🎬 t2v_03_minecraft_fight.mp4](videos/README.md#t2v-文生视频) |
| 【场景】奢华的私人飞机机舱内... | [🎬 t2v_04_private_jet.mp4](videos/README.md#t2v-文生视频) |
| 东方古装写实风格... | [🎬 t2v_05_queen_cold_smile.mp4](videos/README.md#t2v-文生视频) |
| A cinematic script scene set in a sun-drenched Parisian café... | [🎬 t2v_06_paris_cafe.mp4](videos/README.md#t2v-文生视频) |
| 生成一段10s韩国男女在咖啡馆谈恋爱对话的片段... | [🎬 t2v_07_korean_cafe.mp4](videos/README.md#t2v-文生视频) |
| 一镜到底，电影质感画面。pizza店... | [🎬 t2v_08_pizza_shop.mp4](videos/README.md#t2v-文生视频) |
| 纯黑背景，微型厨房ASMR... | [🎬 t2v_09_tiny_kitchen.mp4](videos/README.md#t2v-文生视频) |
| 人群与遮阳伞渐渐散去... | [🎬 t2v_10_peaceful_beach.mp4](videos/README.md#t2v-文生视频) |
| 生成一个连续的延时摄影风格视频，展示一颗柠檬树... | [🎬 t2v_11_lemon_timelapse.mp4](videos/README.md#t2v-文生视频) |
| 高山雪原，极限滑雪者... | [🎬 t2v_12_ski_avalanche.mp4](videos/README.md#t2v-文生视频) |

### I2V 图生视频（首帧）

以一张图片作视频的起始画面（首帧），模型基于该图片内容生成后续的动态视频。上传的图片即为视频第一帧，确保画面起点与你的预期完全一致。

**适用场景**：

- 有一张满意的设计稿或插画，想让它"动起来"
- 需要精确控制视频的开场画面
- 基于产品图、人像照等现有素材快速生成动态展示

**书写建议**：提示词中重点描述"动起来之后发生什么"——动作、运动轨迹、镜头变化等。无需重复描述图片中已有的静态内容，模型会自动识别首帧画面信息。

| Input (Text + Image) 输入文字+首帧图片 | Output Video 输出视频 |
| --- | --- |
| 分镜1 (生成4s)：王爷端坐执卷... | [🎬 i2v_01_period_drama.mp4](videos/README.md#i2v-图生视频) |
| 直播间里，两只猫咪以拟人化形象做搞笑对话... | [🎬 i2v_02_cat_livestream.mp4](videos/README.md#i2v-图生视频) |
| 【镜头一 · 0–4秒】画面从头盔玻璃面罩内侧... | [🎬 i2v_03_scifi_helmet.mp4](videos/README.md#i2v-图生视频) |
| 镜头1：高空垂直俯视镜头，银色跑车... | [🎬 i2v_04_sports_car.mp4](videos/README.md#i2v-图生视频) |
| The camera slowly pushes into the astronaut's reflective gold visor... | [🎬 i2v_05_astronaut_moon.mp4](videos/README.md#i2v-图生视频) |
| The black and white wavy lines and checkered patterns... | [🎬 i2v_06_cartoon_card.mp4](videos/README.md#i2v-图生视频) |
| The cute teddy bear as it briskly walks forward... | [🎬 i2v_07_teddy_bear.mp4](videos/README.md#i2v-图生视频) |
| A girl is dancing gracefully. As she spins... | [🎬 i2v_08_girl_dance.mp4](videos/README.md#i2v-图生视频) |

### R2V 参考生视频（支持图片输入）

HappyHorse 1.0 R2V 支持通过多张图片引导视频生成，包括主体多视角参考、场景图参考、分镜图参考等多种用法。上传图片时，如对图片顺序有要求，请按顺序上传。在提示词中可通过 `@[图片1]` `[图片2]` ... `[图片n]` 进行准确指代。

API 中最多支持 9 张图片上传。

**适用场景**：

- 需要保持角色在不同镜头中外观一致，提供同一角色的多角度照片作为参考
- 有明确的场景设定或美术风格板，希望视频还原特定的视觉风格
- 按照分镜脚本制作视频，将各分镜图依次上传引导生成
- 需要将多个元素（如角色 + 场景 + Logo）组合到同一段视频中

**提示词参考示例**：

- 参考 `[图片1]` 中的角色形象，她走进 `[图片2]` 中的场景，推开门后回头微笑，镜头跟随，电影质感
- 提取 `[图片1]` 和 `[图片2]` 中的猫咪特征，生成它在窗台上打盹后被惊醒的画面，保持毛色和花纹一致
- 结合 `[图片1]` 的正面照和 `[图片2]` 的侧面照，生成该角色转身回眸的动态画面，保持五官和发型一致
- 以 `[图片1]` 为画面风格参考，`[图片2]` 中的人物在樱花树下漫步，最后出现 `[图片3]` 中的 Logo，整体色调统一

| Input (Text + Image) 输入文字+图片 | Output Video 输出视频 |
| --- | --- |
| 一张超逼真的4K摄影级画面，宠物播客... | [🎬 r2v_01_pet_podcast.mp4](videos/README.md#r2v-参考生视频) |
| Generate a Pixar-style video... | [🎬 r2v_02_pixar_girl.mp4](videos/README.md#r2v-参考生视频) |
| 参考 [图1] 中的王爷形象与 [图2] 中的丫头形象... | [🎬 r2v_03_period_romance.mp4](videos/README.md#r2v-参考生视频) |
| 电影质感，智能分镜，少年特工对话... | [🎬 r2v_04_young_spies.mp4](videos/README.md#r2v-参考生视频) |
| 生成一段韩漫风格、电影感的短视频。雨夜便利店... | [🎬 r2v_05_convenience_store.mp4](videos/README.md#r2v-参考生视频) |

### Video Edit 视频编辑（风格转换/元素替换）

对已有视频进行 AI 智能编辑，无需从零生成，在原片基础上实现精准修改。你可以通过文字提示词描述修改意图，也可以同时上传参考图片提供视觉引导，两种方式可灵活搭配使用。

**适用场景**：

- 对视频整体风格不满意，想转换画面氛围（如写实转动漫、白天转黄昏）
- 需要修改画面中的局部元素（如替换背景、改变服装颜色、添加天气特效）
- 有一张目标风格的参考图，希望视频整体视觉效果向其靠拢
- 需要将视频中的某个元素替换为参考图中的特定对象
- 对 AI 生成的视频做二次修正，微调动作或画面细节

**提示词参考示例**：

- 将视频中的背景从现代城市替换为古风街道，青石板路，远处有飞檐亭台，保持人物动作不变
- 将整体画面风格转为吉卜力动画风格，色彩明亮柔和，保持原始运动轨迹
- 为画面添加飘落的雪花效果，地面逐渐覆盖薄雪，整体色调偏冷
- 参考 `[图片1]` 的画面风格，将视频整体色调和质感调整为与参考图一致，保持原始动作和构图
- 将视频中人物的服装替换为 `[图片1]` 中的服装样式，保持人物动作和面部不变

**书写建议**：提示词中明确指出"改什么"和"保留什么"。描述越具体，模型越能精准执行编辑，避免误改不需要调整的部分。

| Input (Text + Image + Video) 输入文字+视频+参考图 | Output Video 输出视频 |
| --- | --- |
| 参考 Image 1，将视频中女主衣服替换为雾霾蓝明制汉服... | [🎬 edit_01_hanfu_replace.mp4](videos/README.md#video-edit-视频编辑) |
| 参考 Image 1，将视频中白色邮轮替换为太空飞船... | [🎬 edit_02_spaceship_replace.mp4](videos/README.md#video-edit-视频编辑) |
| 参考 Image 1 中的视觉特征，视频转为传统黑白水墨画风格... | [🎬 edit_03_ink_wash.mp4](videos/README.md#video-edit-视频编辑) |
| Transform the city into a cyberpunk style. | [🎬 edit_04_cyberpunk.mp4](videos/README.md#video-edit-视频编辑) |
| Transform the entire video into the Minecraft voxel style... | [🎬 edit_05_minecraft_voxel.mp4](videos/README.md#video-edit-视频编辑) |
| 将视频中猫戴的黑框眼镜替换为金丝框眼镜，随音乐摇摆... | [🎬 edit_06_cat_glasses.mp4](videos/README.md#video-edit-视频编辑) |

---

## 🐴 应用场景参考

### 电商 - 古装爽剧带货

| Input 模型输入 | Output Video 输出视频 |
| --- | --- |
| 4s 1080P R2V：参考王爷与丫头形象，古风书房暖光场景... | [🎬 case_01_period_perfume_ad.mp4](videos/README.md#应用场景案例) |
| 宋代宫廷内景，皇后与贵妃，蓝鱼子精华带货... | [🎬 case_02_palace_skincare_ad.mp4](videos/README.md#应用场景案例) |

---

## 💻 API 参考

### 开发文档

- [HappyHorse - 文生视频 API](https://help.aliyun.com/zh/model-studio/happyhorse-text-to-video-api-reference)
- [HappyHorse - 图生视频（基于首帧）API](https://help.aliyun.com/zh/model-studio/happyhorse-image-to-video-api-reference)
- [HappyHorse - 参考生视频 API](https://help.aliyun.com/zh/model-studio/happyhorse-reference-to-video-api-reference)
- [HappyHorse - 视频编辑 API](https://help.aliyun.com/zh/model-studio/happyhorse-video-edit-api-reference)

### 模型调用地址

**北京**：
```
POST https://dashscope.aliyuncs.com/api/v1/services/aigc/video-generation/video-synthesis
```

**新加坡**：
```
POST https://dashscope-intl.aliyuncs.com/api/v1/services/aigc/video-generation/video-synthesis
```

### Python 调用示例

```python
import requests

url = "https://dashscope.aliyuncs.com/api/v1/services/aigc/video-generation/video-synthesis"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}
payload = {
    "model": "happyhorse-1.0-t2v",
    "input": {
        "prompt": "电影质感，一镜到底。一个pizza店里，大胡子的白人店员正在烤制披萨..."
    },
    "parameters": {
        "duration": 5,
        "resolution": "1080p"
    }
}

response = requests.post(url, headers=headers, json=payload)
print(response.json())
```

---

## 🤝 贡献指南

欢迎提交你的使用技巧、Prompt 案例和最佳实践！详见 [CONTRIBUTING.md](CONTRIBUTING.md)。

---

## 📄 许可证

本项目采用 Apache License 2.0 许可证，详见 [LICENSE](LICENSE)。

---

## 🔗 相关链接

- [百炼平台](https://help.aliyun.com/zh/model-studio/)
- [DashScope API 密钥](https://dashscope.aliyun.com/)
- [HappyHorse 1.0 创作指南](https://alidocs.dingtalk.com/i/nodes/14lgGw3P8vxjwogPCp6oqM91V5daZ90D)
