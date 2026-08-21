# Blockframe specification

Use this reference for every Blockframe generation or review task. It defines the default visual system, layout grammar, output expectations, and acceptance criteria.

## Default palette

Use these exact six colors when the user does not provide another palette:

- `--bf-canvas: #F8FAFC` — page canvas and the named base color.
- `--bf-surface: #FFFFFF` — cards, panels, and elevated content surfaces.
- `--bf-muted: #E2E8F0` — large placeholder fills and low-emphasis regions.
- `--bf-line: #CBD5E1` — borders, rules, text skeletons, and grid lines.
- `--bf-secondary: #94A3B8` — side navigation, avatars, media symbols, and secondary blocks.
- `--bf-strong: #475569` — active navigation, headings, key bars, arrows, and strongest emphasis.

The palette is a cool Slate neutral system. Keep it restrained and mostly flat: do not introduce gradients, transparency, black, accent hues, or alternative grays unless the user requests them or a supplied reference requires them.

### Color priority

- Let `#F8FAFC` and `#FFFFFF` occupy most of the canvas.
- Use `#E2E8F0` and `#CBD5E1` for the majority of placeholders and boundaries.
- Use `#94A3B8` for grouped secondary areas, not for every block.
- Reserve `#475569` for a small number of focal elements so hierarchy remains visible.

## Block grammar

Represent content with a small reusable vocabulary:

- **Text:** horizontal bars; title bars are thicker or darker than body bars.
- **Image:** a framed rectangle containing a simple mountain-and-sun placeholder.
- **Avatar:** a circle using `--bf-secondary` or a lighter fill.
- **Button or active navigation:** a compact `--bf-strong` rectangle.
- **Card:** a `--bf-surface` panel with a `--bf-line` border and internal padding.
- **Section:** a group of blocks aligned to the same start and end lines.
- **Divider:** a 1px `--bf-line` rule.

Do not add detail that implies a finished UI. A Blockframe should answer where content lives, how much space it receives, and what is primary before it answers how the product is branded.

## Grid and spacing

- Default desktop grid: 12 columns with consistent gutters.
- Default tablet grid: 8 columns.
- Default mobile grid: 4 columns.
- Default spacing unit: 8px; prefer 8, 16, 24, 32, 40, and 48px.
- Align the first meaningful child of adjacent regions to shared horizontal or vertical start lines when the design intent calls for continuity.
- Repeated cards must share width, internal padding, media ratio, title position, and body-line rhythm unless variation communicates hierarchy.
- Keep outer margins larger than inner gaps, and section gaps larger than gaps between items within a section.

These defaults are starting points, not requirements that override a supplied design system or viewport.

## Common page archetypes

Choose the smallest structure that explains the page:

- **Dashboard:** top navigation, side navigation, summary cards, primary data/content region, secondary modules, footer or utility row.
- **Content index:** top navigation, filters or category navigation, repeated media cards, featured row, pagination/footer.
- **Article/detail:** top navigation, title/meta, main content column, optional aside, related-content section, footer.
- **Landing page:** header, hero, benefit or feature sections, proof/content band, call to action, footer.
- **Form/workflow:** header, progress or navigation, grouped fields, contextual help, sticky or terminal actions.

## Palette-plus-layout board

When producing a composition like the bundled reference:

- Place a narrow palette card on the left and the larger Blockframe viewport on the right.
- Show the named base color prominently, then list all semantic swatches with exact hex values.
- Include a compact primitive legend for rectangle, line, circle, and image placeholder.
- Keep the right-side layout large enough to reveal grid, hierarchy, and repeated-component rules.
- Use a clean white or `--bf-canvas` background with subtle borders; avoid heavy shadows and decorative effects.

## Code output

For HTML/CSS output:

- Use semantic elements such as `header`, `nav`, `aside`, `main`, `section`, `article`, and `footer` where they match the layout.
- Define the palette and spacing as CSS custom properties rather than repeating hex values.
- Use CSS Grid for page regions and repeated card grids; use Flexbox for one-dimensional alignment inside components.
- Avoid absolute positioning except for small internal placeholder artwork or when exact reference reproduction requires it.
- Keep the source viewport pixel-faithful, then add deliberate tablet and mobile breakpoints without uniformly scaling the entire interface.
- Ensure image placeholders preserve aspect ratio, text bars do not overflow, and navigation remains usable at narrow widths.

## Comparison images

Each “调整前 / 调整后” board should demonstrate one rule only. Keep content, card size, colors, and surrounding layout constant so the changed alignment, spacing, sizing, or hierarchy is easy to identify.

Use a neutral arrow or divider between states. Do not add measurement boxes or guide lines unless the user explicitly asks for annotated diagnostics.

## Acceptance checklist

- The output uses the exact requested palette; default output contains no unapproved colors.
- Major regions are identifiable without production copy.
- Repeated elements share dimensions and internal rhythm.
- Alignment lines and spacing increments are consistent.
- Strong color is reserved for focal elements and does not dominate the page.
- The artifact matches the requested dimensions and does not crop or stretch content.
- Code output runs locally, remains editable, and responds intentionally rather than through uniform scaling.
- Screenshot-derived values are labeled as verified or estimated according to the available evidence.

