# HappyHorse T2V — Text-to-Video Guide

The Text-to-Video (T2V) model generates physically realistic, smoothly-moving video content from text prompts alone. The model is `happyhorse-1.0-t2v`.

---

## Prompt Formula

```
Prompt = Scene + Subject + Motion + Audio
```

| Component | Description |
|-----------|-------------|
| **Scene** | The environment where the subject is situated — includes background and foreground. Can be a real physical space or an imagined fictional setting. |
| **Subject** | The main object of the video content — can be a person, animal, plant, object, or imaginary entity. |
| **Motion** | The specific movements of the subject and non-subject motion states — can be static, small amplitude, large amplitude, local motion, or overall dynamic momentum. |
| **Audio** | Dialogue lines, background sound descriptions, ambient audio cues. |

> **Tip**: The more accurate and detailed your description, the higher the quality of the generated video.

---

## Prompt Examples

### Example 1 — Cinematic Dialogue

```
Scene: Inside a luxury private jet cabin, with a magnificent golden-red sea of clouds at sunset outside the window. Sunlight renders the cabin in amber tones.

Subject: On the left, an elderly silver-haired man in a bespoke suit, holding a whiskey glass, his gaze sharp as an eagle's. On the right, a young man leaning slightly forward, brow furrowed, expression tense yet full of ambition.

Motion: The elder gently swirls his glass, liquid clinging to the sides, leaning in toward the other. The young man takes a deep breath, meeting his gaze with determination. The camera slowly pushes sideways, focusing on the tension between the two.

Audio: [Elderly male, low and gravelly, commanding] "In this world, you either hunt or you become the prey. Which one are you?" [Young male, voice tight but resolute] "I am the one who pulls the trigger." — accompanied by the deep rumble of jet engines and the crisp sound of ice clinking in a glass.
```

### Example 2 — Anime Style

```
Anime style, guofeng 2D art style. A white-haired young woman with tied-up hair, cool-toned pale skin, cold-beauty aesthetic, grainy picture quality. Phoenix eyes, leisurely and calm expression, dignified demeanor. White flowing hair, wearing a navy blue velvet-embroidered robe with ethnic minority elements. Soft lighting, dreamy hazy atmosphere, low saturation, rich narrative contrast. A blue jade or crystal pendant hairpin adds elegance and nobility.
```

### Example 3 — Realistic Product / Scene

```
One continuous take, cinematic quality. Dim lens slowly pushes from exterior glass to interior close-up. Inside a pizza shop, a bearded Caucasian staff member is baking pizza. He retrieves the pizza from the oven with a metal tray, places it in a red box, closes the lid, smiles warmly and hands it to the customer. Over-the-shoulder shot.

Audio: Continuous low-frequency oven hum, slight metallic clink of the tray. Staff member with a hearty, enthusiastic American accent: "Here you go!" — voice loud and cheerful.
```

---

## Best Practices

1. **Be Specific**: Use concrete descriptions instead of vague terms.
2. **Layer Details**: Build from scene → subject → motion → audio for structured prompts.
3. **Specify Style**: Mention art style, lighting, color palette, camera movements.
4. **Control Duration**: Specify how long each segment should be.
5. **Native Multilingual Support**: The model supports 7 languages natively (Chinese Mandarin, Cantonese, English, Japanese, Korean, German, French).

---

## API Quick Reference

```python
payload = {
    "model": "happyhorse-1.0-t2v",
    "input": {
        "prompt": "Your detailed prompt here..."
    },
    "parameters": {
        "duration": 5,
        "resolution": "1080p"
    }
}
```

---

[Back to Home](../README_zh.md)
