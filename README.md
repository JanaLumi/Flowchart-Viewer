# Flowchart-Viewer
A browser-based viewport designed to read and display interactive, high-resolution structural diagrams. Version 2.0 also includes Text-to-Speech (TTS) to read contextual system stories. Markdown files (in the *diagrams* folder) store the graph layouts (`Mermaid.js` syntax) and system stories.

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

Open the `diagrams/` folder, duplicate a template file, and format your specific metrics inside the `title:`, `text:`, and `code:` parameters shown in the schema in step 3.

### 3. Align the Application Matrix

Select the version you want to work with (details below). And edit the markdown files and perspectives

#### 🛠️ File Structure & Labelled Properties

To feed data into the viewport matrix, your external text documents (stored inside the `diagrams/` folder) must wrap configuration lines inside explicit delimiters. This keeps data assets readable by humans and cleanly sliceable by the computer.

##### The Standard Document Schema:

```markdown
title: "Your Perspective Title Here",
text: `<p>First paragraph of your perspective story essay...</p>
<p>Second paragraph of your story context...</p>`,
code: `flowchart TD
  A[Your Structural Node] --> B[Your Next Connecting Layer]`

```
##### Linking diagrams to data matrix
Open `viewer-X.0.html`, navigate to the `perspectives` data matrix inside the script tags, and link your file destination properties directly to the paths of the new documents.

### 4. Deploy Your Viewport

Commit your changes and push the directory assets to a static hosting platform (such as GitHub Pages). The script engine will automatically execute its asynchronous lookups and serve your interactive diagram matrix globally.

---

## Version details

### 🔹 Version 1.0 — Static Interactive Canvas

[flowchart-viewer-1.0](https://janalumi.github.io/Flowchart-Viewer/viewer-1.0.html)

The initial foundational tier focused purely on micro-precision browser graphics and canvas manipulation layers.

* **Static Graph Ingestion:** Reads pure diagram strings directly into the client DOM layout target.
* **Magnifying Lens Core:** Tracks cursor coordinates to clone, scale, and paint high-density vectors onto a floating canvas element.
* **Granular Wheel Zooming:** Captures browser scrolling events to modify magnification depth incrementally between **1.5× and 8.0×** without distorting layout text or arrow markers.

---

### 🔸 Version 2.0 — Decoupled Story Viewport

[flowchart-viewer-2.0](https://janalumi.github.io/Flowchart-Viewer/viewer-2.0.html)

The architecture introduces an asynchronous content parser and a localised audio runtime engine to turn architectural models into accessible stories.

* **Property Labels:** Reads standalone markdown files formatted with strict data properties (`title:`, `text:`, and `code:` blocks).
* **Zero-Dependency Core Execution:** Operates entirely within browser memory via raw string index boundary lookups, bypassing database servers, layout side effects, or configuration environments.
* **Local Text-to-Speech:** Grabs whatever story content is visible on-screen at the exact moment of activation, managing audio synthesis parameters, tracking word boundaries, and honouring live pitch/rate adjustments locally.
* **Asynchronous Fallback:** Automatically displays local matrix text and fires setup warnings if external files are unconfigured.

#### Html and Javascript edits:

Open `viewer-2.0.html`, navigate to the `perspectives` data matrix inside the script tags, and link your file destination properties directly to the paths of the new documents:

```javascript
const perspectives = {
  journey: {
    title: "Your Custom Journey View",
    file: "diagrams/your-custom-journey.md",
    text: "<p>Baseline fallback text for first-time loads...</p>"
  }
};

```

---

### 🔹 Version 3.0 — Dynamic Perspective Carousel & Scalable Navigation

[Flowchart Viewer 3.0](https://janalumi.github.io/Flowchart-Viewer/viewer-3.0.html)

Version 3.0 expands the viewport from a fixed two-perspective view into a fully modular, scalable system that can support any number of custom diagram perspectives dynamically.

* **Dynamic Tab Generation:** Removes fixed UI constraints, automatically generating navigation tabs based on the keys present in your `perspectives` matrix configuration.
* **Scrollable Navigation Bar:** Introduces a responsive, horizontally scrollable tab carousel with custom navigation controls, ensuring smooth tab browsing across both desktop and mobile layouts regardless of how many diagrams are added.
* **Modular Multi-Diagram Architecture:** Allows creators to plug in an arbitrary number of `.md` file references without modifying the core UI layout or CSS structure.
* **Active Perspective Indicator:** Smoothly syncs tab highlight states and automated audio resets across the expandable carousel controls.

#### JavaScript Configuration Example (v3.0)

To add more perspectives in Version 3.0, simply extend the `perspectives` object in `viewer-3.0.html` with new entries—the navigation UI will automatically construct the new buttons for you:

```javascript
const perspectives = {
  journey: {
    title: "System Journey",
    file: "../diagrams/system-journey.md",
    text: "<p>Baseline fallback text for the journey...</p>"
  },
  overview: {
    title: "System Overview",
    file: "../diagrams/system-overview.md",
    text: "<p>Baseline fallback text for the overview...</p>"
  },
  // Add as many additional perspective keys as you need:
  architecture: {
    title: "Detailed Architecture",
    file: "../diagrams/system-architecture.md",
    text: "<p>Baseline fallback text for architectural details...</p>"
  }
};

```
