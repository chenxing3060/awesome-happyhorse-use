# HappyHorse 1.0 — Next-Gen AI Video Generation Models

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Documentation](https://img.shields.io/badge/docs-中文指南-brightgreen)](README_zh.md)

**HappyHorse 1.0** is a next-generation AI video generation model series built on a native multimodal architecture, supporting synchronized audio-visual generation. The product is deeply optimized for content production scenarios including advertising & marketing, e-commerce showcases, short drama production, and social media creativity — offering an integrated creative workflow from **intelligent generation** to **fine-grained editing**.

> 🎉 HappyHorse 1.0 is now available on [Alibaba Cloud Model Studio (百炼)](https://help.aliyun.com/zh/model-studio/).

---

## ✨ Key Highlights

- **Cinematic Visual Quality** — Film-grade lighting and textures, production-ready output out of the box
- **Smooth Cinematography** — Stable camera movements with natural transitions, no more jarring cuts
- **Lifelike Characters** — Delicate facial expressions and natural motion, free from the "uncanny valley" effect
- **Clear Narrative Expression** — Strong close-up and mid-shot expressiveness, ideal for dialogue and storytelling scenes
- **Creative Freedom** — Diverse styles with tunable parameters to meet differentiated creative needs

HappyHorse 1.0 is committed to providing creators and enterprises with a stable, efficient, and controllable video production solution that continuously empowers professional content creation workflows.

---

## 🧩 Model Lineup

| Model | Capability | Input → Output | Pricing |
|-------|-----------|----------------|---------|
| `happyhorse-1.0-t2v` | Generate physically realistic, smoothly-moving videos from text prompts | Text → Video | 720p: ¥0.9/s<br>1080p: ¥1.6/s<br>Free tier: 10s |
| `happyhorse-1.0-i2v` | Generate dynamic videos starting from a first-frame image, guided by text descriptions | Image + Text → Video | |
| `happyhorse-1.0-r2v` | Accept multiple reference images to fuse character/subject roles into smooth video through text-driven scene description | Reference Images + Text → Video | |
| `happyhorse-1.0-video-edit` | Perform style transfer, local replacement, and other editing tasks on input video with text instructions and optional reference images | Video + Text (+ Reference Image) → Video | |

> ⚠️ HappyHorse natively supports **7 languages**: Chinese (Mandarin), Cantonese, English, Japanese, Korean, German, French.

---

## 🎬 Quick Start

### Prerequisites

- An Alibaba Cloud account with Model Studio (百炼) access
- API key from [DashScope](https://dashscope.aliyun.com/)

### API Endpoint

```
POST https://dashscope.aliyuncs.com/api/v1/services/aigc/video-generation/video-synthesis
```

For international users:

```
POST https://dashscope-intl.aliyuncs.com/api/v1/services/aigc/video-generation/video-synthesis
```

### Text-to-Video Example

```python
import requests
import json

url = "https://dashscope.aliyuncs.com/api/v1/services/aigc/video-generation/video-synthesis"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}
payload = {
    "model": "happyhorse-1.0-t2v",
    "input": {
        "prompt": "Cinematic shot of a girl dancing gracefully, spinning in a full turn, sunset golden hour lighting"
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

## 📚 Documentation

- **[中文使用指南 (Chinese Guide)](README_zh.md)** — Full usage guide with prompt writing tips, case demos, and application scenarios
- **[Video Demos 🎬](videos/README.md)** — Download all demo videos via GitHub Releases
- **[Text-to-Video Guide](docs/t2v-guide.md)** — Prompt engineering and best practices for T2V
- **[Image-to-Video Guide](docs/i2v-guide.md)** — First-frame based video generation
- **[Reference-to-Video Guide](docs/r2v-guide.md)** — Multi-reference image video generation
- **[Video Edit Guide](docs/video-edit-guide.md)** — Style transfer, element replacement, and fine-tuning
- **[API Reference](docs/api-reference.md)** — Complete API documentation

---

## 🎯 Use Cases

| Vertical | Application |
|----------|-------------|
| 🛒 **E-commerce** | Product showcase videos, costume-drama style product placements |
| 📢 **Advertising** | Brand storytelling, creative ad spots with cinematic quality |
| 🎭 **Short Dramas** | Vertical short drama production with consistent character appearance |
| 📱 **Social Media** | Eye-catching short-form content, meme-style creative videos |
| 🎨 **Creative Design** | Style transfer, artistic video transformation, concept visualization |

---

## 🏗️ Project Structure

```
awesome-happyhorse-use/
├── README.md                 # English project overview
├── README_zh.md              # Full Chinese usage guide
├── LICENSE                   # Apache 2.0 License
├── CONTRIBUTING.md           # Contribution guidelines
├── videos/                   # Video demo library (download via Releases)
└── docs/
    ├── t2v-guide.md          # Text-to-Video detailed guide
    ├── i2v-guide.md          # Image-to-Video detailed guide
    ├── r2v-guide.md          # Reference-to-Video detailed guide
    ├── video-edit-guide.md   # Video Edit detailed guide
    └── api-reference.md      # API reference documentation
```

---

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to improve documentation, report issues, or submit pull requests.

---

## 📄 License

This project is licensed under the Apache License 2.0 — see the [LICENSE](LICENSE) file for details.

---

## 🔗 Related Links

- [HappyHorse: Text-to-Video API Reference](https://help.aliyun.com/zh/model-studio/happyhorse-text-to-video-api-reference)
- [HappyHorse: Image-to-Video (First Frame) API Reference](https://help.aliyun.com/zh/model-studio/happyhorse-image-to-video-api-reference)
- [HappyHorse: Reference-to-Video API Reference](https://help.aliyun.com/zh/model-studio/happyhorse-reference-to-video-api-reference)
- [HappyHorse: Video Edit API Reference](https://help.aliyun.com/zh/model-studio/happyhorse-video-edit-api-reference)
- [HappyHorse 1.0 Creation Guide](https://alidocs.dingtalk.com/i/nodes/14lgGw3P8vxjwogPCp6oqM91V5daZ90D)
- [Alibaba Cloud Model Studio](https://help.aliyun.com/zh/model-studio/)

---

<p align="center">
  <sub>Built with ❤️ for AI video creators everywhere</sub>
</p>
