---
name: pixel-perfect-diagram-ppt
description: Recreate, repair, and iteratively refine reference diagrams, scientific schematics, biological mechanism figures, process maps, infographic panels, legends, and OCR-extracted image layouts as high-fidelity editable PowerPoint slides. Use when the user provides an image/PDF/screenshot and asks for perfect or high-fidelity PPT replication, editable elements, 任意元素可修改, 像素级复刻, 1:1复刻, 完美复刻, OCR-assisted reconstruction, transparent PNG module extraction, or iterative correction of arrows, labels, formulas, molecule/particle markers, borders, spacing, typography, legends, and visual details.
---

# Pixel-Perfect Diagram PPT

## Purpose

Rebuild reference diagrams as editable PPTX files while treating the source image as the visual truth. This skill is for dense scientific figures, biological mechanism diagrams, process maps, infographic panels, legends, and other layouts where small visual details matter.

Use a hybrid strategy:

- Keep global structure, readable labels, tables, simple lines, simple arrows, frames, and legends editable whenever practical.
- Use source-image transparent PNGs for complex visual modules that cannot be faithfully redrawn with PPT primitives.

Never hide weak fidelity behind a full-slide screenshot unless the user explicitly asks for a non-editable fallback.

## Core Rule

Inspect the original source crop before every local edit. Do not rely only on the current PPT preview, and do not improvise. Every correction must trace back to the source image.

## Reconstruction Strategy

1. Establish the source image dimensions and coordinate system.
2. Map source pixel bboxes to PPT coordinates.
3. Rebuild simple editable objects with PPT primitives:
   - Titles, labels, legends, and formulas
   - Zone headers, panels, rounded boxes, dashed boxes, separators
   - Simple straight arrows, simple curves, and flow lines
   - Native tables when the source has rows/columns
4. Extract complex modules from the source as transparent PNGs:
   - Cells, bacteria, organisms, bubbles, molecule clusters, particles, icons
   - Containers, equipment, shaded objects, glossy markers, hand-drawn artwork
   - Complex legend icons when style consistency matters
   - Any object that looks visibly wrong when recreated from PPT shapes
5. Keep each complex module separate. Do not rasterize whole zones, whole footers, or the full slide to avoid rebuilding editable content.
6. Preserve original position, size, aspect ratio, antialiasing, shadows, highlights, edge style, and internal details.

## Hard Rules

- Source first, preview second. If unsure, crop the original source region again.
- Do not adjust by taste. Preserve source line continuity, text gaps, arrow endpoints, icon scale, color, border style, and spacing.
- Treat repeated feedback as a rule. If the same defect appears twice, stop guessing and measure source bbox, target bbox, neighboring gaps, arrow endpoints, and layer order.
- Do not hand-redraw complex scientific modules when source PNG extraction gives better fidelity.
- Do not sacrifice global editability. Use PNGs only for complex visual modules; rebuild readable text, tables, simple lines, arrows, boxes, and separators as PPT objects.
- Do not crop, erase, recolor, stretch, or reshape the original complex subject. If color or texture extends beyond a guessed edge, expand the bbox or mask so the border encloses the subject.
- Remove only external residue from PNG modules: arrows, dashed frames, labels, border fragments, gray antialiasing, background blocks, and unrelated particles.
- A repaired PNG must be complete: closed edge, one outer border, no white holes, no patch blocks, no duplicated outline, no leftover internal/external line fragments, and no unexpected shadow.
- Keep PNG canvas and PPT placement synchronized. If transparent margins change, update x/y/w/h in the PPT generator.
- Text must stay inside its frame or source region. If it exceeds a box, reduce font size or adjust the text box.
- Text, icons, biological modules, arrows, arrowheads, dashed boxes, legends, and process lines must not overlap unless the source image visibly overlaps them. Before handoff, audit every dense region for object collisions and restore the source gaps, especially around chemical formulas, curved arrows, PNG modules, and legend labels.
- If the source keeps a label on one line, prevent PowerPoint wrapping.
- Match text color and weight. Scientific legends often encode meaning through green/red/blue/purple/black labels.
- Use Chinese-capable fonts such as `微软雅黑` / `Microsoft YaHei` when the source uses Chinese labels.
- Use real subscript/superscript when stable. If PowerPoint/preview baseline drifts, use Unicode formula glyphs such as `NH₄⁺`, `NO₃⁻`, `NO₂⁻`, `PO₄³⁻`, and `N₂`.
- Arrow meaning is strict. The arrow head must land on the same visual target as the source: word center, word gap, icon edge, particle cluster, box edge, or label center.
- Arrow shafts and heads must not cross readable labels or complex module bodies unless the source does. If a line relation approaches text, match the source gap or route the curve around the label.
- One relationship arrow has one arrow head. Do not append a second arrow-headed segment to extend a curve.
- Curved arrows need source-like curvature. Do not replace curved solid arrows with broken, dotted, or visibly segmented substitutes.
- Preserve line topology. If the source line is continuous, keep it continuous; if the source line has a text gap, preserve the gap.
- Match dashed/solid styles, line width, color, and arrowhead size.
- Legend icons must match the main diagram style. If main diagram modules use source-style PNGs, footer/side legends should use the same visual vocabulary.

## Examples Of Complex Modules

The following are examples, not limits:

- Biological mechanism diagrams: cells, bacteria, PAOs, AOB/NOB, denitrifiers, gas bubbles, molecule clusters, sludge/WAS containers.
- Chemistry and process diagrams: glossy particles, labeled reaction arrows, recycle streams, dashed storage/utilization boxes.
- Medical and lab schematics: organ icons, experimental equipment, shaded sample containers, microscopy-like inserts.
- Infographic panels: detailed icons, pictorial legends, map markers, textured badges.

When a complex module is the reason the slide looks unlike the source, extract it from the source as PNG first; convert it to editable vector only after visual fidelity is accepted.

## High-Frequency Biological Mechanism Figures

For A/O/A, wastewater treatment, biological nitrogen/phosphorus removal, microbiology process diagrams, or any dense biological mechanism figure with cells, bacteria, gas bubbles, molecule clusters, recycle streams, legends, and Chinese/chemical labels, load and follow [references/aoa-biological-mechanism-lessons.md](references/aoa-biological-mechanism-lessons.md).

These lessons are not AOA-only; they are reusable guardrails for complex scientific mechanism figures where biological icon style, arrow semantics, formula typography, and legend consistency are fragile.

## Correction Workflow

When the user circles a defect:

1. Crop the corresponding source region.
2. Crop the current PPT preview region.
3. Compare them before editing.
4. Name the exact mismatch: color, spacing, line type, arrow target, text wrapping, missing edge, residue, duplicated outline, wrong icon style, or wrong layer order.
5. Modify the source script, construction assets, or editable PPT objects, not just the final binary.
6. Re-export the PPTX.
7. Render a preview and zoom the corrected area.
8. Confirm no unrelated region moved.
9. If the defect is a repeat pattern, update the reusable construction rules.

Do not claim "100% replication" or "百分百复刻" until the user accepts the visual result.

## PNG Repair Protocol

Use this whenever a complex PNG module is incomplete, contaminated, or mismatched:

1. Return to the original image, not the already-damaged PNG.
2. Re-take a wider bbox including full subject, edge, highlight, shadow, and antialiasing.
3. Apply alpha masking to remove only external relations such as arrows, labels, dashed frames, background rectangles, and stray text pixels.
4. Do not crop subject color/texture to force an outline.
5. Do not overlay patch lines that create double edges.
6. If a boundary must be rebuilt, remove old fragments first and end with one continuous closed edge.
7. Update PPT placement if the PNG canvas changed.
8. Render a zoomed preview and verify: complete subject, no residue, no duplicate border, no white gap, no scale drift.

## OCR And Tool Selection

OCR is useful for initial text extraction, but visual fidelity comes from source comparison.

- Use lightweight local OCR when heavy dependencies are unavailable.
- Use stronger OCR/layout tools when batch layout analysis or table detection matters.
- Manually normalize domain text and formulas. OCR often damages subscripts, superscripts, slashes, Chinese labels, and chemical symbols.

## QA Checklist

Before final handoff, run [references/diagram-fidelity-checklist.md](references/diagram-fidelity-checklist.md).

Final delivery should include the PPTX, safe copy when useful, extracted PNG assets, rendered preview crops, and a concise list of concrete changes.
