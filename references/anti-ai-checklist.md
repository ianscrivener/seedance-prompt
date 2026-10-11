# De-AI Checklist: AI Default Behaviors, Negative Constraint Sentence Library, Imperfect Event Library

## I. AI Video Model Default Aesthetics (will appear if not proactively disabled)

| AI Default Behavior | Problem Caused | Corresponding Negative Constraint |
|---|---|---|
| Cinematic smooth camera movement (dolly, crane feel) | Instantly exposes AI look | No cinematic camera movement |
| Frame stable as if on tripod | Contradicts handheld setting | No stabilization |
| Modern commercial color grading (teal-orange, high contrast) | Destroys era feel | No modern color grading |
| Perfect centered composition | Too "designed," doesn't look like casual shooting | Imperfect composition, off-center framing |
| Auto-adds shops, cafes, crowds, billboards to scenes | Destroys quiet residential atmosphere | No shops, ads, cafes, crowds, or commercial activity |
| Auto-adds background music | Destroys documentary feel | No music. No sound design. No narration |
| Strong performance feel, staring into camera and posing | Doesn't look candid | Authentic spontaneous behavior, unscripted everyday slice-of-life feel |
| Over-smooth skin, airbrushed feel | Mannequin look | Realistic skin texture |
| Character drift across shots (face/clothes change) | Consistency breakdown | Maintains consistent identity, clothing, hairstyle, and appearance throughout the entire video |
| Lighting too evenly perfect | Studio feel | Natural light, exposure fluctuation when moving between sunlight and shadow |

## II. Imperfect Event Library (select one per timeline shot, no repeats across the entire piece)

**Shooter's mistakes**:
1. Autofocus repeatedly hunting between subject and foreground/background
2. Framing drifting off-center because the operator tries to keep up with the subject
3. Camera lagging slightly behind key moments (person already turned before camera catches up)
4. Zoom too aggressive, pushed too far then pulled back
5. Strong shake and motion blur during walk-and-follow shooting
6. Finger or strap briefly covering a corner of the lens
7. Camera struggling to focus but briefly failing, frame breathing

**Environmental interventions**:
8. A gust of wind blowing loose hair or clothing edges
9. Cloud shadow passing, exposure fluctuating accordingly
10. Stray cat/dog/pigeon entering the frame, subject responding naturally
11. Someone off-screen greeting the subject, subject turning to respond
12. Sunlight filtering through leaves, flickering on/off on the face
13. Passersby inadvertently crossing in front of the lens

**Subject's natural behavior**:
14. Noticing the camera, showing a small genuine smile then looking away
15. Talking interrupted by ambient sound, breaking into a laugh
16. Unconscious small gestures like adjusting hair, tucking hair behind ear
17. Changing mind mid-action (reaching for a cup but wiping the table first)

**Closure methods** (must choose one for the ending):
18. Recording suddenly cuts to black mid-shot, as if the camera was turned off
19. Subject walks out of frame, camera lingers on empty scene for two seconds
20. Camera drops to film the ground/feet, then cuts
21. Someone calls the shooter's name, camera shakes toward the sound source and cuts

## III. Item-by-item self-check before output

- [ ] Character section: all visualizable features? Zero abstract adjectives? Ends with a consistency lock sentence?
- [ ] Location section: 8+ specific elements? Has dynamic lighting? Ends by excluding commercial elements?
- [ ] Visual style section: 4 to 6 realism-defining phrases?
- [ ] Camera section: at least 6 physical defect phenomena? Ends with at least 3 "no XX"? Matches the set equipment era?
- [ ] Timeline: 5 to 7 shots? Each shot has three-layer structure (action + environment + imperfect event)? Imperfect events don't repeat? Actions have life-logic chain? Ending has closure?
- [ ] Audio section: sound elements correspond one-to-one with visual elements? Ends with triple negation?
- [ ] Goal section: one-sentence anchor self-consistent with the whole?
- [ ] Full text scan: any escaped "beautiful," "cinematic," "premium," "gorgeous" abstract words?

## IV. Common Failure Modes

1. **Section information bleeding**: Writing camera movement into the character section, writing music into the visual section. Strictly partition.
2. **Too many imperfect events**: Stuffing three mishaps into one shot makes it fake instead. One per shot.
3. **Negative constraints fighting positive descriptions**: Writing "no cinematic camera movement" earlier, then "slow dolly shot" in the timeline. Cross-check after writing.
4. **Audio-visual mismatch**: No cat in the frame but cat meowing in audio. Check item by item.
5. **Anachronism**: Smartphone, shared bike, or modern ad screen appearing in a 2000s DV scene. Check era of all environmental elements.
6. **Missing closure**: Video stopping on an "in-progress" action, looking like truncated footage rather than a complete recording.

---

## V. Advanced Techniques

### Scene Unit Four-Element Formula (a more precise model replacing the "three-layer structure")

Each timeline shot consists of four layers. Missing any one reduces realism:

| Element | Function | Required? |
|---------|----------|-----------|
| ① Spatial positioning | "Where" — a specific location anchor | Required |
| ② Subject action chain | "What" — 2 to 3 consecutive actions forming a behavior flow (not a single action) | Required |
| ③ Environmental dynamics | "How the environment responds" — immediate changes in wind, light, animals, pedestrians | Optional |
| ④ Camera defect | "This shot's mishap" — one of focus/composition/shake/exposure/lag | Required |

Example — comparing two ways of writing:
```
❌ She sits by the wall, wind blowing her hair.                    ← Insufficient information density; model may auto-fill with posed footage
✅ Outside the small house entrance. She sits on a low concrete wall, using both hands to lift and adjust her ponytail.   ← Has spatial positioning
   A gust of wind blows loose strands of hair. Camera struggles to maintain focus.              ← Has environmental dynamics + camera defect
```

### 2-Second Rhythm Rule (timeline granularity control)

The realism of DV-style fragmentation comes from the "short shot, rapid progression" rhythm, not each shot being a full wide shot:

| Total Duration | Recommended Shots | Per-Shot Duration |
|----------------|-------------------|--------------------|
| 15 sec | 7 | ~2 sec |
| 10 sec | 5 | ~2 sec |
| 8 sec | 4 | ~2 sec |
| 4-5 sec | 2 | ~2 sec |

Shots exceeding 3 seconds weaken the DV footage feel and slide toward "carefully shot."

### Real-time Speed Check (cardinal sin of DV aesthetics)

Home DV almost never uses slow motion. Check in the timeline:

```
❌ She slowly turns her head, hair drifting through the air in slow motion    ← Slow motion, not DV behavior
✅ She turns her head, hair blown loose by the wind, motion blur from the quick head turn  ← Real-time speed + natural blur
```

The only exception: if the equipment pack explicitly sets "phone slow-motion feature" or "film overcranked shooting."

### Environmental Interaction Density Check

The secret of real DV footage is not how good-looking the subject is, but the environment's continuous "response" to the subject. Check how many interactions exist between subject and environment in each shot:

```
Low density: She walks on the road.                      ← Subject is in space, but environment is dead backdrop
Medium density: She walks on the road, wind blowing her skirt.            ← Environment responded to subject
High density: She walks on the road, wind blowing her skirt and hair,
              sunlight flickering through leaves on her face,         ← Multiple environmental elements responding simultaneously
              she squints and adjusts her sun hat position.           ← Subject makes a secondary response to environment
```

Goal: at least 1 environmental response per shot, 2+ is better.

### Autofocus Path Specification Method

After declaring autofocus issues in the "Camera Style" section, for each shot in the timeline that uses a focus defect, **explicitly write the focus start and end points**:

```
❌ Autofocus repeatedly hunting              ← Model interpretation varies widely
✅ Autofocus switching back and forth between her face and the watermelon in her hand  ← Model knows which two objects to focus between
✅ Autofocus drifting from distant tree shadows to her back then pulling back to distant sky  ← Three-state path, more realistic
```