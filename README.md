# astro-blocks

A collection of Astro UI components, distributed as raw source with no build step required.

## Installation

```sh
npm install git+https://github.com/you/astro-blocks.git
```

## Usage

```astro
---
import { Header, Footer, VideoHero, ImageHero } from 'astro-blocks';
import 'astro-blocks/styles/base.css';
---
```

## Components

### `<Header>`

Absolute-positioned header wrapper with a slot.

```astro
<Header>
  <nav>...</nav>
</Header>
```

---

### `<Footer>`

Centered footer wrapper with a slot.

```astro
<Footer>
  <p>© 2026 My Site</p>
</Footer>
```

---

### `<VideoHero>`

Full-viewport hero section with an autoplaying background video, gradient overlays, and a title/subtitle panel.

```astro
<VideoHero
  title="EXPANDING HUMANITY BEYOND EARTH"
  subtitle="Our mission is to develop the technology that will enable people to explore, live, and work beyond our planet."
  video="/mars.webm"
  content="right"
/>
```

| Prop | Type | Default | Description |
| --- | --- | --- | --- |
| `title` | `string` | — | Required. Hero heading. |
| `subtitle` | `string` | — | Optional subheading. |
| `video` | `string` | — | Path or URL to the video source. |
| `content` | `'left' \| 'right'` | `'right'` | Side the text panel appears on (desktop). |
| `style` | `string` | — | Additional inline styles on the root element. |

**CSS custom property:** `--video-hero-overlay-color` (default `#000`) controls the gradient overlay color.

---

### `<ImageHero>`

Same as `VideoHero` but with a static image instead of a video.

```astro
<ImageHero
  title="EXPANDING HUMANITY BEYOND EARTH"
  subtitle="Our mission is to develop the technology that will enable people to explore, live, and work beyond our planet."
  image="/mars.jpg"
  alt="Surface of Mars"
  content="left"
/>
```

| Prop | Type | Default | Description |
| --- | --- | --- | --- |
| `title` | `string` | — | Required. Hero heading. |
| `subtitle` | `string` | — | Optional subheading. |
| `image` | `string` | — | Path or URL to the image. |
| `alt` | `string` | `""` | Alt text for the image. |
| `content` | `'left' \| 'right'` | `'right'` | Side the text panel appears on (desktop). |
| `style` | `string` | — | Additional inline styles on the root element. |

**CSS custom property:** `--image-hero-overlay-color` (default `#000`) controls the gradient overlay color.

---

## Base styles

The optional base stylesheet resets margins, sets `box-sizing: border-box`, and applies sensible defaults for a dark-themed site.

```astro
import 'astro-blocks/styles/base.css';
```

## Development

```sh
npm run playground        # Start the playground dev server (localhost:4321)
npm run playground:build  # Build the playground
```
