# A tile image for your dashboard

Metalens lists a dashboard on its [Dashboards page](/dashboards) as a picture tile. If your page
publishes one, that picture is used; otherwise the tile is left plain.

Below is a prompt for generating one in the house style, so your tile sits comfortably beside the
others. Paste it into an image model of your choice, generate at **1200x630**, and save
the result next to your page — then name it in your `metalens.json`:

```json
{ "preview": "preview.png" }
```

You can also supply an image directly when you register the dashboard, which takes precedence over
the manifest. Either way the picture is decorative: it is not evidence, and it should not state a
result.

## The prompt

```
Draw a 1200x630 illustration for the cover of a research dashboard.

Subject — illustrate the idea, not the words: Register-data claims — agent (Danish) The nine seed papers extracted by the danish-register-econ agent with stated_claims_v3_agent.md (four passes; constructs, estimands, value_from). The review target; supersedes the import of the old pipeline's claims. Themes: causal claims, Danish register data, administrative data, economics, labor supply, taxation, evidence extraction.

Find one concrete visual metaphor for that subject and draw only it. Do not try to depict every theme listed; do not draw a chart of invented data, and do not imply a finding the dashboard may not support.

Style — follow every point:
- A flat vector editorial illustration, in the manner of a broadsheet newspaper's science section.
- Geometric and diagrammatic: circles, arcs, lines, dots, simple silhouettes. No perspective, no
  three-dimensional rendering, no drop shadows, no glossy or metallic surfaces.
- Palette, and no other colours: deep navy #122740 and slate blue #1b485e for the drawing; teal
  #367380 and pale teal #9cbcc4 for supporting shapes; a single warm orange #eb6834 used sparingly,
  for the one element that matters most; a near-white background, #f5f5f5 to #ffffff.
- Calm and sparse. Generous empty space. A single clear idea, legible when the image is only
  300 pixels wide.
- Absolutely no text, letters, numbers, labels, captions, watermarks or logos anywhere in the image.
- No photorealism, no stock-photo people, no faces, no robots, no glowing neural networks, no
  circuit boards, no brains — none of the usual visual clichés for artificial intelligence.

```

## If you would rather draw it from your data

A tile drawn from the dashboard's own figures is usually better than a generated one, because it is
specific to the page. Render one of your figures at 1200x630 with no title, no legend and
no axis labels — the tile prints the title and description underneath, so words inside the picture
only repeat them.
