# AOA And Biological Mechanism Lessons

Use this reference for A/O/A diagrams and similar biological/environmental engineering mechanism figures. It preserves the hard-won details from iterative AOA_Model reconstruction and generalizes them to future scientific diagrams.

## Core AOA Lesson

Do not treat complex biological diagrams as generic flowcharts. Their fidelity depends on small visual systems: cell style, bacteria style, glossy molecule markers, curved arrows, chemical formula baselines, dashed/solid box conventions, and repeated legend consistency.

## Biological Modules

- Use source PNGs for PAOs/cells, bacteria, AOB/NOB, denitrifiers, gas bubbles, molecule clusters, sludge/WAS cones, and other shaded or glossy biological modules when PPT redrawing looks flat or wrong.
- Preserve original gradients, highlights, shadows, antialiasing, outlines, internal particles, liquid surfaces, and hand-drawn texture.
- Keep each biological module separate from surrounding arrows, labels, dashed boxes, and panel frames.
- If a module edge is missing or contaminated, return to the original crop and re-extract wider. Do not repair by cropping away subject color or adding a second outline.
- A good repaired PNG has one continuous closed border, no white hole, no duplicated line, no leftover arrow fragment, no text residue, and no patch block.
- If the source has repeated icon systems, such as main-panel bacteria plus bottom legend bacteria, use source-style icons consistently in all locations.

## Text And Formulas

- Keep readable labels editable. Only tiny internal artwork can remain inside PNGs.
- Use Chinese-capable bold fonts such as `微软雅黑` / `Microsoft YaHei`.
- Preserve source color coding: denitrifiers often green, PAOs red, AOB/NOB blue, phosphate purple, recycle streams green/navy/brown depending on source.
- Use Unicode chemical formulas when baseline rendering is unstable: `NH₄⁺`, `NO₃⁻`, `NO₂⁻`, `PO₄³⁻`, `N₂`.
- Do not let formulas wrap if the source is single-line.
- Bracketed/parenthetical subtitles should be smaller and positioned like the source, not treated as the same-size main label.
- Text must stay inside boxes and panels. If it exceeds a frame, reduce font size or adjust the text box; do not let it cross the border.

## Arrows And Line Semantics

- Arrow heads must land on the same semantic target as the source: label center, word gap, icon edge, particle cluster, dashed box edge, or panel boundary.
- Do not move an arrow from under text onto the text just because it looks centered.
- One relationship arrow has one arrow head. Do not extend a curve by adding another arrow-headed short segment.
- Curved arrows need real curvature. Do not replace them with visibly segmented, dotted, or angular approximations unless the source does.
- Preserve line topology:
  - If the source line is continuous, keep it continuous.
  - If the source line breaks around a label, keep the break.
  - Do not assume all labels require line breaks.
- Preserve line type: dashed boxes stay dashed, solid arrows stay solid, intermittent arrows stay intermittent only when the source shows that.
- Maintain source gaps between arrows and text/icons. Avoid both overlap and excessive separation.

## AOA-Specific Visual Systems

- Anaerobic, aerobic, and anoxic zones usually have different panel tints and border colors. Preserve panel identity.
- `PHAs/Gly` boxes may be dashed or solid depending on the source context. Storage, utilization, and hydrolysis labels are not interchangeable.
- `N₂ (释放)` arrows should point as in the source, often from below toward the label area without overlapping the text.
- Internal recycle and external recycle lines must preserve direction, color, line continuity, label placement, and vertical/horizontal offsets.
- WAS/sludge discharge icons should be source PNG modules if they contain liquid, particles, shading, or a cone/container shape; surrounding arrows should remain editable when simple.
- Bottom and side legends should match the main diagram icon style. Do not mix source PNG cells with flat hand-drawn legend cells.
- Legend icon-to-text spacing matters. Move text closer or farther according to the source, and keep labels away from separator lines.

## Practical Repair Patterns

When a user circles an issue:

1. Determine whether the issue is a simple editable object or a complex module.
2. For simple objects, fix PPT primitives: text box size, font size, color, line continuity, arrow target, frame style.
3. For complex modules, go back to the source image and re-extract or repair the PNG.
4. Never repair a damaged complex module only by stacking PPT shapes over it unless the user explicitly wants editable approximation.
5. After every fix, render a zoomed preview of the exact region and compare to the source crop.

## Common Failure Modes To Avoid

- Flat circles without glossy highlight when source particles have highlights.
- Chemical superscripts/subscripts split across lines or drifting far from the base text.
- Dashed storage/utilization boxes accidentally becoming solid.
- Curved arrows becoming dotted, angular, or duplicated.
- Arrow heads duplicated by adding a second arrow segment.
- PNG modules cropped so cell/bacteria borders are incomplete.
- Removing arrow residue but also erasing the biological subject edge.
- Text and icon spacing based on taste instead of the source.
- Legend icons not matching the corresponding main-panel icons.
