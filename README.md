<div align="center">

# Realistic Video Prompting .skill

> *Elevate AI video prompts from "scene descriptions" to "real footage design."*

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-Standard-green)](https://agentskills.io)
[![Runtime](https://img.shields.io/badge/Runtime-Hermes%20·%20Claude%20·%20Codex%20·%20Cursor-blueviolet)](#installation)
[![AI Video](https://img.shields.io/badge/AI%20Video-Seedance%20·%20Sora%20·%20Kling%20·%20Runway%20·%20Veo-ff69b4)](#use-cases)

<br>

**A realism-focused prompt Skill designed for AI video generation.**

It doesn't just help you write "cinematic, high definition, beautiful lighting."
It first determines who shot the footage, what equipment was used, and in what era it was captured, then bakes equipment defects, natural mishaps, environmental audio, and timeline into the prompt.

<br>

[Examples](#examples) · [Installation](#installation) · [What It Solves](#what-it-solves) · [How It Works](#how-it-works) · [Usage](#usage)


English Translation & Adaptation of [zhouwei713/seedance-prompt](https://github.com/zhouwei713/seedance-prompt)

</div>

---

## Examples

### New York Street Morning

User input:

```text
New York street morning
```

The Skill doesn't just output "cinematic morning street, beautiful light." It first establishes the video as real footage with a source:

```text
2020s, a passerby captured a morning commute snippet on a smartphone in vertical orientation at a Manhattan street corner.
```

Then generates a structured video prompt:

```text
Main Character:
A New York office worker around 30 years old, dark gray wool coat, white cotton shirt, black straight-leg trousers, holding a paper coffee cup in left hand, black commute bag slung over right shoulder. Short hair with a few strands blown across the forehead by the morning wind, realistic skin texture with a slight look of fatigue. Maintains consistent identity, clothing, hairstyle, and appearance throughout the entire video.

Location:
A Manhattan street corner at 7:30 AM, with wet asphalt on the sidewalk, yellow taxis, steaming manhole covers, breakfast carts, stainless steel coffee pots, crosswalk buttons, subway stairwell entrances, and just-risen sunlight.

Camera Style:
Smartphone vertical shooting, 9:16 vertical composition, slight over-sharpening and HDR processing feel, up-and-down bobbing while walking, brief exposure fluctuation when light shifts from shadow to sunlight. No horizontal orientation. No tripod stabilization. No professional lighting.

Timeline:
00:00-00:02 Camera lifts from the subway exit, first capturing the wet sidewalk, then panning to the street corner.
00:02-00:04 The office worker walks out of the subway entrance, white steam from the manhole cover drifting past his legs.
00:04-00:06 He stops at the crosswalk waiting for the red light, sunlight falling between two buildings onto his coat shoulder, exposure suddenly brightening then recovering.
...
```

This type of prompt makes the model understand the footage identity: a real city morning that existed on a stranger's phone, not a commercial or tourism promo.

---

### Korean Old Neighborhood Everyday

User input:

```text
A Korean old neighborhood, afternoon, a girl walking through an alley, wants a very real home video feel
```

The Skill switches to a 2000s consumer DV equipment pack:

```text
Moderate digital compression artifacts, faded colors, soft contrast, slight sensor noise, strong handheld shake, frequent autofocus hunting, exposure fluctuation when moving between sunlight and shadow.
No stabilization. No cinematic camera movement. No modern color grading.
```

It also adds imperfect events into the timeline:

```text
00:04-00:06 The girl passes a clothesline, white shirts swaying gently in the wind, the camera lagging slightly behind her turn.
00:06-00:08 A cat walks past the alley entrance, she stops and looks down at it, autofocus briefly landing on the cat then returning to her face.
00:12-00:14 The camera drops to film the concrete ground and the shooter's shoe tips, then suddenly cuts to black, as if the camera was turned off.
```

This kind of realism comes from defects and life details; piling on more style words would only push the image back toward AI demo footage.

---

## What It Solves

Many AI video prompts look complete but still look fake at a glance.

Common problems:

- Camera movement too smooth, like auto-generated demo footage
- Frames too clean, lacking real equipment defects
- People look posed, actions lack life logic
- Scenes automatically become commercials, cafes, shopping streets
- Audio doesn't correspond to visuals
- No temporal progression between shots, just a collage of pretty frames
- Characters change faces, clothes, or hairstyles across shots

Realistic video prompts must specify the footage source: who shot it, why they shot it, what equipment they used, and what small mishaps occurred during filming.

---

## Use Cases

- Seedance, Sora, Kling, Runway, Veo and other text-to-video / image-to-video prompts
- Realistic street photography, home video, DV nostalgia, VHS, Super 8 film, vertical phone, surveillance camera
- City mornings, neighborhood alleys, travel snapshots, slices of life, documentary observation
- Creators who want to remove the overly clean, overly stable, overly commercial color grading from AI video
- People who want to expand a vague scene idea into a complete 10-to-15-second video prompt
- Short video workflows requiring character consistency, timelines, environmental audio, and negative constraints

---

## How It Works

This Skill breaks a video idea into 7 parts.

```text
1. Main Character: Who appears in the frame, how appearance and clothing stay consistent
2. Location: Specific space, era elements, lighting and environmental details
3. Visual Style: Realism level and footage temperament
4. Camera Style: Equipment type, frame defects, operational mishaps, negative constraints
5. Timeline: What happens in each shot within 10 to 15 seconds
6. Audio: How on-site and environmental sounds correspond to the visuals
7. Goal: What this footage should ultimately look like
```

It has three built-in reference libraries.

### Equipment Aesthetic Defect Packs

Different equipment produces different kinds of realism.

```text
2000s consumer DV: compression artifacts, fading, handheld shake, autofocus hunting
VHS home camcorder: scan lines, color bleeding, timestamps, low resolution
Super 8 film: film grain, vignetting, scratches, 18fps stutter
Smartphone vertical: 9:16, HDR processing, electronic stabilization, finger brushing lens edge
Surveillance camera: high-angle top-down, low frame rate, timestamp, silent
```

### Atmosphere Translation Table

It translates abstract words into filmable phenomena.

```text
Warm: sunlight through leaves, fabric swaying gently, steam from a cup, person tucking hair behind ear
Lonely: large negative space, empty street, blue-white fluorescent light, echoing footsteps
Tense: flickering lights, corridor shadows, person frequently looking back, distant metallic clanging
Lived-in: vendor actions, steam and smoke, overlapping conversations, bicycle bells
```

### De-AI Self-Check

Check before output:

```text
Is the character consistent
Is the location specific
Does the camera section have physical defects
Does the timeline have imperfect events
Does audio correspond to visuals
Has commercial-style camera movement and color grading leaked in
```

---

## Installation

### Method 1: Install to Hermes

```bash
git clone https://github.com/zhouwei713/seedance-prompt.git \
  ~/.hermes/skills/creative/realistic-video-prompting
```

Restart Hermes, or start a new session, then use:

```text
realistic-video-prompting
```

### Method 2: Use as a General Skill

If you don't use Hermes, you can also place `SKILL.md` directly into Claude, Codex, Cursor, OpenCode, or other Agent environments that support Skills / long prompts.

### Method 3: Use as Prompt Methodology Reference

Read directly:

```text
SKILL.md
references/camera-aesthetics.md
references/atmosphere-dictionary.md
references/anti-ai-checklist.md
```

---

## Usage

You can say things like:

```text
New York street morning, real phone snapshot feel, 15 seconds
```

```text
Korean old neighborhood, a girl walking through an alley in the afternoon, like a 2000s DV home video
```

```text
Late night convenience store entrance, someone waiting for a bus, a bit lonely, want surveillance camera feel
```

```text
Help me make this video prompt more realistic, remove the AI feel
```

---

## Repository Structure

```text
.
├── README.md
├── SKILL.md
├── references/
│   ├── anti-ai-checklist.md
│   ├── atmosphere-dictionary.md
│   └── camera-aesthetics.md
└── LICENSE
```

---

## Design Philosophy

Realism doesn't come from adding more "cinematic," "ultra realistic," "8K."

Realism comes from footage identity: who is filming, what equipment they're using, whether the shooter has experience, how the on-site light and sound change, and what small imperfections appear in the frame.

If you don't write these things, the video model will automatically fill in what it does best: stable, clean, symmetrical, commercially graded, demo-footage-like.

This Skill's value is in codifying the judgment process for "real footage," so that every AI video generation first passes through equipment, era, space, action, sound, and mishaps.

---

## License

MIT License.