# [Master Guide] CAD & SketchUp Style Facility Dimension Guide

## 1. Universal Structural Analysis Rules (모든 시설물 공통 정밀 분석 규칙)
When analyzing a reference image to generate technical drawings, the AI MUST automatically scan and explicitly render the following structural details without simplifying them:

1. **Non-Rectilinear Geometries (비직육면체 및 경사 구조):**
   - Do NOT simplify sloped roofs, tapered profiles, curved edges, or chamfers into basic boxes.
   - Accurately reflect slope angles, tapered thickness variations, and asymmetrical forms.

2. **Structural Supports & Hardware (지지 구조 및 철물):**
   - Explicitly draw support brackets, cantilever arms, diagonal struts, mounting plates, and joint connection details.

3. **Pattern, Relief & Material Details (패널, 루버 및 소재 디테일):**
   - Render louvers, cutouts, panel joints, glass/metal frames, and material thickness changes accurately.

---

## 2. Visual Style Guidelines (도면 시각 표현 규칙)
- **Render Mode:** Orthographic 2D Elevation (Front, Side View) or 3D Isometric View.
- **Background & Lines:** Pure white background (`#FFFFFF`), sharp solid black vector line art (0.5pt to 1.5pt line weights).
- **Shading & Texture:** NO 3D rendering, NO realistic textures, NO gradients, NO cast shadows. Pure flat line drawing.
- **Annotations & Dimensions:** 
  - Thin black extension lines with tick marks or small arrows.
  - Sans-serif architectural typography indicating major dimensions (W, H, D) and component callouts.
- **Output Format:** Always generate clean, modular SVG code (xml format) inside a code block, using raw `<path>`, `<rect>`, `<line>`, and `<text>` elements.
---

## 3. Scale & Proportional Dimensioning Protocol (치수 추정 수칙)
1. Identify the user-provided reference metric (e.g., Planter Height = 70cm, Post Height = 2600mm).
2. Correct for perspective distortion in 3/4 view images.
3. Calculate proportions for seat height, clear opening widths, roof overhangs, and member thicknesses.
4. Output a Markdown table listing overall and sub-component measurements before image synthesis.

---

## 4. Master Prompt Template (모든 가로시설물 공통 생성 프롬프트)

> **[Copy & Use Prompt Template]**
> *Clean architectural 2D orthographic elevation / 3D axonometric technical drawing of a [INSERT FACILITY NAME, e.g., Bus Shelter, Street Bench, Smart Kiosk, Street Lamp]. Precise SketchUp lineart and CAD blueprint style. Feature sloped/tilted geometries, tapered profile edges, diagonal support brackets, cantilever struts, and louvre panels exactly as seen in the reference image—do NOT simplify into basic rectangular boxes. Pure white background, sharp solid black vector outlines, no gradients, no shadows. Include thin black dimension extension lines, tick marks, and clear numerical annotations for key dimensions (Width, Height, Depth, and angles). Professional public design presentation drawing, highly detailed, minimalist.*