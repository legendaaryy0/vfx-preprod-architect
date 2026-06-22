# VFX Pre-Production Architect

> An IronClaw agent skill — Ascendant Pack Bounty Submission  
> **Author:** [@legendaaryy0](https://github.com/legendaaryy0)

---

## What It Does

The **VFX Pre-Production Architect** takes a natural-language scene description and returns a fully structured technical pre-production breakdown for VFX-heavy shoots.

It bridges the director's creative vision and the technical pipeline — ensuring no critical on-set data is missed before stepping into post-production.

---

## Skill Files

| File | Purpose |
|------|---------|
| `skill/SKILL.md` | Full skill spec, trigger conditions, behavior rules, and examples |
| `skill/agent.py` | IronClaw runtime entry point |
| `skill/schema.json` | Skill metadata and I/O schema |

---

## Key Capabilities

- 🎥 **Camera & Lens Logic** — Focal length, aperture, frame rate for CGI match
- 💡 **Lighting Strategy** — Key/Fill/Rim setups to match 3D assets
- 🎬 **On-Set Protocols** — Clean plates, HDRI spheres, tracking markers
- 🖥️ **Render Pipeline** — AOV/pass spec (Z-Depth, Emission, Shadow Catcher, Cryptomatte, etc.)
- 📋 **Pre-Production Checklist** — Sign-off list for department heads

---

## Example

**Input:**
> "Dark room with a glowing holographic briefcase on a table. Character reaches in and pulls out a data chip. Moody, cinematic, sci-fi."

**Output:** A full technical breakdown with camera specs (85mm, f/2.8, 24fps), lighting ratios, HDRI and clean plate protocols, and a render pass list.

---

## License
MIT
