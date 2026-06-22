# VFX Pre-Production Architect

## Overview
The `vfx-preprod-architect` skill bridges the gap between a director's creative vision and the technical VFX pipeline. Given a natural-language scene description, it outputs a fully structured technical breakdown covering camera, lighting, on-set protocols, and render pipeline requirements.

## Trigger Conditions
Use this skill when the user describes:
- A scene intended for VFX compositing or green screen work
- A complex video shoot requiring CGI integration
- Pre-production planning for motion graphics or 3D asset integration
- Any prompt containing terms like: "composite", "VFX shot", "CGI", "clean plate", "HDRI", "render pass", "holographic", "3D asset"

## Input
A natural-language scene description from the director/cinematographer.

**Example:**
> "Dark room with a glowing holographic briefcase on a table. Character reaches in and pulls out a data chip. Moody, cinematic, sci-fi."

## Output Structure

### 1. 🎥 Camera & Lens Protocol
- Recommended focal length(s) and why
- Aperture / depth-of-field notes for CGI match
- Frame rate and shutter angle for VFX integration
- Camera movement constraints (locked, tracked, or handheld with stabilization)

### 2. 💡 Lighting Strategy
- **Key Light:** Position, temperature, intensity, modifier
- **Fill Light:** Ratio relative to key, diffusion notes
- **Rim/Separation Light:** Edge definition for compositing
- **Practical Lights:** In-scene sources to match 3D emission
- **CGI Match Notes:** What the 3D lighter needs to replicate

### 3. 🎬 On-Set Protocols
- Clean plate capture instructions
- HDRI sphere capture (exposure bracketing, placement)
- Tracking marker placement (facial, environmental)
- Color reference card timing
- Witness camera requirements

### 4. 🖥️ Render Pipeline Specification
List of required AOV/render passes from 3D software:
- `Beauty` — final composite base
- `Z-Depth` — for depth-of-field and atmospheric effects
- `Shadow Catcher` — for grounding CGI on real surfaces
- `Emission` — for glowing/light-emitting CGI objects
- `Reflection` / `Refraction` — for glass, water, metallic assets
- `Cryptomatte` — for clean masking of individual elements
- `Motion Vector` — for motion blur in post
- `Ambient Occlusion` — for contact shadow grounding

### 5. 📋 Pre-Production Checklist
- [ ] Shot list locked with VFX supervisor approval
- [ ] HDRI captures scheduled (magic hour or controlled stage)
- [ ] Tracking markers ordered and color-coded
- [ ] 3D asset handoff format confirmed (FBX, USD, Alembic)
- [ ] Render farm allocated and tested
- [ ] Compositing software and version locked (Nuke, After Effects, Fusion)
- [ ] LUT and color pipeline agreed upon (ACES, DaVinci Wide Gamut, etc.)

## Behavior Rules
- Always ask for clarification if the scene description is under 10 words
- If no CGI elements are mentioned, still generate clean plate and HDRI protocols
- Adapt focal length suggestions to the emotional tone (wide = epic/environmental, telephoto = intimate/isolated)
- Flag any on-set condition that would make clean VFX integration difficult (e.g., highly reflective floors, fast handheld movement without tracking)

## Example Invocation

**User:** "Sci-fi interrogation room. Character sits under a single overhead light. Holographic display behind them shows alien text. Tense, cold atmosphere."

**Agent Output:**

### 🎥 Camera & Lens Protocol
- **Focal Length:** 85mm–100mm (telephoto compression for tension; avoids wide distortion on face)
- **Aperture:** f/2.8–f/4 (shallow DOF; hologram display naturally bokeh'd unless hero frame)
- **Frame Rate:** 24fps / 180° shutter (cinematic; motion blur matches 3D render motion vectors)
- **Movement:** Locked or subtle push on slider (no handheld — hologram tracking must be clean)

### 💡 Lighting Strategy
- **Key:** Hard overhead practical (500W tungsten practical, directly above; mimics harsh interrogation)
- **Fill:** Minimal — 8:1 key-to-fill ratio (cold, shadowy feel)
- **Rim:** Cool blue LED strip from behind (matches holographic color temp ~5600K–6500K)
- **CGI Match:** 3D lighter must replicate single hard overhead + cool ambient bounce from hologram

### 🎬 On-Set Protocols
- Shoot clean plate with character removed (locked camera)
- HDRI sphere at seated character position (5-stop bracket minimum)
- Apply tracking dots to monitor stand / wall corner (3-point minimum)
- Color chart at start and end of each setup

### 🖥️ Render Pipeline
Required passes: `Beauty`, `Z-Depth`, `Emission`, `Shadow Catcher`, `Cryptomatte`, `Motion Vector`
