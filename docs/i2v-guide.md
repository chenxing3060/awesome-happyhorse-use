# HappyHorse I2V — Image-to-Video Guide

The Image-to-Video (I2V) model takes a first-frame image as the starting point and generates subsequent dynamic video from it, guided by a text prompt. The model is `happyhorse-1.0-i2v`.

---

## How It Works

The uploaded image serves as the **first frame** of the generated video. The model then generates all subsequent frames based on the content of the image and your text prompt instructions. This ensures the opening frame is exactly what you want.

---

## Use Cases

- You have a finished design draft or illustration and want to make it "come alive"
- You need precise control over the opening frame of your video
- You want to quickly generate dynamic showcases from existing product photos, portraits, or other assets

---

## Prompt Writing Tips

**Focus on "what happens after it starts moving":**
- Actions and motion trajectories
- Camera movements and transitions
- Character interactions

**Do NOT repeat static content already in the image** — the model automatically recognizes the first-frame content. Just describe the dynamics.

---

## Examples

### Example 1 — Short Drama (Chinese Period Style)

```
Shot 1 (4s): The prince sits holding a scroll, the maid leans in from the side tilting her head to look at him. A crisp, playful female voice asks: "The prince doesn't fancy women?" A low, cool male voice replies: "Hmm." Warm light filters through the window lattice. Elegant study room. Fixed camera.

Shot 2 (4s): The maid's fingertip lightly touches the prince's cheek, tilting her head with a smile. The prince's eyelashes tremble slightly, his fingers tighten on the scroll, but he still looks down, reading. Playful female voice: "What about me?" Male voice, after a pause: "...Not even you." Camera gently pushes in.
```

### Example 2 — Sci-Fi Cinematic

```
[Shot 1 · 0–4s] The image slowly focuses from inside the helmet glass visor's mist and light specks — those light points resemble the afterimage of a distant galaxy, or a fading memory. Red alert light rhythmically sweeps across her face, dyeing her skin in alternating deep red and shadow pulses. Her eyes are closed, eyelashes gently trembling, as if receiving a frequency only she can hear in the darkness. The camera approaches the visor glass at an extremely slow pace, trying to penetrate that transparent barrier.

Tone: Deep red alert × Cool blue deep space × Amber skin glow. The camera breathes like a rhythm, restrained and full of tension.
```

### Example 3 — Car Commercial

```
Shot 1: High-altitude vertical overhead shot. A silver sports car travels at constant speed on an S-shaped country road. The car body lines reflect ambient light forming flowing light bands. Thin mist-like dust rises where tires meet the road surface. Trees on both sides form a green tunnel effect.

Shot 2: Camera moves in sync with the sports car. Headlight rays form light trails in motion. The grille details are clearly visible. Wheel hub maintains stable rotation during tire rotation. Side scenery creates motion blur.
```

---

## API Quick Reference

```python
payload = {
    "model": "happyhorse-1.0-i2v",
    "input": {
        "image_url": "https://your-image-url.png",
        "prompt": "Describe the motion that follows from this starting frame..."
    },
    "parameters": {
        "duration": 4,
        "resolution": "1080p"
    }
}
```

> **Note**: The `image_url` should be a publicly accessible image URL. For local images, upload to your preferred hosting service first.

---

[Back to Home](../README_zh.md)
