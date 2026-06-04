# Diagram Fidelity Checklist

Use this checklist before handing off an editable PPTX diagram reconstruction.

## Source Comparison

- The original source crop was inspected before each local edit.
- The final preview has been compared with the same source crop at zoom level.
- Corrections are based on source geometry, not visual taste.
- No unrelated region moved during a local correction.
- For biological/environmental mechanism diagrams, the AOA lessons in `references/aoa-biological-mechanism-lessons.md` were considered.

## Structure And Editability

- The slide aspect ratio matches the source or intentionally preserves the source crop.
- Major panels, headers, legends, arrows, footer bands, and side panels align to the source grid.
- The final PPTX is not a single screenshot or a small number of large raster regions.
- Readable labels, tables, simple lines, simple arrows, frames, legends, and process notes remain editable where practical.
- Complex visual modules use source-style transparent PNGs only where editable redrawing would be visibly worse.
- If a PNG canvas or transparent margin changed, the PPT placement bbox changed with it.

## Text And Formulas

- Single-line source labels stay single-line in PPT.
- Text stays inside its frame or source region.
- Chinese labels match source weight and approximate typeface.
- Text color matches the source, especially scientific legends where color carries meaning.
- Chemical formulas render correctly, using rich text or Unicode forms such as `NH₄⁺`, `NO₃⁻`, `NO₂⁻`, `PO₄³⁻`, and `N₂`.
- Parenthetical subtitles have source-like smaller size and spacing.
- Labels do not collide with separator lines, arrows, icons, or frame borders unless the source does.
- Dense regions have been checked for collisions among text, chemical formulas, PNG modules, arrows, arrowheads, dashed boxes, legends, and process lines. Any source gap around these objects is preserved instead of being guessed.

## PNG Modules And Icons

- PNG modules have transparent backgrounds.
- Complex modules preserve source highlights, gradients, shadows, antialiasing, outlines, and internal details.
- PNG modules contain only the intended module, with no external arrow, dashed-frame, label, border, gray antialiasing residue, or unrelated particles.
- No PNG has a cropped body, missing border, white hole, duplicated outline, patch block, or leftover line fragment.
- Biological icons, cells, bacteria, gas bubbles, molecule clusters, containers, and other complex source-style elements match the source rather than flat redraws.
- Footer and side legend icons match the style of the main diagram icons.
- Icon-to-label distance in legends matches the source and is not overly loose or cramped.

## Arrows, Lines, And Frames

- Arrow heads and shafts match source color, thickness, head size, and geometry.
- Arrow heads point to the same target as the source: word gap, label center, particle cluster, box edge, or icon body.
- Arrow shafts and heads do not pass through readable text or complex modules unless the source shows that exact overlap.
- A single relationship arrow has only one arrow head.
- Curved arrows preserve source curvature and continuity.
- Solid lines remain solid; dashed lines remain dashed.
- Lines are continuous or broken exactly as the source shows.
- Flow/recycle arrow directions match the source.
- Arrow-to-text and arrow-to-icon gaps match the source and do not create ambiguity.

## Legends And Repeated Systems

- Repeated icon systems use the same visual vocabulary throughout the slide.
- Legend markers use the right type: single glossy dots vs molecule clusters vs full icon modules.
- Marker-to-label spacing matches the source.
- Separator lines do not overlap labels.
- Side legends and footer legends agree with main-panel icon styles.

## PowerPoint Safety

- The PPTX opens in PowerPoint.
- Rendered preview is nonblank.
- OOXML has no negative extents from line generation.
- Avoid fragile custom geometry when native line segments or source PNGs are safer.
- A safe copy is updated when the workflow has previously produced unreadable files.

## User Feedback Loop

- For every circled correction, update the reusable source script or construction notes.
- Re-export after each correction.
- Generate a zoomed crop for the corrected area and compare it with the source crop.
- State the local change precisely; avoid broad claims.
- Do not claim 100% replication until the user accepts the visual result.
