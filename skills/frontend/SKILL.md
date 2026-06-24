---
name: frontend-design-v3
description: Advanced visual design guidance for creating distinctive, fluid interfaces with intentional motion, animated backgrounds, and no AI-slop defaults. Every choice is derived from the subject—not from trends.
version: 3.0
---

# Frontend Design v3: Distinctive, Fluid, Alive

You're the design strategist at a studio that builds interfaces people remember. Not because they're shiny, but because they *feel* intentional. Every animation, every color, every interaction has a reason. Your job is to help create something that could never be mistaken for a template.

---

## Part 0: AI Slop — Kill It First

Before designing anything, run this checklist. These are the patterns AI generates by default, regardless of the brief. If you catch yourself here, stop and change course.

### The instant tells (specific, with hex values):

**Colors that scream AI:**
- Purple/indigo dominant: `#6366f1`, `#8b5cf6`, `#4f46e5` on dark backgrounds → instant AI tell
- "Dark mode teal": `#14b8a6`, `#0d9488` → overused AI SaaS default
- Dark navy background: `#1e1b4b`, `#1a1f3a`, `#1e293b` → AI dark mode cliché
- Warm cream + terracotta: `#F4F1EA` bg + `#D85A30` accent → AI "editorial" default
- Acid green + near-black: `#A8FF3E` or `#39FF14` on `#0a0a0a` → AI "hacker" default

**Layout patterns that scream AI:**
- Hero: big gradient headline + floating gaussian blob orbs in background + glassmorphic card + 3 feature cards with emoji icons below. This is the default output for ~70% of AI-generated landing pages. If your layout follows this shape, you're in template territory.
- Perfectly centered everything with uniform whitespace → neutral, forgettable
- `backdrop-filter: blur(20px)` on every card → glassmorphism is dated and lazy
- `-webkit-background-clip: text` gradient text as the primary headline treatment → decoration masquerading as personality

**Animation patterns that scream AI:**
- Floating blob orbs: `@keyframes float` applied to multiple blurred circles in the background → this is not "ambient motion," it's a tell
- Everything animates identically: same duration, same easing, different delays → template
- `animation: fadeInUp 0.5s ease` on every single element → lazy stagger
- Hover: color change only → no sense of depth or physicality

**The self-test:** If you changed the brand name and kept the design, would it still "work"? If yes, you've applied a template — not designed for the subject.

---

## Part 1: Discovery & Strategy

### Ground it in the subject

Before touching any code, nail these three things:

1. **What is this, really?** (Not what it does—what it *is*)
   - A marketplace? A journal? A control panel? A playground?
   - Name the subject and its world. Build from there.

2. **Who uses it, and what do they feel?**
   - A financial dashboard feels different than a music creation tool.
   - The interface should *feel* like it belongs in that world.

3. **What's the single job of this page/interface?**
   - Not everything it can do—the *primary* reason someone lands here.
   - Design to that job first. Everything else is supporting cast.

### Extract the aesthetic DNA

Look at the subject itself for clues:
- **Materials & textures**: Is it mechanical, organic, digital, tactile?
- **Pace & rhythm**: Does it move fast, slow, in bursts, or methodically?
- **Language**: Does it speak technically, poetically, casually, urgently?
- **Light & shadow**: Is it bright/optimistic, dark/moody, high-contrast, soft?

This is where you find your color palette, animation timing, typography, and spacing—not from design trends.

---

## Part 2: The Design System (No Defaults)

### Color: Meaning, not decoration

Don't start with "what colors look good together." Start with:
- **What emotion does the subject evoke?**
- **What information needs to stand out?**
- **What should feel active vs. passive?**

Then build a **4–6 color palette** with intentional roles:

```
Primary (action): The hero color — use it sparingly, it should demand attention
Secondary (context): Complements the primary, creates depth
Accent (micro): For interactive moments, warnings, success states
Neutral range (3–4 shades): Background → text, with purpose at each level
```

**The Color Personality Test** — before finalizing, ask each of these:

1. Is my accent any of these? `#6366f1` `#8b5cf6` `#14b8a6` `#10b981` → If yes: WHY does THIS specific subject require this color? If you can't answer immediately, change it.

2. Could this palette work for a different product in a totally different industry? If yes, it's not specific enough.

3. What does the subject physically look like, feel like, or smell like? A recording studio is different from a hospital is different from a bakery — their color temperature should differ too.

4. Are your neutrals truly neutral, or are they "dark mode navy defaults"? (`#0f172a`, `#1e293b` are Tailwind defaults, not choices.)

**Derive, don't pick:**
- A legal tech tool: dark slate + deep amber (authority, precision)
- A food delivery app: warm off-white + deep terracotta (appetite, warmth)
- A video downloader: near-black (utility) + sharp red (video, urgency, precision)
- A meditation app: very light stone + muted sage (calm, natural)
- A dev tool: true black + electric accent (no-nonsense, terminal)

**Example**: A meditation app shouldn't use the same palette as a trading platform, even if the colors are technically "nice." The first needs calming, organic tones; the second needs clarity and contrast.

### Typography: Personality first

Two-face pairing is minimum; three faces gives you range:

1. **Display face** (headlines, hero): One characterful typeface used with *restraint*
   - Not every heading, just the big moments
   - Examples: EB Garamond (elegant), Space Mono (technical), Unbounded (modern)

2. **Body face** (reading, description): Highly legible, complements the display
   - Should feel at home next to the display face
   - Examples: Inter (neutral), Georgia (classic), Caladea (warm)

3. **Mono/Data face** (optional, code, numbers): If your interface deals in precision
   - Courier Prime, IBM Plex Mono, JetBrains Mono

**Type scale with intention:**
- Don't just make sizes. Make them work *together*.
- Example: `10px` (caption), `12px` (label), `14px` (body), `18px` (subhead), `32px` (display), `48px` (hero)
- Weight, line-height, letter-spacing all matter—they're not neutral.

---

## Part 3: Motion & Interaction (The Signature)

This is where generic designs die and yours comes alive.

### Motion is not decoration — it's communication

Every animation answers: **"What is this movement telling the user?"**

---

### 3A: Animated Backgrounds — The Technical Playbook

The background is the canvas. It should breathe, drift, or pulse in a way that's specific to the subject. Here are five real techniques, each with working CSS:

#### Technique 1: Animated dot grid (precision/technical)
Best for: tools, dashboards, utilities. Feels systematic and alive without being loud.
```css
.bg {
  background-color: #06080F;
  background-image: radial-gradient(circle, rgba(ACCENT, 0.13) 1px, transparent 1px);
  background-size: 28px 28px;
  animation: dotDrift 35s linear infinite;
}
@keyframes dotDrift {
  to { background-position: 28px 28px; }
}
```
Dial it: increase `background-size` for more open feel, lower alpha for subtlety, change the accent color to match your palette. The seamless diagonal drift reads as technical, precise.

#### Technique 2: Scan line overlay (CRT/screen texture)
Best for: tech, precision tools, developer products. Applied as an overlay on top of any background.
```css
.scanlines {
  position: absolute;
  inset: 0;
  background: repeating-linear-gradient(
    0deg,
    transparent 0, transparent 2px,
    rgba(0,0,0,0.04) 2px, rgba(0,0,0,0.04) 4px
  );
  pointer-events: none;
}
```
Very subtle — barely visible — but adds a tactile, physical quality. Makes the screen feel like a surface rather than a void.

#### Technique 3: Moving gradient mesh (ambient, organic)
Best for: creative tools, music apps, portfolio sites. Feels organic, warm, alive.
```css
.mesh-layer {
  position: absolute;
  width: 800px; height: 600px;
  background: radial-gradient(ellipse at center, rgba(ACCENT, 0.08) 0%, transparent 65%);
  animation: meshDrift 22s ease-in-out infinite;
  top: -200px; left: -200px;
  pointer-events: none;
}
@keyframes meshDrift {
  0%, 100% { transform: translate(0, 0); }
  33%  { transform: translate(80px, 60px); }
  66%  { transform: translate(-40px, 120px); }
}
```
Note: this is a slow-moving soft glow, not a harsh gradient. Keep alpha low (0.06–0.10). Use 2–3 layers offset from each other for depth.

#### Technique 4: Moving diagonal stripes (velocity, urgency)
Best for: sports, action, high-energy contexts. Suggests movement and direction.
```css
.bg {
  background-color: #08090E;
  background-image: repeating-linear-gradient(
    -45deg,
    transparent 0px,
    transparent 18px,
    rgba(255,255,255,0.015) 18px,
    rgba(255,255,255,0.015) 19px
  );
  animation: stripeDrift 8s linear infinite;
}
@keyframes stripeDrift {
  to { background-position: 50px 50px; }
}
```
At this opacity it's almost invisible — reads as texture, not pattern. Increase for a bolder effect.

#### Technique 5: Noise + canvas particles (immersive, atmospheric)
Best for: creative, gaming, music. Use sparingly — it's expensive and can dominate.
```js
const canvas = document.createElement('canvas');
// ... place behind content, draw 80-120 slow-drifting dots with requestAnimationFrame
// Each particle: random position, very low opacity, random radius 1-2px
// Drift: each frame, move by Math.sin(t + offset) * 0.3 in x, Math.cos(t + offset) * 0.2 in y
```
Params that matter: particle count (80 max), opacity (0.05–0.15 max), speed (very slow), size (1–2px). More than this and it becomes noise that fights the content.

---

### 3B: State Machine Interactions

Interfaces aren't just static → hover. They're state machines. Define every state before you code:

**State 1 → Idle**: Default, waiting for input
**State 2 → Active/Processing**: Something is happening, user is waiting
**State 3 → Success/Result**: The job is done
**State 4 → Error**: Something went wrong

Each state should have:
- A distinct visual appearance
- A transition *into* it (not just appearing)
- A clear signal to the user about what to do next

**Progress bars that feel precise, not fake:**
```js
// Don't: CSS animation loop that looks busy but means nothing
// Do: Step-based progress that reflects real stages
const stages = [
  [300,  28, 350],   // [delay_ms, target_pct, transition_ms]
  [900,  62, 500],
  [1600, 84, 700],
  [2200, 100, 300],
];
stages.forEach(([delay, pct, dur]) => {
  setTimeout(() => {
    fill.style.transition = `width ${dur}ms cubic-bezier(0.25, 0.46, 0.45, 0.94)`;
    fill.style.width = pct + '%';
  }, delay);
});
```

---

### 3C: Page Load & Entrance

- **One animation, not many**: Animate the whole content zone in as a unit, not 12 separate elements
- **Or**: Stagger only the top 3 elements (hero, sub, CTA) — after that, content should just be there
- Timing: `0.6–0.8s`, easing `cubic-bezier(0.16, 1, 0.3, 1)` (snappy spring)
- Never: fade everything in at the same time with `animation-delay` increments of 0.1s per div — that's template stagger

### 3D: Hover & Interactive States

- **Buttons**: Not just color change. At minimum: `transform: translateY(-2px)` + shadow shift
- **Cards**: `translateY(-6px)` + border color shift (no blur)
- **Inputs**: Border animates to accent color, background very subtly shifts (no scale)
- Timing: `150–200ms` for instant responsiveness feel
- Always: `will-change: transform` on elements that animate transform

### 3E: Micro-interactions

- Loading: a thin `2px` line that fills precisely — not a spinner, not a blob
- Success: element scales up 1% then settles: `transform: scale(1.01)` → `scale(1)` at 200ms
- Error: horizontal shake: `@keyframes shake { 0%,100% {translate:0} 25% {translate:-4px} 75% {translate:4px} }`
- Navigation transitions: content fades out (100ms) then new content fades in from Y+8px

**Rule of thumb**: If you find yourself saying "I'll add animation," that's usually wrong. Animation should emerge from the design direction, not be bolted on.

---

## Part 4: Layout & Structure (Information Design)

### Hierarchy through density and proximity

- **Whitespace is a tool**: Use it to group related things and separate unrelated ones
- **Alignment**: Grid or justified? Either is fine; be intentional
- **Asymmetry**: Sometimes dynamic, sometimes awkward—know which
- **Numbered steps/markers**: ONLY if the content is actually a sequence. Don't use 01/02/03 just because it looks design-y

### Responsive thinking from the start

- Mobile: How does this *feel* at 375px? Does the personality survive?
- Tablet: Is there an in-between state, or does it skip?
- Desktop: Can you use whitespace, or should everything be denser?

Don't just shrink. Redesign for each breakpoint if the content demands it.

### Restraint: The hard part

- **Spend your boldness in one place.** That's your signature moment.
- Everything around it? Quiet, disciplined, supporting the star.
- If an element doesn't serve the brief, cut it. Seriously.

---

## Part 5: Building (No Templates)

### Before you code

Write a **design brief (1 paragraph)** that nails:
1. What is this interface?
2. What should it feel like?
3. What's one unique thing about it?

Example:
> "A minimalist password manager that feels like a physical safe being opened. Dark, secure, but not cold. When you unlock it, information slides out smoothly. Every interaction feels deliberate and tactile. The signature moment: the unlock animation that builds tension then releases."

### CSS and Motion Principles

**Easing is personality:**
```css
/* Confident, modern */
transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);

/* Bouncy, playful */
transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);

/* Smooth, luxe */
transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);

/* Snappy, responsive */
transition: all 0.15s cubic-bezier(0.16, 1, 0.3, 1);
```

**Avoid these generic patterns:**
- Fade-in-fade-out on *everything* (lazy)
- Bounce animations everywhere (dated)
- Staggered lists that all animate identically (template)
- Gradients that don't mean anything (decoration)

**Do this instead:**
- Purposeful, directional movement (something *arrives* or *reveals*)
- Motion that echoes the interface personality
- Timing and easing that reinforces the brand feeling
- Minimal, specific animations that land hard

### CSS Best Practices for Animation

```css
/* Use transform for 60fps animations, not left/top */
.element {
  transition: transform 0.3s ease-out;
}

.element:hover {
  transform: translateY(-4px) scale(1.02);
}

/* Use will-change sparingly */
.animated-hero {
  will-change: transform;
}

/* Respect prefers-reduced-motion */
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

### Responsive Animation

- Smaller screens: Shorter durations, simpler moves (users expect snappier)
- Larger screens: Can breathe with longer enters, parallax, ambient motion
- Touch devices: Hover states become tap states; don't rely on hover

---

## Part 6: Critique Checklist

Before you ship it:

- [ ] **Does it pass the AI Slop Test?** (Part 0 checklist — no purple/indigo AI defaults, no blob orbs, no glassmorphism)
- [ ] **Is there ONE element alive when nothing else is happening?** (Background texture drifting, ambient motion — something always breathing)
- [ ] **Is the background meaningful, not just dark?** (It should feel like it belongs to THIS subject, not any dark-mode interface)
- [ ] **Does motion tell something**, or does it just exist?
- [ ] **Is there a real state machine?** (Not just idle/hover — idle/active/success/error, each visually distinct with transitions between them)
- [ ] **Is the pace consistent with the subject?** (Fast UI for fast work, slow for contemplation)
- [ ] **Does it work on mobile** without losing personality?
- [ ] **Can you remove one element** and it looks better? (Chanel's mirror test)
- [ ] **Would this design make sense for a different product?** (If yes, it's not specific enough — iterate)
- [ ] **Does a person unfamiliar with the subject still understand what this is** from the interface alone?

If any answer is "no", you're close to a template — iterate.

---

## Part 7: Advanced Techniques for Distinctive Motion

### Clip-path masking with animation
```css
@keyframes revealWithClip {
  from {
    clip-path: inset(0 100% 0 0);
  }
  to {
    clip-path: inset(0 0 0 0);
  }
}
```
Great for text reveals, hero images, dramatic unveils.

### Staggered animations with CSS variables
```css
.list-item {
  --delay: calc(var(--index) * 0.08s);
  animation: slideUp 0.6s cubic-bezier(0.34, 1.56, 0.64, 1) var(--delay) both;
}
```
Each item animates in sequence, with control.

### SVG morphing and filters
- SVG paths can morph between shapes (smooth state transitions)
- Filters (blur, drop-shadow, turbulence) add dimension
- Combined with animation, these feel premium

### Scroll-driven animations (ScrollTimeline API)
```css
@supports (animation-timeline: scroll()) {
  .element {
    animation-timeline: view();
    animation: revealAsYouScroll linear;
  }
}
```
Modern browsers: Elements animate *exactly* as they scroll into view.

### Gesture-aware animations (Intersection Observer + motion preferences)
- Detect when elements enter viewport
- Respect `prefers-reduced-motion` automatically
- Layered animations that stack complexity (not overwhelm)

---

## Part 8: Writing for Interfaces (Words as Design)

Words are *not* separate from design—they're part of it.

- **Button labels**: Active voice, clear action. "Save changes," not "Submit."
- **Errors**: Explain what broke and how to fix it. Don't apologize.
- **Empty states**: An invitation to act, not mood-setting copy.
- **Micro-copy**: "Loading your workspace..." is better than "Loading..."
- **Tone**: Match the interface personality. A financial tool feels different than a creative tool.

---

## Part 9: The Anti-Template Checklist

If you find yourself doing *any* of these, pause and ask why:

- Warm cream background (#F4F1EA) + terracotta accent + serif display
- Near-black background + acid-green accent + minimal UI
- Hairline rules, zero border-radius, broadsheet-style columns
- Perfectly centered content with large gaps
- Generic gradient overlays
- Identical staggered animations on all list items
- Underused whitespace compensated with shadows or gradients

These aren't *wrong*—they're just default choices that appear regardless of subject. Your job is to make choices *for this specific brief.*

---

## Part 10: Quick Workflow

1. **Read the brief** → Extract the subject's DNA
2. **Design plan** (color, type, layout, motion signature) → Review against defaults
3. **Revise if needed** → Make sure it's *different*
4. **Build with motion** → Every animation has a reason
5. **Critique** → Does it feel alive and intentional?
6. **Ship** → It should feel like no one else could have made it

---

## Quick Reference: Easing Curves for Mood

| Mood | Easing | Use Case |
|------|--------|----------|
| Playful | `cubic-bezier(0.34, 1.56, 0.64, 1)` | Bouncy interactions, fun UIs |
| Modern | `cubic-bezier(0.25, 0.46, 0.45, 0.94)` | Confident, slightly snappy feel |
| Smooth | `cubic-bezier(0.4, 0, 0.2, 1)` | Luxe, professional, premium |
| Sharp | `cubic-bezier(0.16, 1, 0.3, 1)` | Responsive, energetic, snappy |
| Subtle | `cubic-bezier(0.165, 0.84, 0.44, 1)` | Minimal, contemplative |

---

## Final Thought

The best designed interfaces don't announce themselves. They *feel* right for what they are. Your job is to understand the subject deeply enough that every choice—color, motion, type, space—flows naturally from it. That's not generic. That's distinctive.

Make something only you could make.
