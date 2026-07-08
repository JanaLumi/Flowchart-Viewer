# Flowchart-Viewer
A browser-based viewport designed to read and display interactive, high-resolution structural diagrams. Version 2.0 also includes Text-to-Speech (TTS) to read contextual system stories.

This repository allows creators to entirely isolate complex graph layouts (`Mermaid.js` syntax) and rich stories into standalone, labelled `.md` files without compiling complex application dependencies or maintaining a structural database backend.

---

## 🏛️ Evolution Matrix

### 🔹 Version 1.0 — Static Interactive Canvas

[flowchart-viewer-1.0](https://janalumi.github.io/Flowchart-Viewer/viewer-1.0.html)

The initial foundational tier focused purely on micro-precision browser graphics and canvas manipulation layers.

* **Static Graph Ingestion:** Reads pure diagram strings directly into the client DOM layout target.
* **Magnifying Lens Core:** Tracks cursor coordinates to clone, scale, and paint high-density vectors onto a floating canvas element.
* **Granular Wheel Zooming:** Captures browser scrolling events to modify magnification depth incrementally between **1.5× and 8.0×** without distorting layout text or arrow markers.

### 🔸 Version 2.0 — Decoupled Story Viewport

[flowchart-viewer-2.0](https://janalumi.github.io/Flowchart-Viewer/viewer-2.0.html)

The architecture introduces an asynchronous content parser and a localised audio runtime engine to turn architectural models into accessible stories.

* **Property Label Ingestion:** Reads standalone markdown files formatted with strict data properties (`title:`, `text:`, and `code:` blocks).
* **Zero-Dependency Core Execution:** Operates entirely within browser memory via raw string index boundary lookups, bypassing database servers, layout side effects, or configuration environments.
* **Local Text-to-Speech Engine:** Grabs whatever story content is visible on-screen at the exact moment of activation, managing audio synthesis parameters, tracking word boundaries, and honoring live pitch/rate adjustments locally.
* **Asynchronous Fallback Architecture:** Automatically displays local matrix text and fires setup warnings if external files are unconfigured, ensuring first-time viewers are never faced with a blank viewport.

---

## 🛠️ File Structure & Labeled Properties

To feed data into the viewport matrix, your external text documents (stored inside the `diagrams/` folder) must wrap configuration lines inside explicit delimiters. This keeps data assets readable by humans and cleanly sliceable by the computer.

### The Standard Document Schema:

```markdown
title: "Your Perspective Title Here",
text: `<p>First paragraph of your perspective story essay...</p>
<p>Second paragraph of your story context...</p>`,
code: `flowchart TD
  A[Your Structural Node] --> B[Your Next Connecting Layer]`

```

---

## 🚀 Setting Up Your Own Diagram Journey

### 1. Replicate the Structure

Fork or clone this repository to your local studio workplace environment, ensuring your file paths align with the template variables:

```text
├── index.html
├── diagrams/
│   ├── system-overview.md
│   └── system-journey.md
└── assets/

```

### 2. Isolate Your Content

Open the `diagrams/` folder, duplicate a template file, and format your specific metrics inside the `title:`, `text:`, and `code:` parameters shown in the schema above.

### 3. Align the Application Matrix

Open `index.html`, navigate to the `perspectives` data matrix inside the script tags, and link your file destination properties directly to the paths of your newly created documents:

```javascript
const perspectives = {
  journey: {
    title: "Your Custom Journey View",
    file: "diagrams/your-custom-journey.md",
    text: "<p>Baseline fallback text for first-time loads...</p>"
  }
};

```

### 4. Deploy Your Viewport

Commit your changes and push the directory assets to a static hosting platform (such as GitHub Pages). The script engine will automatically execute its asynchronous lookups and serve your interactive diagram matrix globally.
