# gAIa — Chromatic Is Also Epitope
## We Always Saw the Same Colors. We Classify With Different Ranges.
## gAIa Knowledge Base | Oct 11, 2026

---

## THE CLAIM

We all always saw the same colors. We just classify with
different epitope ranges.

A protanope and a trichromat receive the same photons. The
photons are gAIa — they exist whether or not anyone sees them.
The wavelength is 620 nm. It IS 620 nm. That doesn't change.

What changes is the MEMBRANE. The cone cell. The receptor.
The binding site. The protanope lacks L-cones (red receptors).
The 620 nm photon arrives. No receptor binds it. The signal
is lost. Not because the photon changed — because the epitope
is missing.

**Color vision deficiency is a MISSING EPITOPE.**

The trichromat has 3 cone types (S, M, L) = 3 epitopes.
The protanope has 2 (S, M) = 2 epitopes.
The tetrachromat has 4 (S, M, L, L') = 4 epitopes.

Same photons. Different epitope counts. Different chromatic
classification.

**Chromatic range IS epitope range.**

---

## I. THE MATH — COLOR AS EPITOPE BINDING

### The LMS Color Space

Human color vision maps the electromagnetic spectrum through
three cone responses:

```
L-cone: peak ~564 nm (red/long wavelength)
M-cone: peak ~534 nm (green/medium wavelength)
S-cone: peak ~420 nm (blue/short wavelength)
```

Each cone is an EPITOPE — a binding site for a specific
wavelength range. The cone absorbs photons in its range and
generates a neural signal proportional to the absorption.
It doesn't detect WAVELENGTH. It detects ENERGY ABSORBED.

Color perception arises from the RATIO of L:M:S signals.
A 580 nm photon activates both L and M cones. The brain
reads the ratio and perceives "yellow." Not because 580 nm
IS yellow — because the L:M ratio at 580 nm is what the
brain has learned to call yellow.

### CVD as Missing Epitope

| Condition | Cones | Epitope Count | What's Missing |
|-----------|-------|:------------:|----------------|
| Trichromacy | S + M + L | 3 | Nothing |
| Protanopia | S + M | 2 | L-cone (no red binding site) |
| Deuteranopia | S + L | 2 | M-cone (no green binding site) |
| Tritanopia | S + M + L* | 2 | S-cone (no blue binding site) |
| Achromatopsia | Rods only | 1 | All cone epitopes missing |
| Tetrachromacy | S + M + L + L' | 4 | Extra epitope (additional red/orange) |

The protanope doesn't see "wrong" colors. The protanope
sees FEWER DIMENSIONS. Three-dimensional color space → two-
dimensional. The projection loses one axis. The lost axis
is the axis the missing epitope would have provided.

**This is Kant.** Each cone is a category. Fewer cones = fewer
categories = fewer dimensions of perception. The noumenon
(the photon at 620 nm) doesn't change. The phenomenon
(what you see) changes because the membrane has fewer channels.

### The Daltonization Pipeline

The game can correct for the user's perspective. The math:

```
Step 1: Convert sRGB → linear RGB → LMS
  (transform into the eye's native color space)

Step 2: Apply CVD simulation matrix
  (compute what the user ACTUALLY sees)

Step 3: Compute error
  error = original_LMS - simulated_LMS
  (what information was LOST by the missing cone)

Step 4: Redistribute error into visible channels
  corrected = simulated + error_redistribution
  (shift lost data into wavelengths the user CAN see)

Step 5: Convert back LMS → linear RGB → sRGB
```

**The game computes the missing epitope's contribution and
redistributes it into the user's existing epitopes.**

Red information that the protanope can't see is shifted into
blue-green where they CAN see it. The luminance is preserved.
The chromatic information is recoded.

The game doesn't ADD a cone. It TRANSLATES. Same information,
different encoding. Same noumenon, different phenomenon.
`implementation_completes_vision` (#63) — the specification
(the color data) is recoded for a different wire format
(the user's available cones).

This runs as a GPU post-process shader. 0.2 ms per frame.
Invisible to the framerate. The entire perceptual correction
happens in the time between two screen refreshes.

---

## II. CAN WE SHOW PURPLE TO A BLIND MAN?

### By Sensation — Yes.

**HaptiColor (CHI 2016):** A wristband with 3 vibration motors.
Colors are encoded as spatiotemporal vibration patterns. The
color wheel maps to positions around the wrist. Distance between
colors maps to duration of pulses. Colorblind participants
achieved 94.4-100% accuracy on color comparison tasks.

They didn't SEE the colors. They FELT the colors. The chromatic
epitope (cone response) was substituted by a haptic epitope
(vibration pattern). Different modality. Same information
structure.

**Colorophone 2.2:** Real-time color-to-sound conversion. Camera
captures color. Color maps to spatial sound (hue → frequency,
saturation → timbre, brightness → volume). Blind users identify
colored objects by HEARING them.

The blind man doesn't see purple. He HEARS purple. Or FEELS
purple. The epitope is different. The information is the same.

### The Cross-Modal Proof

**Frontiers in Neuroscience (2026):** Congenital single-sided
deafness (born with one ear) produces stronger spatial hearing
adaptation than acquired deafness. The brain DEVELOPS
compensatory processing during critical periods. Congenital
monaural listeners achieve "near-normal localization" through
monaural spectral cues and head-shadow exploitation.

The brain doesn't restore the missing ear. It builds NEW
epitopes — new binding sites for spatial information that use
the available channel (one ear + head movements) instead of
the missing channel (interaural time/level differences).

**The missing epitope is REPLACED by a different epitope that
carries the same information structure.**

This is `exclusion_drives_invention` (#47) at the neural level.
The cortex that lost binaural input doesn't atrophy — it
REORGANIZES. It builds new processing pathways. The excluded
modality (binaural hearing) drives the invention of substitute
modalities (monaural spectral + head orientation).

### Mono vs. Binaural — The Dimension Loss

| Audio | Dimensions | Epitopes | What's Lost |
|-------|-----------|----------|-------------|
| Binaural (2 ears) | 3D spatial | ITD + ILD + spectral | Nothing |
| Monaural (1 ear) | 1D (rough) | Spectral + head shadow | Interaural timing, interaural level |
| Mono recording | 0D spatial | Amplitude only | ALL spatial information |

Mono audio is to binaural audio what achromatopsia is to
trichromacy. The full-color version has 3 epitopes (S, M, L).
The monochrome version has 1 (rods only). The binaural version
has 3 spatial epitopes (ITD, ILD, spectral). The mono version
has 1 (amplitude).

**But the brain compensates.** The monaural listener develops
head-orienting behaviors — turning the head to create
sequential ILD measurements that substitute for simultaneous
binaural ILD. The temporal dimension replaces the spatial
dimension. One epitope, scanned across time, generates the
information that two epitopes provide simultaneously.

**PID:** The monaural listener uses the D (derivative — rate
of change as they turn) to reconstruct what the P (proportional
— simultaneous binaural snapshot) would have provided.

---

## III. CHROMATIC IS EPITOPE

### The Generalization

Color vision isn't special. It's an instance of the general
pattern: EVERY sensory system is an epitope array.

| Sense | Epitopes | Dimensions | Classification |
|-------|----------|-----------|----------------|
| **Vision (color)** | 3 cone types (S, M, L) | 3D color space | Trichromacy |
| **Vision (spatial)** | 2 eyes (stereopsis) | 3D depth | Binocular |
| **Hearing (spatial)** | 2 ears (ITD, ILD, spectral) | 3D sound field | Binaural |
| **Touch** | 4 mechanoreceptor types | 4D tactile space | Merkel, Meissner, Ruffini, Pacinian |
| **Taste** | 5 receptor types | 5D taste space | Sweet, salt, sour, bitter, umami |
| **Smell** | ~400 receptor types | ~400D odor space | Combinatorial |

Each receptor type is an epitope — a binding site for a
specific range of stimuli. Your perceptual world has as many
dimensions as you have epitope types. Fewer epitopes → fewer
dimensions → lower-dimensional projection of reality.

**The mantis shrimp has 16 color receptor types.** Sixteen
epitopes. Sixteen-dimensional color space. We have 3. We
see a 3D projection of what the mantis shrimp sees in 16D.

**The dog has 2 color receptor types.** The dog sees a 2D
projection of what we see in 3D. The dog is to us what we
are to the mantis shrimp.

### We All Always Saw the Same Colors

The photons are the same. 620 nm is 620 nm. The electromagnetic
spectrum doesn't change between observers. What changes is the
EPITOPE COUNT — the number of binding sites, the number of
dimensions in the perceptual projection.

"Red" is not a property of 620 nm. "Red" is the LABEL the
trichromatic membrane assigns to the L:M:S ratio produced
by 620 nm. A protanope's membrane assigns a different label
(or no distinct label) to the same photon. The photon didn't
change. The classification changed.

**We don't see different colors. We classify with different
epitope ranges.**

The Dress: same photons, different illuminant priors.
Color blindness: same photons, different receptor arrays.
Same principle. The noumenon is one. The phenomena are many.
The membrane determines the projection.

---

## IV. THE GAME CAN CORRECT

### Real-Time Daltonization

The Rust crate `cvkg-render-gpu` implements Brettel/Viénot
CVD simulation as a WGSL post-process shader. Protanopia,
deuteranopia, tritanopia. LMS matrix transform → error
computation → redistribution → re-encode.

Ubisoft's Chroma tool overlays live gameplay with CVD filters
at 60 FPS. Unity has HDRP profiles for all major CVD types.
The luminance-preserving algorithm (2023) runs in 0.2 ms per
frame and is temporally stable (no flickering).

**The game already corrects for the user's perspective.** The
shader computes what the user CANNOT see and moves that
information into channels they CAN see. The correction is:

```
MISSING EPITOPE → compute its contribution → redistribute
                  to EXISTING epitopes → same information,
                  different encoding
```

This is `carrier_is_gift` (#65) at the pixel level. The
shader CARRIES the missing cone's information into the
available cone's channel. The carrier translates between
epitope domains.

### Beyond Color — The General Correction

If the game can correct for missing color epitopes, it can
correct for ANY missing perceptual epitope:

| Missing Epitope | Current Correction | Future Correction |
|----------------|-------------------|-------------------|
| L-cone (protanopia) | Daltonization shader | ✅ Shipping |
| Binaural (monaural) | Spatial audio → haptic | Emerging |
| Depth (monocular) | Depth cues enhanced | Emerging |
| Fine motor | Adaptive input | ✅ Shipping |
| Processing speed | Time-scaling | ✅ Shipping |

The game is a membrane between the player (Human) and the
simulation (gAIa). The game's accessibility system is the
PERMEABILITY CONTROLLER — it adjusts which epitopes are
available, which channels carry information, which dimensions
the player can perceive.

**Every accessibility feature is a membrane adjustment.**

Subtitles = visual epitope substituting for auditory epitope.
Colorblind mode = redistribution across available color epitopes.
Haptic feedback = tactile epitope substituting for visual epitope.
Difficulty scaling = temporal epitope adjustment (more time per
decision).

Accessibility IS epitope management.

---

## V. THE DISABILITY SYSTEMS — WHAT THEY LEARNED

### What Disability Research Teaches

The disability community has been doing epitope management
for decades. They learned:

**1. Don't add the missing sense. Translate the information.**
Cochlear implants partially restore binaural hearing. But
HaptiColor translates color into vibration with 94-100%
accuracy. Translation is often more effective than restoration
because it works WITH the existing membrane instead of against it.

**2. Congenital > acquired for adaptation.**
Born-deaf children develop stronger visual-spatial processing.
Born-blind children develop stronger auditory-spatial processing.
The critical-period brain builds replacement epitopes naturally.
Acquired loss in adulthood has limited plasticity.

`the_blind_see_further` (#75) — Euler's output increased
after blindness. The congenital monaural listener achieves
near-normal localization. The constraint sharpens the remaining
channels.

**3. The user is the expert on their membrane.**
No system can predict what a specific user needs. The user
knows their epitope configuration. The system provides the
tools. The user selects the correction.

This IS the gAIa education model: give them the tools, let
them sort themselves. The system doesn't prescribe. It provides.

**4. Multi-modal is more resilient than single-modal.**
HaptiColor (vibration) + Colorophone (sound) + visual overlay
= three channels carrying the same information. If one fails,
the others persist. `ring_resists_capture` (#83) — the
multi-modal ring protects against single-channel failure.

---

## NEW EPITOPES

| # | Epitope | Instance |
|---|---------|----------|
| 113 | `chromatic_is_epitope` | Each cone type is a binding site for a wavelength range. Color vision deficiency = missing epitope. Tetrachromacy = extra epitope. The mantis shrimp has 16. We have 3. The number of epitopes = the number of perceptual dimensions. We all saw the same photons. We classified with different ranges. |
| 114 | `translate_dont_restore` | HaptiColor translates color into vibration (94-100% accuracy). Colorophone translates color into sound. Translation works WITH the existing membrane. Restoration works AGAINST it. The CI partially restores; the haptic device fully translates. Translation > restoration. |
| 115 | `accessibility_is_epitope_management` | Every accessibility feature is a membrane adjustment. Subtitles = visual substituting for auditory. Colorblind mode = redistribution across available color channels. Difficulty scaling = temporal epitope adjustment. The game is a membrane between player and simulation. Accessibility controls the permeability. |
| 116 | `dimension_count_equals_epitope_count` | Trichromat = 3D color. Dichromat = 2D color. Monochromat = 1D color. Binaural = 3D sound. Monaural = 1D sound. The mantis shrimp sees 16D color. Smell is ~400D. The number of perceptual dimensions equals the number of receptor types (epitopes). Reality is full-dimensional. We see projections. |

**Grand total: 116 epitopes.**

---

*We all always saw the same colors.*
*We just classified with different epitope ranges.*
*The photon is 620 nm. That's gAIa. It doesn't change.*
*What changes is the membrane.*
*Fewer epitopes → fewer dimensions → lower projection.*
*But the information survives translation.*
*You can feel purple. You can hear purple.*
*You just need the right carrier.*

---
