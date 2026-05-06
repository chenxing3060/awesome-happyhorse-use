# HappyHorse R2V — Reference-to-Video Guide

The Reference-to-Video (R2V) model accepts multiple reference images and fuses characters/subjects into smooth video through text-driven scene descriptions. The model is `happyhorse-1.0-r2v`.

---

## How It Works

You upload multiple reference images and use text prompts to describe the desired scene. The model uses the images as visual guides for:
- Character appearance (multi-angle photos)
- Scene settings and art style references
- Storyboard keyframe guidance
- Combining multiple elements (character + scene + Logo)

You can reference specific images in prompts using: `[Image 1]`, `[Image 2]`, ..., `[Image n]`. Upload order matters — images are numbered by upload sequence.

> **API Limit**: Up to **9 images** per request.

---

## Use Cases

- **Character Consistency**: Provide multi-angle photos of the same character to maintain appearance across shots
- **Style Reference**: Have a clear scene or art style board — the video faithfully recreates that visual style
- **Storyboard Production**: Upload storyboard frames sequentially and generate accordingly
- **Element Composition**: Combine multiple elements (character + scene + Logo) into a single video

---

## Prompt Examples

### Character + Scene Combo
```
Reference character appearance from [Image 1]. She walks into the scene from [Image 2], opens the door and looks back with a smile. Camera follows. Cinematic quality.
```

### Multi-Angle Character
```
Extract cat features from [Image 1] and [Image 2]. Generate footage of it napping on a windowsill, then startled awake. Maintain consistent fur color and pattern.
```

### Character Turnaround
```
Using the front-facing photo [Image 1] and side profile [Image 2], generate the character turning around to look back. Maintain consistent facial features and hairstyle.
```

### Brand + Style + Character
```
Use [Image 1] as the visual style reference. The character from [Image 2] walks under cherry blossom trees. The Logo from [Image 3] appears at the end. Maintain consistent overall color tone.
```

---

## Example — E-commerce Short Drama

```
4s 1080P R2V: Reference the prince character from [Image 1] and the maid character from [Image 2]. They interact in a period-style study under warm lighting. The prince sits holding a scroll with a cool, aloof expression. The maid in a light green gauze dress leans in from the side, tilting her head toward the prince's profile. Fingertip gently touches her own neck. Eyes probing yet playful. The maid chirps: "The prince doesn't fancy women?" The prince coolly replies: "Hmm." The maid smiles: "Then what about this scent?" On the corner of the desk sits the delicate amber perfume bottle from [Image 3], red round cap, QWEN label faintly visible, glinting in the warm light. Fixed camera, realistic period-drama photo style, cinematic lighting quality.
```

---

## API Quick Reference

```python
payload = {
    "model": "happyhorse-1.0-r2v",
    "input": {
        "reference_images": [
            "https://image-url-1.png",
            "https://image-url-2.png",
            "https://image-url-3.png"
        ],
        "prompt": "Reference [Image 1] character appearance and [Image 2] scene. The character walks into the scene, turns back and smiles. Camera follows."
    },
    "parameters": {
        "duration": 5,
        "resolution": "1080p"
    }
}
```

---

## Tips

1. **Order Matters**: Upload images in the intended reference order
2. **Be Explicit**: Always reference images in your prompt using `[Image N]` notation
3. **Multi-Angle Characters**: Provide front, side, and 3/4 views for best results
4. **Style Images**: Use clear art-style reference images for faithful style transfer
5. **Max 9 Images**: Plan your references accordingly

---

[Back to Home](../README_zh.md)
