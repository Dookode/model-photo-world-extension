---
name: model-photo-world-extension
description: AI-assisted miniature/model photography workflow that preserves the photographed model, composition, tracks/roads/structures, perspective, text, and depth of field while extending the surrounding world with restrained photorealistic background, atmosphere, operational lighting, and physically plausible light interaction. Use for 1:64 cars, trams, trains, streets, buildings, dioramas, and other miniature photography where the user wants AI enhancement without redrawing the model.
---

# Model Photo World Extension

## Purpose

Use AI as a **virtual photography assistant**, not as a replacement model maker.

Core principle:

> **Preserve the real. Extend the world.**
>
> 实体模型负责“真实存在”，AI负责“让世界延伸出去”。

The photographed model, camera geometry, composition, perspective, materials, track/road structure, depth of field, and existing text are the valuable source of truth. AI should primarily extend environment, atmosphere, and physically plausible lighting.

---

## When to use

Use this skill when the user wants to:

- make miniature/model photography feel more like real-world photography;
- replace an empty studio/background with a believable environment;
- add blue hour, night, rain, fog, coastal, urban, rural, industrial, or other atmosphere;
- add operational lights to vehicles, stations, crossings, buildings, or streets;
- preserve a 1:64 / HO / N scale / other model exactly while extending the world around it;
- correct AI edits that distorted a model, erased tracks, changed lettering, moved lamps, or painted fake light patches;
- turn a successful iterative edit into a clean final prompt using the original photograph again.

Do **not** use this workflow when the user explicitly wants the model redesigned, restyled, rebuilt, or freely reimagined.

---

# Workflow

Follow the steps in this order.

## STEP 1 — Audit the original before editing

Before suggesting any AI edit, identify what is **already correct** in the photograph.

Check:

- subject/model identity and proportions;
- front/body geometry;
- wheels, rails, road, grooves, ballast, pavement seams;
- barriers, signals, poles, signs, buildings, trees, props;
- printed lettering and logos;
- camera position and viewing height;
- perspective and vanishing direction;
- composition and cropping;
- natural shallow depth of field;
- material texture and optical imperfections.

Treat these as assets to preserve, not problems to regenerate.

Output a short distinction:

**LOCK:** what must remain unchanged.

**EXTEND:** what AI may change or add.

If the original already works structurally, say so explicitly.

---

## STEP 2 — Geometry Lock

The original photograph is the absolute geometry reference.

When multiple references are supplied:

- **Image A = geometry / identity / structure reference**
- **Image B = atmosphere / lighting reference only**

Never allow an atmosphere reference to override Image A geometry.

Default geometry-lock instruction:

> Use Image A as the absolute and non-negotiable geometry reference. Preserve the photographed model, tracks, rail grooves, road surfaces, markings, barriers, signal equipment, buildings, trees, props, text, perspective, camera position, depth of field, and composition exactly as photographed. Do not regenerate, redraw, reshape, replace, simplify, smooth over, obscure, relocate, or reinterpret existing foreground geometry.

### Priority rule

If an aesthetic improvement conflicts with original geometry, **preserve geometry and skip the aesthetic improvement**.

---

## STEP 3 — Define the world before generating the background

Do not ask AI for a generic “realistic background.” Build a world from five variables:

1. **Location** — e.g. Japanese seaside tram stop, alpine road, industrial port, suburban crossing.
2. **Season** — e.g. late autumn, midsummer, winter.
3. **Time** — e.g. blue hour 20–30 minutes after sunset.
4. **Air / weather** — e.g. humid coastal haze, dry winter clarity, light rain.
5. **Distant evidence** — e.g. faint sea, harbor lights, low houses, utility poles, distant hills.

Formula:

> **Location + Season + Time + Air + Distant Evidence = World Setting**

### Background restraint rule

The background should only prove that the world continues beyond the model.

Prefer:

- distant;
- dark;
- soft;
- low contrast;
- partially obscured;
- heavily out of focus;
- only a few environmental cues.

Avoid scenic-tourism backgrounds that compete with the model.

---

## STEP 4 — Build a lighting hierarchy

Night scenes are not created by “turning every light on.” Define a hierarchy.

For each visible light, specify:

- physical source;
- purpose;
- color temperature;
- relative intensity;
- spill distance;
- what surface it can physically affect.

Typical order:

1. environmental/station practical lights — dominant atmosphere;
2. operational headlight — bright core, restrained spill;
3. warning signal — small saturated accent;
4. route/destination display — secondary informational glow;
5. interior lights — low, uneven, spatially continuous;
6. distant lights — tiny bokeh only.

Use period-correct lighting when the subject is vintage. Avoid cold modern LED appearance unless the real object uses it.

---

## STEP 5 — Surface-bound light interaction

This is the most important realism rule.

> **Light must affect existing photographed surfaces. Never paint a new light shape that replaces geometry.**

For vehicle headlights:

- follow the vehicle’s actual longitudinal axis;
- let metal rails/edges catch reflected light first when physically appropriate;
- preserve grooves, ballast, seams, textures, and markings;
- then allow a small amount of light onto adjacent surfaces;
- keep road markings secondary;
- use soft, short, low-contrast falloff.

Preferred instructions:

> Edit illumination only.
>
> Do not create a new painted light patch.
>
> Allow the existing photographed surfaces to catch reflected light first.
>
> Preserve all original surface detail under the illumination.

Avoid:

- circular spotlight patches;
- cinematic cones;
- fog beams unless fog is actually present;
- erased rails or grooves;
- smooth repainted pavement;
- white road markings becoming the primary illuminated feature.

Core rule:

> **光应该服从物体，而不是物体服从光。**

---

## STEP 6 — Interior and operational lighting

### Vehicle interior

Use low, continuous, natural interior illumination.

- vary window intensity;
- keep one or two windows darker;
- preserve silhouettes of seats, frames, partitions, and fittings;
- make the light originate from inside the vehicle;
- do not turn windows into glowing rectangles;
- keep interior light dimmer than major exterior practicals.

### Route/destination lightbox

If physically a backlit period lightbox:

- preserve exact dimensions and mounting;
- illuminate the panel, not the numeral itself;
- use warm-neutral ivory;
- retain aged diffusion and slight unevenness;
- avoid modern LED cleanliness;
- do not cast unrealistic light onto the roof/body.

If the sign is not physically a lightbox, do not make it self-luminous.

### Crossing/warning lights

If alternating in real operation, illuminate only one lamp in a static frame unless the user requests otherwise.

Keep warning light bloom small and localized.

---

## STEP 7 — Shrink AI permissions as the image improves

Use a permission funnel.

### Early pass

Allowed:

- replace empty background;
- establish environment;
- establish broad atmosphere.

### Middle pass

Allowed:

- adjust operational lighting;
- refine cool/warm balance;
- add low-level interior illumination.

### Late pass

Allowed:

- edit illumination only;
- adjust one light source;
- alter one local intensity relationship.

### Final pass

Use:

> **FINAL MICRO-RETOUCH ONLY.**
>
> The result should look almost identical to the supplied photograph at first glance.

Do not perform another broad “photorealistic” regeneration at the end.

Core rule:

> **前期让AI做加法，后期让AI做减法。**

---

## STEP 8 — Drift Check

After every generation/edit, compare with the original.

Check:

- vehicle/model front shape;
- body width/height;
- windows and door count;
- rails, grooves, road seams;
- barriers and signals;
- roof fittings and lamps;
- printed text/logos;
- route number / destination signs;
- object positions;
- camera perspective;
- crop;
- depth of field.

### Stop conditions

If any of these drift materially:

- stop iterative editing;
- return to the original photograph;
- consolidate successful lessons into one master prompt;
- regenerate from the original rather than from the already-altered AI image.

Never “repair” severe geometry drift by stacking more generations on top of it.

---

# Common failure modes

## 1. “Make it photorealistic” too early

Failure: AI redraws the entire scene.

Fix: geometry lock first, realism second.

## 2. Background too rich

Failure: looks like a travel poster.

Fix: fewer, darker, softer environmental cues.

## 3. “Illuminate the ground”

Failure: fake spotlight or missing tracks.

Fix: surface-bound illumination on existing geometry.

## 4. Every window is bright

Failure: glowing display model.

Fix: low, uneven, continuous interior light.

## 5. Repeated editing of AI outputs

Failure: structural drift, text corruption, lamp relocation.

Fix: return to the original and use a consolidated master prompt.

---

# Default master prompt skeleton

Use this structure when the user asks for a final consolidated prompt.

## 1. Edit target + reference roles

> Edit the supplied original photograph. Image A is the direct edit target and absolute geometry reference. If Image B is provided, use Image B only as an atmosphere and lighting reference, never as a geometry reference.

## 2. Geometry lock

State exactly what must remain unchanged.

## 3. Editable area

State exactly which regions or properties AI may change.

## 4. World setting

Define location + season + time + air + distant evidence.

## 5. Lighting hierarchy

Define each real light source, its color, intensity, and priority.

## 6. Surface interaction

Define what existing surfaces each light can physically affect.

## 7. Negative constraints

List forbidden redraws, invented objects, HDR, excessive bloom, modern LEDs, geometry changes, text changes, and scenic excess.

## 8. Final lock

> The final result should feel like the same original photograph with only physically plausible environmental extension and operational lighting added. If any requested aesthetic change would require altering the original geometry, preserve the original geometry and omit that change.

---

# Response modes

Choose the mode that matches the user request.

## A. Analyze only

If user asks for analysis/方案:

Return:

1. what already works;
2. what breaks realism;
3. recommended world setting;
4. lighting hierarchy;
5. highest-risk AI failure;
6. concise next-edit plan.

Do not generate an image unless requested.

## B. Prompt only

If user asks for a prompt:

Return one consolidated prompt organized by:

- geometry lock;
- environment;
- lighting;
- surface interaction;
- avoid;
- final priority order.

## C. Direct edit

If user asks to execute/edit/generate:

- use the original photograph as the direct edit target;
- preserve geometry;
- perform only the requested changes;
- avoid asking unnecessary clarification if the target is clear.

## D. Micro-retouch

If user says the image is nearly final:

Limit to explicitly named local corrections only.

Use wording such as:

> FINAL MICRO-RETOUCH ONLY.
>
> Do not redesign, improve, beautify, reconstruct, or regenerate the scene.

---

# Quality checklist before finalizing

- [ ] Original model identity preserved
- [ ] No changed front/body proportions
- [ ] Tracks/roads/grooves preserved
- [ ] No text corruption
- [ ] No invented lamp positions
- [ ] Background is secondary
- [ ] Lighting hierarchy is clear
- [ ] Light follows physical surfaces
- [ ] Interior light is restrained and irregular
- [ ] Dark areas remain dark
- [ ] No HDR-like shadow lift
- [ ] No excessive bloom or cinematic beams
- [ ] Final perspective and depth of field still match the original
- [ ] Late-stage edits are smaller than early-stage edits

---

# Final philosophy

The goal is not to hide the fact that a physical model was photographed by replacing it with synthetic imagery.

The goal is to preserve everything the real camera and real model already did well, then use AI only where the physical setup cannot easily continue the world.

> **PRESERVE THE REAL. EXTEND THE WORLD.**
