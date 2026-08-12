# model-photo-world-extension

> **Preserve the real. Extend the world.**

A reusable AI-assisted workflow for extending miniature/model photography into believable environments while preserving the original subject, geometry, perspective, materials, and photographic character.

## Core Philosophy

> Physical models provide the reality.
>
> AI extends the world around them.

实体模型负责“真实存在”，AI 负责“让世界延伸出去”。The photographed subject, camera geometry, composition, perspective, materials, depth of field, and existing text remain the source of truth. AI may extend the background, environment, atmosphere, and physically plausible lighting around them.

This is not a one-click “make the model real” generator. It is a geometry-first editing workflow for preserving what already works in a physical model photograph.

## Scope

This Skill can be used for:

- 1:64 car model photography;
- tram and train model photography;
- railway scenes;
- miniature streetscapes;
- architectural models;
- port and industrial scenes;
- road scenes;
- miniature night scenes;
- other model photography where the goal is to preserve a real physical photograph and extend its environment.

It is not primarily intended for:

- completely regenerating the main subject;
- substantially changing the composition;
- illustration, anime, or poster-style repainting;
- rescuing source images whose subject is severely blurred or whose geometry is already distorted.

## What It Does

- **Geometry Lock** — preserves the photographed subject, structures, text, camera perspective, composition, and depth of field.
- **Editable Area Definition** — states exactly what AI may change and what must remain untouched.
- **World Setting** — defines location, season, time, air/weather, and distant environmental evidence.
- **Lighting Hierarchy** — ranks real light sources by purpose, color, intensity, and spill.
- **Physical Light Interaction** — makes illumination follow existing photographed surfaces instead of repainting geometry.
- **Drift Check** — compares each edit with the original and stops accumulated structural drift.
- **Micro-retouch Lock** — limits late-stage edits to explicitly named local corrections.

## Workflow

1. **Geometry Lock** — audit the original and lock the subject, geometry, perspective, composition, text, and photographic character.
2. **Editable Area** — define the exact regions or properties AI may modify.
3. **World Setting** — specify location, season, time, air/weather, and distant evidence.
4. **Lighting Hierarchy** — define only physically present or explicitly requested light sources and their priorities.
5. **Surface Interaction** — bind light to existing rails, roads, walls, materials, seams, and textures.
6. **Drift Check** — compare the result with the original; return to the source image if geometry drifts.
7. **Micro-retouch** — shrink permissions and make only local, named corrections near the final stage.

## Key Rule

> **If an aesthetic improvement requires changing the original geometry, skip the aesthetic improvement.**

> 如果某项美化需要破坏原始几何，就宁可不执行这项美化。

## Recommended Usage

```text
$model-photo-world-extension Analyze this miniature photograph first. Tell me what geometry must be preserved and how the background could be extended.
```

```text
$model-photo-world-extension Extend this 1:64 model photograph into a late-autumn Japanese seaside blue-hour scene. Preserve the original subject, tracks, perspective and composition exactly.
```

```text
$model-photo-world-extension Micro-retouch only. Correct the headlight interaction with the existing rails and do not regenerate any other part of the image.
```

```text
$model-photo-world-extension 分析这张模型照片，先告诉我哪些结构必须锁死，再给出环境延伸方案。
```

## Templates

- [Master prompt template](templates/master-prompt.md) — build a consolidated geometry-first environment-extension prompt.
- [Micro-retouch template](templates/micro-retouch.md) — restrict a nearly finished image to named local corrections only.

## Example

- [Seaside Hiroshima tram case study](examples/hiroshima-tram.md) — one worked example of the workflow. It does **not** limit the Skill to trams, Hiroshima, or railway photography.

## Installation

Place this repository in your Codex Skills directory with `SKILL.md` at the repository root:

```text
~/.codex/skills/model-photo-world-extension/
```

Then call it as:

```text
$model-photo-world-extension
```

## Dependencies

No external dependencies are required. The Skill consists of Markdown instructions, reusable prompt templates, and an example.
