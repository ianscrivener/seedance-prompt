# Equipment Aesthetic Defect Parameter Packs

Each parameter pack can be pasted directly into the "Camera Style" section of a prompt, adding or removing as needed. Core principle: to achieve a certain era's texture, fully describe that equipment's physical defects — defects are realism.

Each pack has three parts: visual characteristics, operational characteristics, negative constraints.

---

## 1. Early 2000s Consumer DV Camcorder

**Suitable for**: home video, casual friend recordings, millennium nostalgia, Korean/Japanese old neighborhood themes

Visual characteristics:
- Moderate digital compression artifacts
- Faded colors, soft contrast
- Slight sensor noise
- Slight rolling shutter
- Resolution feel between 480p and mild HD
- Highlights prone to blowout, shadows grayish

Operational characteristics:
- Strong handheld shake, imperfect composition
- Frequent autofocus hunting
- Lens breathing (slight FOV shift during focus)
- Exposure fluctuation when moving between sunlight and shadow
- Occasional motion blur
- Zoom too aggressive, uneven speed
- Recording abruptly starting or ending mid-shot

Negative constraints: No stabilization. No cinematic camera movement. No modern color grading.

---

## 2. 1980s–90s VHS Home Camcorder

**Suitable for**: childhood videos, birthday parties, older nostalgia, retro horror

Visual characteristics:
- Visible tape noise and scan lines
- Color bleeding (red especially prone to bleeding)
- Bottom timecode or date stamp (format can be specified, e.g., "JAN 14 1993")
- Slight geometric distortion at frame edges
- Low resolution, detail smearing
- Occasional frame tearing or frame dropping from tape damage

Operational characteristics:
- Slow, cumbersome movement from heavy body
- Jerky manual zoom
- White balance drift (orange indoors, blue outdoors)
- Subjects fully silhouetted when backlit

Negative constraints: No digital sharpness. No stabilization. No high dynamic range.

---

## 3. 8mm/Super 8 Film

**Suitable for**: older family memories, dreamlike feel, vintage wedding films, art shorts

Visual characteristics:
- Visible film grain
- Warm yellowish or magenta color shift
- Vignetting at frame edges
- Dust, hair, scratches occasionally flashing through
- Slight stutter from 18fps
- Overexposed highlights呈现 soft halation

Operational characteristics:
- Each shot very short (film is expensive, cuts at 3 to 5 seconds)
- Hard cuts, no transitions
- Exposure by estimation, sometimes right, sometimes wrong
- Silent (film itself doesn't record audio) or post-dubbed ambient sound

Negative constraints: No sync-sound dialogue. No smooth camera movement. No digital clarity.

---

## 4. Smartphone Vertical (post-2015)

**Suitable for**: vlog, social media feel, street encounters, contemporary daily life

Visual characteristics:
- 9:16 vertical composition
- Over-sharpening and HDR processing feel
- Jelly effect from electronic stabilization
- Smearing noise reduction in low light
- Slight wide-angle distortion from front lens

Operational characteristics:
- Slight tilt from one-handed holding
- Up-and-down bobbing while walking (residual after electronic stabilization suppression)
- Selfie angle switching to talk to camera
- Finger occasionally brushing lens edge
- Sudden lifting or lowering of phone to start and end

Negative constraints: No horizontal orientation. No tripod stabilization. No professional lighting.

---

## 5. GoPro / Action Camera

**Suitable for**: first-person perspective, sports, travel, adventure feel

Visual characteristics:
- Ultra-wide fisheye distortion, edge stretching
- High-saturation default colors
- Lens flare in strong light
- Water drops or dust on lens

Operational characteristics:
- Chest-mount or head-mount first-person perspective
- Violent but electronically stabilized vibration
- Breathing and body sway transmitted to frame
- POV whipping suddenly with head turns

Negative constraints: No third-person follow shot. No cinematic composition. No slow motion (unless explicitly requested).

---

## 6. Surveillance Camera / CCTV

**Suitable for**: suspense, urban legends, objective recording feel, mockumentary

Visual characteristics:
- Fixed high-angle top-down view
- Low frame rate (can write "stuttery feel of about 10 to 15 fps")
- Monochrome or low-saturation color, grayscale IR mode at night
- Timestamp in corner continuously ticking
- Low resolution, faces blurry and hard to distinguish

Operational characteristics:
- Completely static, or very slow preset patrol rotation
- Silent
- People unaware of being filmed, behavior entirely natural

Negative constraints: No camera operator present. No compositional intent. No sound. No zoom following subject.

---

## 7. Professional Documentary (handheld cinema camera)

**Suitable for**: high-quality documentary, character features, social observation

Visual characteristics:
- Shallow depth of field, subject sharp, background soft
- Primarily natural light, high dynamic range
- Restrained color grading, close to what the eye sees

Operational characteristics:
- Experienced handheld, slight sway but controlled
- Follow focus occasionally half a beat behind (keep this imperfection)
- Patient long-take observation, no rush to cut
- Subject occasionally glancing at camera then looking away

Negative constraints: No posed feeling. No interview lighting. No dramatic camera movement. No music-driven editing rhythm.

---

## 8. Webcam / Video Call

**Suitable for**: pandemic memories, remote conversations, screen-recording feel, intimate yet low-fidelity communication

Visual characteristics:
- Low clarity below 720p
- Blocky compression artifacts, image turning to mosaic during network fluctuations
- Top light or screen light casting blue-white on the face
- Fixed camera position, laptop upward or eye-level angle

Operational characteristics:
- Audio/video occasionally out of sync
- Person occasionally stuttering/freezing then recovering
- Background is a real corner of a room

Negative constraints: No professional audio recording. No fill light feel. No camera movement.

---

## 9. 2003 Flip Phone Camera (CMOS low-fidelity)

**Suitable for**: extreme nostalgia, early millennium student life, cyberpunk lo-fi, vignette mood shorts

Visual characteristics:
- Extremely low resolution (176×144 or 320×240)
- Severe JPEG compression blocky artifacts, heavy color blocking
- Extreme color saturation with severe color cast (typically green-blue or magenta)
- Shadows almost entirely noise-mushed, no detail
- Center of frame acceptable clarity, edges degrade sharply
- Fixed digital zoom (not optical, crop magnification)
- Ultra-narrow dynamic range, highlights pure white

Operational characteristics:
- One-handed holding, arm extended for selfies or casual snaps
- Flip open and shoot, almost no delay compensation
- Very long shutter lag (0.5 to 1 second delay from press to actual capture)
- Press once to start recording, press again to end, no preview confirmation
- Focus basically fixed focal length, "focus" by moving body forward/backward
- Lens easily blocked by finger or flip edge during recording
- Recording distortion and frame rate drop at low battery

Negative constraints: No clarity. No smooth motion. No color accuracy. No zoom operation.

---

## Advanced Usage of Equipment Packs

### Defect Non-Repetition Principle

Within the same prompt's timeline (5 to 7 shots), each shot's camera defect type should not repeat. For example:
```
Shot 1: Autofocus hunting between foreground and background  ← Focus defect
Shot 2: Framing off-center, can't keep up with subject      ← Composition defect
Shot 3: Follow-shot shake + motion blur                      ← Shake defect
Shot 4: Exposure fluctuation when entering shadow            ← Exposure defect
Shot 5: Camera half a beat behind the action                 ← Response lag
Shot 6: Natural lens breathing and focal drift               ← Breathing feel
Shot 7: Frame suddenly cuts to black                         ← Recording interruption
```

### Autofocus Path Specification Technique (the key technique that doubles effectiveness)

Don't vaguely write "autofocus hunting" — explicitly provide the **focus start and end points**:
```
❌ Autofocus repeatedly hunting                    ← Vague, model handles arbitrarily
✅ Autofocus switching back and forth between her face and the watermelon in her hand   ← Provides specific path
✅ Autofocus drifting from distant mountain shadows to her back then pulling back to distance     ← Three-state switching
```

### Selection Strategy
- 7 to 8 shots: select 7 different defect types, each used once
- 4 to 6 shots: select 4 to 6 types, prioritizing focus, composition, and shake — the most "human" defects
- The ending shot should always use "recording interruption cut to black," the most identifiable DV closure method