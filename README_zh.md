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

> 🎉 百炼现已支持体验 HappyHorse 1.0 系列模型

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

> HappyHorse 创作手册：[《HappyHorse 1.0 创作指南》](https://alidocs.dingtalk.com/i/nodes/14lgGw3P8vxjwogPCp6oqM91V5daZ90D?utm_scene=person_space)

### T2V 文生视频

文生视频模型，只需要用户输入一段提示词即可生成。prompt 即正向提示词，用来描述视频中所包含的画面内容和运动过程，描述越准确、越丰富，生成视频的质量越高。

**提示词公式 = 场景 + 主体 + 运动 + 音频**

- **场景**：场景是主体所处的环境，包含背景、前景，可以是物理存在的真实空间或想象出来的虚构场景。
- **主体**：主体是视频内容的主要表现对象，可以是人、动物、植物、物品或非物理真实存在的想象物体。
- **运动**：运动包含主体的具体运动和非主体的运动状态，可以是静止、小幅度运动、大幅度运动、局部运动或整体动势。

| Input (Text) 输入文字 | Output Video 输出视频 |
| --- | --- |
| 动漫风格，国风2d风格，类似玄机科技的画风白发少女，扎发，冷白皮肤，兼具冷艳系长相，画面有颗粒感。丹凤眼，闭眼姿态，表情慵懒平静，举止端庄，极致细节，极致厚涂，琉璃质感，流线笔刷。白色披着的头发，身着藏蓝色绒翎长袍，衣服的元素带有少数民族元素，整体有柔光、质感，氛围梦幻朦胧，低饱和度，富有反差故事感。头上簪着一支蓝色翡翠或者水晶垂吊簪，既显温婉又不失贵气，契合角色气质形象。正脸示人，轻笑一声，语气轻柔又不屑说完"哦？要抓我？"之后，缓缓抬眼，眼中闪炸开一丝微乎其微的光，瞬间镜头从她脸前拉远，身后瞬间乌云密布电闪雷鸣，一条水龙从天而降咆哮龙吟一声，极速飞至她头顶，霸气盘立上空，眼中红光乍现，震耳的嗡鸣声滚滚响起。 | ![t2v_01](videos/t2v_01_guofeng_girl.gif)<br>[▶️ 高清播放](https://github.com/chenxing3060/awesome-happyhorse-use/blob/main/videos/t2v_01_guofeng_girl.mp4) |
| 全景，新海诚风格，时间为盛夏的夜晚，地点是远离尘嚣的宁静小镇边缘山坡。晴朗无云，繁星密布如同璀璨宝石镶嵌于天幕，银河横跨天际，散发着幽蓝深邃的光晕。月光如银纱般轻柔地洒在翠绿的山坡草坪上，使其染上一层淡淡的冷白色。一位身着淡蓝色连衣裙的少女静立于此，微风吹拂着及肩的棕色长发，发丝在月光下泛着柔和的暖棕色光泽。她双手交叠放在身前，抬头仰望着星空，眼中满是对浩瀚宇宙的憧憬和淡淡的孤独。周围萤火虫提着绿幽幽的光在草丛中飞舞，像是在安慰少女的寂寞。山坡上五颜六色的野花在星月光辉与萤火虫光亮交织的光影中轻轻摇曳，画面主色调为蓝紫冷色调，点缀着暖黄的萤火虫光与少女裙装的淡蓝。镜头从夜空缓缓向下移动至少女，带着一种静谧又略带忧伤的氛围。 | ![t2v_02](videos/t2v_02_makoto_shinkai.gif)<br>[▶️ 高清播放](https://github.com/chenxing3060/awesome-happyhorse-use/blob/main/videos/t2v_02_makoto_shinkai.mp4) |
| 主题与动作：一场电影般的武术对决，一方是身穿绿色束腰外衣、背着棕色大皮背包的健壮拟人化野猪，另一方是身着白色武术服、系着蓝色腰带的沉着拟人化公鸡。场景以恭敬的鞠躬开始，随后迅速转入一场快节奏的打斗，包括高踢腿、拳击和空中跳跃。环境与风格：场景是一个充满活力、阳光明媚的Minecraft 风格方块景观，拥有连绵起伏的绿色山丘、风格化的方块树木和湛蓝的天空，点缀着蓬松的白云。动画风格是高质量的3D，具有流畅的动作和动态的摄像机角度（低角度镜头、特写和广角平移）。<br>灯光：明亮、自然的日光，带有微妙的镜头光晕。视觉特效：打斗时，尘土小云从土路上扬起；当他们的攻击命中时，会出现明亮的"火花"或冲击闪光。摄像机：冲击时快速剪切和"抖动镜头"，以强调打击的力量。 | ![t2v_03](videos/t2v_03_minecraft_fight.gif)<br>[▶️ 高清播放](https://github.com/chenxing3060/awesome-happyhorse-use/blob/main/videos/t2v_03_minecraft_fight.mp4) |
| 【场景】奢华的私人飞机机舱内，窗外是壮丽的金红色的云海落日，阳光将机舱渲染成琥珀色。<br>【主体】左侧满头银发的 [年长男性] 身穿高定西装，手持威士忌酒杯，目光如鹰般锐利；右侧的 [年轻男性] 身体微微前倾，眉头微皱，神情既紧张又充满野心。<br>【运动】年长男性轻轻晃动着手中的酒杯，液体挂壁，他身体逼近对方；年轻男性深吸一口气，眼神坚定地回视。镜头缓慢侧推，聚焦两人之间紧席的张力。<br>【音频】[年长男性, 低沉沙哑, 充满威严] 说道："In this world, you either hunt or you become the prey. Which one are you?" [年轻男性, 嗓音紧帮但坚定] 回答："I am the one who pulls the trigger." 背景伴随着飞机引擎深沉的轰鸣声和冰块撞击玻璃杯的清脆声。 | ![t2v_04](videos/t2v_04_private_jet.gif)<br>[▶️ 高清播放](https://github.com/chenxing3060/awesome-happyhorse-use/blob/main/videos/t2v_04_private_jet.mp4) |
| 东方古装写实风格，中近景正面视角。一位身着华丽红色绣花礼服的东方古代女子端坐于富丽典雅的宫廷室内，头戴精致繁复的凤冠，珠宝与垂链在灯火下散发高贵威仪；背景朦胧的宫殿装饰营造出庄重的皇家氛围，整体色调以富丽的红金暖色为主。随着镜头环绕，女子神情由端庄肃穆逐渐转为冷厉：眼神微眯透出狠戾寒光，眉尾下压，嘴角单侧上扬呈冷笑状。就在背景纱幔被无形气流掀起、头饰红珠随动作轻晃的瞬间，她阴簉冷笑："既然你不识抬举，就休怪本宫心狠。"整个画面在注重服饰绣纹与金属质感刻画的同时，展现出极强的皇家仪式感与暗流涌动的戏剧张力。 | ![t2v_05](videos/t2v_05_queen_cold_smile.gif)<br>[▶️ 高清播放](https://github.com/chenxing3060/awesome-happyhorse-use/blob/main/videos/t2v_05_queen_cold_smile.mp4) |
| A cinematic script scene set in a sun-drenched Parisian café, golden afternoon light spilling through arched windows. A sharp-dressed man in a tailored navy suit sits across from an elegant woman in a flowing crimson dress, half-empty coffee cups between them. The air is thick with unspoken tension. He leans forward, voice low and steady: "You knew from the beginning, didnt you? That none of this was real." She holds his gaze without flinching, a ghost of a smile on her lips, slowly stirring her coffee: "Everything was real. Thats exactly what makes it so dangerous." Cinematic wide-angle composition, warm golden hour lighting, shallow depth of field, film grain texture, muted vintage color palette with deep crimson accents, highly detailed wardrobe and facial expressions, noir romantic aesthetic, emotionally charged atmosphere, European street photography style, dramatic storytelling, 35mm film look. | ![t2v_06](videos/t2v_06_paris_cafe.gif)<br>[▶️ 高清播放](https://github.com/chenxing3060/awesome-happyhorse-use/blob/main/videos/t2v_06_paris_cafe.mp4) |
| 生成一段10s韩国男女在咖啡馆谈恋爱对话的片段，恋爱细节丰富，带有分镜 | ![t2v_07](videos/t2v_07_korean_cafe.gif)<br>[▶️ 高清播放](https://github.com/chenxing3060/awesome-happyhorse-use/blob/main/videos/t2v_07_korean_cafe.mp4) |
| 一镜到底，电影质感画面。昏暗的镜头从玻璃外远景缓慢推向近景，一个pizza店里，一个大胡子的白人店员正在烤制披萨。他用铁盘将披萨从烤炉里取出，放在红色的包装盒子里，盖好盒子。最后笑容满面并热情地递给顾客，过肩镜头。音频：烤炉持续的低频喟鸣声，铁盘轻微碰撞的金属声。店员用爽朗热情的美国口音说："Here you go！"，声音洪亮带笑。 | ![t2v_08](videos/t2v_08_pizza_shop.gif)<br>[▶️ 高清播放](https://github.com/chenxing3060/awesome-happyhorse-use/blob/main/videos/t2v_08_pizza_shop.mp4) |
| 纯黑背景，一束戏剧性的顶光照亮操作台... | ![t2v_09](videos/t2v_09_tiny_kitchen.gif)<br>[▶️ 高清播放](https://github.com/chenxing3060/awesome-happyhorse-use/blob/main/videos/t2v_09_tiny_kitchen.mp4) |
| 人群与遮阳伞渐渐散去。海滩回归宁静... | ![t2v_10](videos/t2v_10_peaceful_beach.gif)<br>[▶️ 高清播放](https://github.com/chenxing3060/awesome-happyhorse-use/blob/main/videos/t2v_10_peaceful_beach.mp4) |
| 生成一个连续的延时摄影风格视频，展示一颗柠檬树... | ![t2v_11](videos/t2v_11_lemon_timelapse.gif)<br>[▶️ 高清播放](https://github.com/chenxing3060/awesome-happyhorse-use/blob/main/videos/t2v_11_lemon_timelapse.mp4) |
| 高山雪原，阳光明媚的极寒色调... | ![t2v_12](videos/t2v_12_ski_avalanche.gif)<br>[▶️ 高清播放](https://github.com/chenxing3060/awesome-happyhorse-use/blob/main/videos/t2v_12_ski_avalanche.mp4) |

### I2V 图生视频（首帧）

以一张图片作视频的起始画面（首帧），模型基于该图片内容生成后续的动态视频。上传的图片即为视频第一帧，确保画面起点与你的预期完全一致。

**适用场景**：

- 有一张满意的设计稿或插画，想让它"动起来"
- 需要精确控制视频的开场画面
- 基于产品图、人像照等现有素材快速生成动态展示

**书写建议**：提示词中重点描述"动起来之后发生什么"——动作、运动轨迹、镜头变化等。无需重复描述图片中已有的静态内容，模型会自动识别首帧画面信息。

| Input (Text + Image) 输入文字+首帧图片 | Output Video 输出视频 |
| --- | --- |
| 分镜1 (生成4s)：王爷端坐执卷，丫头从旁侧凑近歪头看他。一个清脆俏皮的女声问：王爷不近女色？一个低沉冷淡的男声回：嗯。暖光透过窗棂，书房雅致。固定机位。分镜2 (生成4s)：丫头指尖轻点王爷脸颊，歪头笑。王爷睫毛微颤，执卷手指收紧，仍垂眸看书。俏皮女声：那我呢？男声停顿后：……你也不行。镜头微推。 | [🎬 i2v_01_period_drama.mp4](videos/README.md#i2v-图生视频) |
| 直播间里，两只猫咪以拟人化形象做搞笑对话，要求写实，使用台湾中年男腔调。银色猫先说话：台词"他说他要当网红"。【1-5秒】画面：银色猫扭头面向金色猫，身子站立，伸着一只前爪，尾巴摇动，动作自然。金色猫说话：台词"靠什么火？"。【5-10秒】画面：金色猫扭头看向银色猫后身子站立，伸着一只爪子，满脸不屑的表情，动作自然。...最后2只猫一起哈哈哈哈哈大笑起来，笑声洪亮，动作表情跟对话内容要严丝合缝。 | [🎬 i2v_02_cat_livestream.mp4](videos/README.md#i2v-图生视频) |
| 【镜头一 · 0–4秒】画面从头盔玻璃面罩内侧的水雾与光斑缓缓对焦——那些光点像是遥远星系的残影，或是某种正在消逝的记忆。红色警报光在她脸上有节律地扫过...色调：深红预警 × 冷蓝深空 × 琥珀肤光。镜头如呼吸般起伏，克制而充满张力。 | [🎬 i2v_03_scifi_helmet.mp4](videos/README.md#i2v-图生视频) |
| 镜头1：高空垂直俯视镜头，银色跑车在S形乡间道路匀速前进，车身线条反射环境光形成流动光带，轮胎与路面接触处扬起薄雾状尘埃，道路两侧树木形成绿色隧道效果。镜头2：镜头和跑车保持同步移动，车头占据画面中心位置，前灯光线在运动中形成光轨，进气格栅细节清晰可见，轮胎转动时轮毂保持稳定旋转，两侧景物形成运动模糊。 | [🎬 i2v_04_sports_car.mp4](videos/README.md#i2v-图生视频) |
| The camera slowly pushes into the astronaut's reflective gold visor, where a miniature world is revealed — the lunar surface and the distant lunar module reflected in breathtaking clarity, like a universe trapped within glass. The camera then eases back as the astronaut takes a single slow, weighted step forward, lunar dust rising in ultra-slow motion under low gravity...The entire sequence carries a cinematic film-grain aesthetic, cold and sacred in tone, with subtle handheld camera tremors evoking the rawness of authentic documentary footage. | [🎬 i2v_05_astronaut_moon.mp4](videos/README.md#i2v-图生视频) |
| The black and white wavy lines and checkered patterns in the background slowly ripple and distort rhythmically, the blue cartoon character sways slightly along with the motion, slowly inserting the card into the yellow and black striped box, electric sparks flicker at the slot of the box, the single eye rotates and looks around, the whole scene pulses with a psychedelic rhythmic energy, camera gently sways left and right. | [🎬 i2v_06_cartoon_card.mp4](videos/README.md#i2v-图生视频) |
| The cute teddy bear as it briskly walks forward across the train station platform, pulling its brown suitcase behind it with a sense of urgency. The bear's mouth moves in perfect lip-sync as it hurriedly says: 'There's no time left, I'm going to be late!' Its expression should appear anxious and determined. The camera follows the bear with a smooth forward tracking shot, maintaining its soft, fuzzy texture and the realistic cinematic lighting. | [🎬 i2v_07_teddy_bear.mp4](videos/README.md#i2v-图生视频) |
| A girl is dancing gracefully. As she spins around in a full turn, the entire scene seamlessly transforms from a cartoon style into a realistic live-action setting. | [🎬 i2v_08_girl_dance.mp4](videos/README.md#i2v-图生视频) |

### R2V 参考生视频（支持图片输入）

HappyHorse 1.0 R2V 支持通过多张图片引导视频生成，包括主体多视角参考、场景图参考、分镜图参考等多种用法。上传图片时，如对图片顺序有要求，请按顺序上传。在提示词中可通过 `[图片1]` `[图片2]` ... `[图片n]` 进行准确指代。

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
| 一张超逼真的4K摄影级画面，场景设定为潮流感满满的播客录音间。背景为蓝灰色几何拼接声学泡沫墙，两侧专业补光灯从侧前方柔和打亮主体...双宠手肘均轻搭桌面，形成稳定的双人主播站位，镜头焦点锐利锁定面部与麦克风区域。基于此高精度底图进行动态口型驱动与表演设计：身份定位为宠物界"吐槽搭子"，对话主题围绕《铲屎官那些"自我感动"的迷惑行为》展开... | [🎬 r2v_01_pet_podcast.mp4](videos/README.md#r2v-参考生视频) |
| Generate a Pixar-style video. The camera orbits around a girl sitting at her desk. She is seated in front of her computer, deep in thought. Mid-orbit, the camera cuts to a close-up of her face, her expression conveying utter puzzlement. Suddenly, her eyes light up and her face instantly relaxes into a delighted smile, showing that she has just struck upon a brilliant idea... | [🎬 r2v_02_pixar_girl.mp4](videos/README.md#r2v-参考生视频) |
| 参考 `[图1]` 中的王爷形象与 `[图2]` 中的丫头形象，两人在古风书房场景中互动。`[图1]` 端坐案前执卷看书，神情清冷专注。`[图2]` 身着浅绿纱衣从旁侧悄悄凑近，歪头凝视 `[图1]` 侧脸，眼神试探又带俏皮...真人古风写真风格，电影级光影质感，面部细节清晰。 | [🎬 r2v_03_period_romance.mp4](videos/README.md#r2v-参考生视频) |
| 电影质感，智能分镜，动作流畅自然，画面无崩坏。分镜1（近景3秒）侧面跟拍。两人起身行走，少女突然停下脚步翻了个白眼...分镜4（中景5秒）正面平视。少年瞬间蔫了，少女绷着脸补刀回应说："收收你的垮脸，组织监控正对着咱呢" | [🎬 r2v_04_young_spies.mp4](videos/README.md#r2v-参考生视频) |
| 生成一段韩漫风格、电影感的短视频。夜晚，雨夜便利店，灯光柔和，情绪安静、治愈、微孤独、温柔。开场镜头展示深夜街角的便利店外景，暖白灯光从玻璃窗透出，外面下着细雨...画面停留在安静、温柔、细腻治愈的情绪中结束。 | [🎬 r2v_05_convenience_store.mp4](videos/README.md#r2v-参考生视频) |

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
| 参考 Image 1，将视频中女主的衣服替换为图中所示的雾霾蓝明制汉服。汉服必须完全贴合女主的身形轮廓和动作姿态，宽大的袖子需跟随她的手臂运动自然摆动...在此过程中，女主的面部表情、发型、肤色、背景环境以及镜头的运镜轨迹必须保持 100% 不变。 | [🎬 edit_01_hanfu_replace.mp4](videos/README.md#video-edit-视频编辑) |
| 参考 Image 1，将视频中正在行驶的白色邮轮替换为图中所示的太空飞船。飞船必须完全遵循原邮轮的行驶轨迹、速度和朝向，严丝合缝地嵌入场景中...在替换过程中，周围的背景、水面、天空以及镜头的运镜轨迹必须保持 100% 不变。 | [🎬 edit_02_spaceship_replace.mp4](videos/README.md#video-edit-视频编辑) |
| 参考 Image 1 中的视觉特征，将视频整体风格转化为传统黑白水墨画风格，把画面中的山脉、雾气、建筑等所有元素全部重塑为具有墨色浓淡变化的写意笔触，在保留原视频运镜轨迹与场景结构完全不变的同时，呈现出一种黑白分明、意境深远的中国水墨视觉效果。 | [🎬 edit_03_ink_wash.mp4](videos/README.md#video-edit-视频编辑) |
| Transform the city into a cyberpunk style. | [🎬 edit_04_cyberpunk.mp4](videos/README.md#video-edit-视频编辑) |
| Transform the entire video into the Minecraft voxel style based on the visual aesthetic of Image 1. Convert all subjects, characters, and the environment into 3D blocks with low-resolution pixelated textures. ...The final result should look like the original scene has been completely rebuilt inside the Minecraft game world. | [🎬 edit_05_minecraft_voxel.mp4](videos/README.md#video-edit-视频编辑) |
| 将视频中猫戴的黑框眼镜替换为参考图中的金丝框眼镜。同时修改猫的动态，让它随着动感的音乐节奏有节奏地左右摇摆头部和身体...在此过程中，必须保持猫的品种外观、背景环境以及镜头的运镜轨迹100%不变。确保金丝眼镜在猫摇摆时始终精准地贴合在它的脸上，并随其头部动作自然移动。 | [🎬 edit_06_cat_glasses.mp4](videos/README.md#video-edit-视频编辑) |

---

## 🐴 应用场景参考

### 电商 - 古装爽剧带货

| Input 模型输入 | Output Video 输出视频 |
| --- | --- |
| 4s 1080P R2V：参考 `[图片1]` 中的王爷形象与 `[图片2]` 中的丫头形象，两人在古风书房暖光场景中互动。王爷端坐案前执卷看书，神情清冷疏离。丫头身着浅绿纱衣从旁侧凑近...案几一角放着 `[图片3]` 中的精致琥珀色香水瓶，红色圆顶瓶盖，瓶身隐约可见 QWEN 字样，在暖光下微微反光。固定机位，真人古风写真风格，电影级光影质感。 | [🎬 case_01_period_perfume_ad.mp4](videos/README.md#应用场景案例) |
| 宋代宫廷内景，华丽但幽暗的宫室，烛光摇曳。`[图1]` 皇后带两名侍女踏入正厅，抬袖掩鼻，轻蔑打量。`[图2]` 贵妃从容从袖中取出蓝色精华液瓶...多镜头切换，保持角色人物一致性。 | [🎬 case_02_palace_skincare_ad.mp4](videos/README.md#应用场景案例) |

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
