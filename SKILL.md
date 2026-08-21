---
name: kryon-blockframe-generator
description: Generate Blockframe UI planning artifacts from a frontend module screenshot, page brief, base color, or existing interface, including screenshot-to-Blockframe conversion, semantic neutral palettes, grid-and-block layouts, comparison visuals, and editable HTML/CSS reproductions. Use for 前端模块截图转 Blockframe、Blockframe、布局规划图、页面占位设计、色卡、栅格线框、前后对比图或 Blockframe 代码复刻；do not use for production UI styling that requires finished brand content and components.
---

# Kryon Blockframe Generator

Create restrained, structurally clear Blockframe artifacts that communicate page regions, hierarchy, alignment, spacing, and color roles before visual design is finalized.

## Default behavior

- When the user does not provide colors, use the exact default palette defined in [references/blockframe-spec.md](references/blockframe-spec.md): `#F8FAFC`, `#FFFFFF`, `#E2E8F0`, `#CBD5E1`, `#94A3B8`, and `#475569`.
- When the user provides a base color or full palette, treat it as authoritative. Preserve explicit colors and derive only the missing roles; do not silently mix the default palette back in.
- When the user provides a frontend module screenshot, treat its visible structure as authoritative. Preserve the module boundary, aspect ratio, element count, order, proportions, layout direction, hierarchy, and shared alignment lines while abstracting real content into Blockframe primitives.
- Use the supplied page type, content hierarchy, target viewport, and output format. If these are omitted, choose a reasonable desktop dashboard or content-page structure and state the assumption briefly.
- Keep Blockframe content abstract: use short bars, image placeholders, avatars, cards, navigation blocks, and labels only when they clarify structure. Do not invent finished product copy or decorative brand imagery.
- Prefer deterministic HTML/CSS or SVG for exact geometry, text, and hex colors. Use raster generation only when the user explicitly wants a generated bitmap style rather than an editable or pixel-verifiable artifact.

## Choose the output mode

- **Palette:** show the base color, semantic swatches, hex values, and role names.
- **Layout plan:** map the viewport into major regions and nested blocks using a consistent grid and spacing rhythm.
- **Screenshot conversion:** transform one supplied frontend module screenshot into a structurally equivalent Blockframe layout image. Read [references/screenshot-to-blockframe.md](references/screenshot-to-blockframe.md) before acting.
- **Combined board:** place the palette panel beside the Blockframe layout, following the bundled reference when appropriate.
- **Comparison:** create clearly labeled “调整前 / 调整后” examples that isolate one layout or calibration rule at a time.
- **Code reproduction:** produce responsive, editable HTML/CSS with semantic regions and CSS variables; match a supplied reference at its source viewport before adding responsive behavior.

Read [references/blockframe-spec.md](references/blockframe-spec.md) whenever generating or reviewing an artifact. For screenshot conversion, also read [references/screenshot-to-blockframe.md](references/screenshot-to-blockframe.md); inspect [assets/01-Blockframe默认色板与布局参考.png](assets/01-Blockframe默认色板与布局参考.png) only when the requested composition resembles a palette-plus-layout presentation. Reuse [assets/blockframe-tokens.css](assets/blockframe-tokens.css) for code output unless the user supplies another palette.

## Workflow

1. Inspect the supplied screenshot when present; otherwise identify the page archetype, main regions, hierarchy, viewport, and requested deliverable from the brief.
2. Choose or derive the semantic palette before drawing blocks so the same role always uses the same color.
3. Establish the outer frame and grid, then place navigation, primary content, secondary content, and repeated components.
4. Apply one spacing rhythm and shared alignment lines across neighboring regions; add optical corrections only after geometric alignment is correct.
5. Generate the requested artifact and verify dimensions, colors, alignment, overflow, and responsive behavior in proportion to the deliverable.

## Delivery rules

- Preserve the requested filename and location. When generating images without a user-specified name, use a two-digit Chinese filename such as `01-Blockframe布局规划图.png`.
- For a single module screenshot, default to one standalone Blockframe image at the source aspect ratio without a separate palette panel. Add the palette panel, annotations, responsive variants, or code only when requested.
- For image output, report the final pixel dimensions and show the finished artifact.
- For code output, provide the runnable entry file and summarize the palette, grid, and responsive breakpoints actually implemented.
- Distinguish exact values from estimates when working from screenshots. Do not describe inferred dimensions or colors as verified measurements.
