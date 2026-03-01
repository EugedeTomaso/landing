# Radius + Arc Landing Page — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Design and build a landing page for Radius (AI transformation firm) + Arc (proprietary platform) using Pencil (.pen) for visual design, then generate production code.

**Architecture:** Design-first workflow. Each page section is designed in Pencil as a screen, validated visually via screenshots, then code is generated from the final design. The landing is a single-page scroll with 6 sections.

**Tech Stack:** Pencil (.pen design tool) → Code generation (HTML + Tailwind CSS)

**Reference:** Design doc at `docs/plans/2026-03-01-landing-page-design.md`

---

### Task 1: Setup Pencil Document & Style Guide

**Files:**
- Create: `designs/landing.pen` (via Pencil MCP tools)

**Step 1: Get design guidelines**

Use `mcp__pencil__get_guidelines(topic="landing-page")` to understand landing page design rules for .pen files.

**Step 2: Get style guide tags**

Use `mcp__pencil__get_style_guide_tags()` to see available style tags.

**Step 3: Get style guide**

Use `mcp__pencil__get_style_guide(tags=[...])` with tags matching: modern, tech-native, minimal, dark or light (decide based on available options), professional, clean typography. The vibe is Vercel/Stripe/Linear.

**Step 4: Open new document**

Use `mcp__pencil__open_document(filePathOrTemplate="new")` or open the .pen file if it already exists.

**Step 5: Set up design variables**

Use `mcp__pencil__set_variables()` to define:
- Color palette (based on style guide — expect dark bg + accent color, or clean white + dark text)
- Typography scale (headline, subheadline, body, caption)
- Spacing tokens (section padding, element gaps)

**Step 6: Verify**

Take a screenshot to confirm the document is ready and variables are set.

---

### Task 2: Design Hero Section

**Step 1: Find empty space on canvas**

Use `mcp__pencil__find_empty_space_on_canvas()` for a 1440x900 frame.

**Step 2: Create the hero screen**

Use `mcp__pencil__batch_design()` to create:
- Screen frame (1440px wide, ~900px tall)
- Navigation bar: Radius logo (text placeholder) left, "Get in touch" button right
- Main content centered:
  - Tagline: large heading — use one of the approved taglines from the design doc
  - Sub-copy: 2-3 sentences from the hero narrative in the design doc
  - CTA button: "Tell us what you're trying to solve"
- Keep it minimal — lots of whitespace. The hero should breathe.

**Step 3: Screenshot and verify**

Use `mcp__pencil__get_screenshot()` to verify:
- Typography hierarchy is clear (tagline dominates)
- CTA is prominent
- Spacing feels generous, not cramped
- Matches the modern/tech-native vibe

**Step 4: Fix any issues**

Iterate with `batch_design` if needed.

---

### Task 3: Design Three Phases Section (Discover, Build, Run)

**Step 1: Create the phases section**

Use `mcp__pencil__batch_design()` to create below the hero:
- Section heading: "How we work" or similar
- Three columns or cards, each containing:
  - Phase number/label ("01 Discover", "02 Build", "03 Run")
  - Short headline for each phase
  - 2-3 sentence description (use copy from design doc)
- Visual connection between phases (arrow, line, or numbered progression)
- Clean, scannable layout — the viewer should understand the 3 phases in 5 seconds

**Step 2: Screenshot and verify**

Check:
- Three phases are equally weighted visually
- Progression from left to right is clear
- Copy is readable at a glance
- Consistent with hero section styling

**Step 3: Fix any issues**

---

### Task 4: Design Arc Platform Section

**Step 1: Create the platform section**

Use `mcp__pencil__batch_design()` to create:
- Section heading: "Built on Arc"
- Sub-copy: the Arc description from the design doc
- Five capability pillars displayed as cards or icon+text blocks:
  - Intelligent Agents
  - Knowledge & Memory
  - Workflow Automation
  - Multi-Channel
  - Measurement
- Each pillar: short client-facing message (from design doc), no technical jargon
- Optional: subtle visual/illustration placeholder for each pillar
- CTA: "See Arc in action"

**Step 2: Screenshot and verify**

Check:
- Arc feels like its own product within the page
- Five pillars are scannable
- No technical jargon visible
- CTA is clear

**Step 3: Fix any issues**

---

### Task 5: Design Why Radius Section

**Step 1: Create the credibility section**

Use `mcp__pencil__batch_design()` to create:
- Anti-hype statement block (large quote or highlighted text)
- Three differentiators, each with:
  - Bold statement headline ("We built the platform.", "Strategy without execution is a slide deck.", "We measure everything.")
  - Supporting paragraph (from design doc)
- Layout: could be stacked vertically or in a grid — let the style guide inform this
- This section should feel confident and grounded

**Step 2: Screenshot and verify**

Check:
- Anti-hype statement stands out
- Three differentiators are distinct and readable
- Tone matches the brand (confident, not arrogant)

**Step 3: Fix any issues**

---

### Task 6: Design CTA Section

**Step 1: Create the contact section**

Use `mcp__pencil__batch_design()` to create:
- Headline: "Tell us what you're trying to solve."
- Sub-copy: "A free, no-commitment conversation..."
- Form with 4 fields:
  - Name (text input)
  - Company (text input)
  - Email (text input)
  - Open field: "What's the biggest operational challenge..." (textarea)
- Submit button
- Below form: "Prefer email? Reach us at hello@radius.ai"

**Step 2: Screenshot and verify**

Check:
- Form is clean and minimal
- Open field is visually larger than other inputs
- CTA button is prominent
- Email fallback is visible but secondary

**Step 3: Fix any issues**

---

### Task 7: Design Footer

**Step 1: Create the footer**

Use `mcp__pencil__batch_design()` to create:
- Minimal footer bar
- Radius logo/wordmark (left)
- "Built with Arc" text (center or right)
- Contact email
- Copyright line
- Keep it extremely simple

**Step 2: Screenshot and verify**

**Step 3: Fix any issues**

---

### Task 8: Full Page Review & Polish

**Step 1: Screenshot the entire page**

Take screenshots of each section and review the full vertical flow.

**Step 2: Check consistency**

Verify across all sections:
- Typography is consistent (same heading sizes, same body sizes)
- Spacing between sections is uniform
- Color usage is consistent
- Overall visual rhythm feels right

**Step 3: Check layout problems**

Use `mcp__pencil__snapshot_layout(problemsOnly=true)` to find any overlapping or clipped elements.

**Step 4: Fix any issues found**

Polish spacing, alignment, typography as needed.

**Step 5: Final screenshot for approval**

Take a final screenshot of each section for user approval before code generation.

---

### Task 9: Generate Code from Design

**Step 1: Get code generation guidelines**

Use `mcp__pencil__get_guidelines(topic="code")` and `mcp__pencil__get_guidelines(topic="tailwind")` to understand code generation rules.

**Step 2: Get design variables**

Use `mcp__pencil__get_variables()` to extract colors, typography, spacing as CSS/Tailwind tokens.

**Step 3: Read the full design tree**

Use `mcp__pencil__batch_get()` to read all sections and their component structure.

**Step 4: Generate HTML + Tailwind**

Create a single `index.html` file with:
- Tailwind CSS via CDN
- All 6 sections as semantic HTML
- Responsive design (desktop + mobile)
- Form with proper input types
- Smooth scroll behavior for internal links

**Step 5: Verify generated code**

Open in browser, compare against Pencil screenshots section by section.

**Step 6: Commit**

```bash
git add designs/ index.html
git commit -m "feat: landing page design + generated code for Radius + Arc"
```
