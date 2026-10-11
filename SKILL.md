---
name: realistic-video-prompting
description: Write realistic, de-AI-ified, documentary-quality structured video prompts for AI video generation models (Seedance, Sora, Kling, Runway, Veo, etc.). Use this skill whenever the user wants to generate AI video prompts, optimize existing video prompts, or pursue "realistic," "home video," "phone footage," "DV," or "surveillance camera" video effects, or mentions Seedance, text-to-video, or video prompts. Even if the user merely describes a scene or mood they want to shoot, use this skill to transform it into a complete prompt.
version: 1.1.0
author: zhouwei713
license: MIT
metadata:
  hermes:
    tags: [ai-video, prompt, realistic-video, seedance, kling, veo, runway, sora]
---

# Realistic Video Prompt Generator

Transforms a vague idea from the user ("I want a video with the everyday feel of a Korean neighborhood") into a high-density, executable, de-AI-ified, structured video prompt that looks like real footage.

## Core Philosophy

The essence of a high-quality video prompt is answering one question: **Who shot this footage, with what equipment, in what era, and for what purpose?**

Once the "footage source identity" is established, all details can be derived. A DV casually shot by a friend in 2005 will be shaky, out of focus, and may suddenly turn off; a 2024 vlogger's vertical phone video will have a beauty-filter look and face-the-camera talking; a 90s surveillance camera has no audio, a top-down angle, and low frame rate.

The second key insight: **AI models have strong default aesthetics** (cinematic camera movement, perfect composition, commercial color grading, clean frames). To achieve realism, you must proactively disable these default behaviors with negative constraints and embed "imperfect events" into the timeline.

## Workflow

### Step 1: Establish the Four Essential Elements (all required)

If the user hasn't been clear, ask these four questions (can be combined into a single inquiry):

1. **Shooter identity**: Who is filming? A friend, family member, passerby, vlogger, surveillance camera, documentary crew, or an unmanned fixed camera?
2. **Equipment and era**: DV, VHS, 8mm film, iPhone, GoPro, surveillance, professional cinema camera? Which era?
3. **Subject and scene**: Who is being filmed? Where? What time of day?
4. **Emotional goal**: Warm nostalgia, lonely detachment, tense unease, calm healing?

If the user has already provided enough information, infer directly and confirm your understanding in one sentence before output.

### Step 2: Generate section by section using the seven-part template

Output strictly in the following order, each section as an independent block, with no information bleeding between sections:

```
Main Character → Location → Visual Style → Camera Style → Timeline → Audio → Goal
```

Writing rules for each section:

**1. Main Character**
- Only write visualizable concrete features: age range, makeup, color/material/fit of each clothing item, shoes, accessories, hairstyle details (including flyaway hair, bangs, and other small features)
- No abstract adjectives (stylish, attractive, elegant)
- Add one line of skin/texture description (e.g., "realistic skin texture")
- Add one line of personality/temperament (to drive body language)
- **Must end with a consistency lock sentence**: "Maintains consistent identity, clothing, hairstyle, and appearance throughout the entire video"

**2. Location**
- Start with time of day + region + scene type
- List 8 to 12 specific environmental elements (potted plants, clotheslines, utility poles, tree shadows, etc.); elements should mutually corroborate the same world
- Add dynamic light/shadow descriptions (tree shadows moving, cloud shadows passing)
- **End with negative constraints**: exclude commercial elements the model tends to add (shops, ads, crowds, cafes)

**3. Visual Style**
- Define the realism level with 4 to 6 short phrases: e.g., "ultra-realistic documentary realism, authentic spontaneous behavior, natural body language, unscripted everyday slice-of-life feel, strong environmental authenticity"

**4. Camera Style**
- This is the core section for de-AI-ifying. Consult `references/camera-aesthetics.md`, select the matching equipment's "defect parameter pack" and write it in completely
- Principle: translate the equipment aesthetic into 6 to 10 specific physical phenomena (focus hunting, exposure fluctuation, rolling shutter, compression artifacts, etc.)
- **Must end with a triple negative constraint**: no stabilization, no cinematic camera movement, no modern color grading (adjust per equipment)

**5. Timeline**
- Total length 10 to 15 seconds, cut into 5 to 7 shots, each shot 2 to 3 seconds, using `00:00–00:02` format
- Each shot contains three layers: subject action + environmental response (wind, light, animals, passersby) + **one imperfect event**
- Select imperfect events from the checklist in `references/anti-ai-checklist.md`, and do not repeat the same type across the 7 shots
- Actions must have a life-logic chain (sitting → walking into an alley → encountering a cat → hanging laundry), not unrelated shot collages
- **The ending must have a closure method**: sudden cut to black (like powering off), walking out of frame, camera dropping to film the ground, etc., matching the shooter identity

**6. Audio**
- First declare the mode (ambient environmental sound only / on-site recording + ambient)
- List 6 to 9 specific sound elements, corresponding one-to-one with scene elements (if there's a cat, there's a meow; if there's a clothesline, there's fabric rustling)
- **End with triple negation**: no music, no sound design, no narration (adjust as needed)

**7. Goal**
- One-sentence soul anchor, format: "Capture XX, as if a XX's XX, ending with 4 to 6 adjectives"
- This sentence is the model's basis for trade-offs when details conflict; it must be self-consistent with all preceding sections

### Step 3: Self-check (mandatory before output)

Check item by item against `references/anti-ai-checklist.md`:

- [ ] Does the character section have a consistency lock sentence?
- [ ] Does the location section exclude commercial elements?
- [ ] Does the camera section have at least 6 physical defect descriptions + 3 "no XX"?
- [ ] Does every shot in the timeline have an imperfect event? Are there repeats?
- [ ] Does the ending have a closure method?
- [ ] Do the audio section's sound elements correspond to visual elements?
- [ ] Does the full text have any leaked abstract adjectives (beautiful, cinematic, premium)?
- [ ] Is the goal sentence self-consistent with the shooter identity/equipment/era?

### Step 4: Delivery

- Output the complete prompt (in Chinese or English per user need; English typically produces more stable results when fed to the model, so proactively offer an English version)
- Attach a brief explanation: what is the "footage source identity" setting of this prompt, and which knobs to adjust when the user wants changes (equipment pack, time period, mood words, closure method)

## Reference Files

- `references/camera-aesthetics.md`: Defect parameter packs for 9 equipment/media types, must-read when writing the camera style section
- `references/atmosphere-dictionary.md`: Translation table from mood words to concrete visual phenomena, consult when writing location and timeline
- `references/anti-ai-checklist.md`: AI-tell source list, negative constraint sentence library, imperfect event library, must-read for self-checking

## Variant Handling

- **User wants non-realistic style** (animation, cyberpunk, commercial): The seven-part structure remains unchanged, but the camera section switches to the corresponding medium's aesthetic parameters (animation frame rate, commercial cinematography language), and negative constraints change to exclude elements unwanted for that style
- **User wants multiple characters**: Each character gets an independent description block, each with its own consistency lock sentence, and interactions between characters are made explicit in the timeline
- **User only wants to optimize an existing prompt**: First diagnose which sections are missing or insufficient using the seven-part framework, provide a diagnostic table, then rewrite
- **Videos longer than 15 seconds**: Recommend splitting into multiple prompts for segment generation, keeping the character section completely identical across segments to maintain continuity