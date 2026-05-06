# HappyHorse Video Edit — Style Transfer & Element Replacement Guide

The Video Edit model performs AI-powered intelligent editing on existing video, applying precise modifications without generating from scratch. Use text prompts to describe modification intent, optionally with reference images for visual guidance. The model is `happyhorse-1.0-video-edit`.

---

## How It Works

Instead of generating video from scratch, this model takes an existing video as input and intelligently modifies it based on your instructions. You can:
- Describe changes via **text prompts** only
- Provide **reference images** for visual guidance
- Combine **both approaches** for maximum control

---

## Use Cases

| Scenario | Example |
|----------|---------|
| **Style Transfer** | Convert realistic footage to anime style, day scene to sunset, modern city to cyberpunk |
| **Element Replacement** | Swap backgrounds, change clothing colors, replace objects with reference images |
| **Style Reference** | Have a target-style reference image, adjust entire video's visual appearance to match |
| **Object Swap** | Replace a specific element in the video with a reference image's specific object |
| **Secondary Refinement** | Fine-tune AI-generated video, adjust motion or frame details |

---

## Prompt Writing Formula

```
Modify WHAT + Preserve WHAT
```

**Be explicit about both**:
- What to change: style, elements, colors, atmosphere
- What to keep: character actions, camera tracking, facial expressions, background

> The more specific the description, the more precisely the model executes the edit and avoids accidentally changing parts you want to keep.

---

## Prompt Examples

### Style Transfer
```
Transform the entire video into a cyberpunk style.
```

```
Convert video to traditional black-and-white ink wash painting (水墨画) style. Reshape all mountains, mist, and architecture into ink-brush strokes with varying density. Preserve the original camera tracking path and scene structure 100%. Present a stark black-and-white, deeply atmospheric Chinese ink-wash visual effect.
```

```
Transform the entire video into the Minecraft voxel style. Convert all subjects, characters, and environment into 3D blocks with low-resolution pixelated textures. Ensure lighting and colors match the blocky world. Original movements, character actions, and camera tracking path must remain 100% unchanged. Final result should look completely rebuilt inside the Minecraft game world.
```

### Element Replacement
```
Replace the background from modern city to ancient-style street. Green flagstone road, distant pavilions with flying eaves. Maintain character actions unchanged.
```

```
Reference Image 1. Replace the female lead's clothing with the fog-blue Ming dynasty hanfu shown in the reference image. The clothing must perfectly conform to her body contours and movement posture. Wide sleeves must naturally sway with arm movements. Embroidered crane and floral patterns' position, proportion, and detail must strictly follow Image 1. Facial expression, hairstyle, skin tone, background, and camera tracking path must remain 100% unchanged.
```

```
Reference Image 1. Replace the white cruise ship moving in the video with the spaceship shown in the reference image. The spaceship must completely follow the original ship's trajectory, speed, and orientation, seamlessly embedding into the scene. Ensure the spaceship's surface lighting, reflection, and shadows match the original video environment's light source. Surrounding background, water surface, sky, and camera tracking path must remain 100% unchanged.
```

### Weather / Atmosphere
```
Add falling snow effect. Ground gradually covers with thin snow. Overall color tone leans cold.
```

### Art Style Reference
```
Reference the visual style from [Image 1]. Convert the overall video into Ghibli animation style. Bright, soft colors. Maintain original motion trajectories.
```

---

## API Quick Reference

```python
payload = {
    "model": "happyhorse-1.0-video-edit",
    "input": {
        "video_url": "https://your-video-url.mp4",
        "image_url": "https://your-reference-image.png",  # Optional
        "prompt": "Replace the car with a spaceship from the reference image. Maintain all movements and background 100% unchanged."
    },
    "parameters": {
        "resolution": "1080p"
    }
}
```

> **Note**: The `video_url` should be a publicly accessible video URL.

---

## Tips

1. **Be explicit about preservation**: Always state what must NOT change
2. **Style fidelity**: Use reference images for best style-matching results
3. **Element precision**: The more detailed the description of the replacement, the better the fit
4. **Complex edits**: Break down complex edits into layered modifications

---

[Back to Home](../README_zh.md)
