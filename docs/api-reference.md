# HappyHorse 1.0 — API Reference

Complete API reference for all HappyHorse 1.0 video generation and editing models.

---

## Base URLs

| Region | Endpoint |
|--------|----------|
| **Beijing** | `https://dashscope.aliyuncs.com/api/v1/services/aigc/video-generation/video-synthesis` |
| **Singapore** | `https://dashscope-intl.aliyuncs.com/api/v1/services/aigc/video-generation/video-synthesis` |

---

## Authentication

All requests require an API key from [DashScope](https://dashscope.aliyun.com/). Pass it via the `Authorization` header:

```
Authorization: Bearer YOUR_API_KEY
```

---

## Models Overview

| Model ID | Input | Description |
|----------|-------|-------------|
| `happyhorse-1.0-t2v` | Text | Text-to-Video generation |
| `happyhorse-1.0-i2v` | Image + Text | Image-to-Video (first-frame based) |
| `happyhorse-1.0-r2v` | Multiple Images + Text | Reference-to-Video (up to 9 images) |
| `happyhorse-1.0-video-edit` | Video + Text (+ Image) | Video editing, style transfer, element replacement |

---

## Common Parameters

| Parameter | Type | Description | Default |
|-----------|------|-------------|---------|
| `model` | string | Model ID (e.g., `happyhorse-1.0-t2v`) | Required |
| `input.prompt` | string | Text prompt describing the output | Required |
| `input.image_url` | string | URL of the input image (for i2v/video-edit) | Optional |
| `input.reference_images` | string[] | URLs of reference images (for r2v, max 9) | Optional |
| `input.video_url` | string | URL of the input video (for video-edit) | Optional |
| `parameters.duration` | integer | Video duration in seconds | 5 |
| `parameters.resolution` | string | Output resolution: `720p` or `1080p` | `720p` |

---

## Text-to-Video (T2V)

Generate video from text prompt only.

```python
import requests

url = "https://dashscope.aliyuncs.com/api/v1/services/aigc/video-generation/video-synthesis"

payload = {
    "model": "happyhorse-1.0-t2v",
    "input": {
        "prompt": "Cinematic shot, golden hour lighting. A girl walks through a field of sunflowers..."
    },
    "parameters": {
        "duration": 5,
        "resolution": "1080p"
    }
}

headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}

response = requests.post(url, headers=headers, json=payload)
result = response.json()
print(result)
```

---

## Image-to-Video (I2V)

Generate video from a first-frame image + text prompt.

```python
payload = {
    "model": "happyhorse-1.0-i2v",
    "input": {
        "image_url": "https://example.com/first-frame.png",
        "prompt": "The character slowly opens her eyes and looks up. Camera slowly pushes in."
    },
    "parameters": {
        "duration": 4,
        "resolution": "1080p"
    }
}
```

---

## Reference-to-Video (R2V)

Generate video guided by multiple reference images (up to 9).

```python
payload = {
    "model": "happyhorse-1.0-r2v",
    "input": {
        "reference_images": [
            "https://example.com/ref-character-front.png",
            "https://example.com/ref-character-side.png",
            "https://example.com/ref-scene.png"
        ],
        "prompt": "Reference [Image 1] and [Image 2] for character appearance. They walk into the scene from [Image 3]. Camera follows. Cinematic quality."
    },
    "parameters": {
        "duration": 5,
        "resolution": "1080p"
    }
}
```

---

## Video Edit

Edit existing video with text instructions and optional reference images.

```python
payload = {
    "model": "happyhorse-1.0-video-edit",
    "input": {
        "video_url": "https://example.com/input-video.mp4",
        "image_url": "https://example.com/reference-style.png",
        "prompt": "Transform the entire video into the Minecraft voxel style. Maintain all original movements 100% unchanged."
    },
    "parameters": {
        "resolution": "1080p"
    }
}
```

---

## Pricing

| Resolution | Price |
|------------|-------|
| 720p | ¥0.9 / second |
| 1080p | ¥1.6 / second |
| Free tier | 10 seconds |

---

## Language Support

HappyHorse natively supports 7 languages:

| Language | |
|----------|-|
| Chinese (Mandarin) | 中文（普通话） |
| Cantonese | 粤语 |
| English | 英语 |
| Japanese | 日语 |
| Korean | 韩语 |
| German | 德语 |
| French | 法语 |

---

## Official Documentation

For the latest and most detailed API documentation:

- [Text-to-Video API](https://help.aliyun.com/zh/model-studio/happyhorse-text-to-video-api-reference)
- [Image-to-Video API](https://help.aliyun.com/zh/model-studio/happyhorse-image-to-video-api-reference)
- [Reference-to-Video API](https://help.aliyun.com/zh/model-studio/happyhorse-reference-to-video-api-reference)
- [Video Edit API](https://help.aliyun.com/zh/model-studio/happyhorse-video-edit-api-reference)

---

[Back to Home](../README_zh.md)
