# Frontend Design v3: Distinctive, Fluid, Alive

Una guía operativa para diseñar interfaces que no parecen templates de IA. Cada decisión de color, movimiento y estructura debe venir del sujeto, no de las tendencias.

## ¿Qué es esta skill?

Es un conjunto de principios + técnicas concretas para crear interfaces que se sienten intencionales. No es un sistema de componentes, ni un design system pre-hecho. Es un checklist mental y un playbook de patrones reales que funcionan.

**Problema que resuelve:**

- Las landing pages de IA se ven todas igual: purple/indigo, blob orbs flotando, glassmorphism, 3 feature cards con emojis
- Los colores son genéricos: los mismos que usaría cualquier herramienta SaaS
- Las animaciones son decorativas: no comunican nada, solo existen
- Los fondos son oscuros pero vacíos: sin personalidad, sin textura, sin vida

**Qué te da esta skill:**

- Un test explícito de "AI Slop" — patrones que debes evitar a toda costa
- 5 técnicas reales de backgrounds animados con código funcional
- Un framework para derivar colores del sujeto, no de templates
- State machines para interacciones — no solo idle/hover
- Un checklist de crítica que te obliga a estar específico

## Estructura

### Part 0: AI Slop — Kill It First

**La sección más importante.** Lista específica de patrones que son tells instantáneos de que fue generado por IA:

- Colores exactos que debes evitar (`#6366f1`, `#8b5cf6`, `#14b8a6`)
- Layouts que son 70% de las landing pages generadas por IA
- Animaciones que son lazy defaults
- Un self-test: "Si cambio el nombre del producto, ¿sigue siendo un diseño válido?" Si sí, es un template.

### Part 1: Discovery & Strategy

Antes de tocar código:

1. ¿Qué es esto realmente? (No qué hace, sino qué es)
2. ¿Quién lo usa y qué siente?
3. ¿Cuál es el trabajo principal?

Luego: extrae el "aesthetic DNA" del sujeto:

- Materiales & texturas
- Pace & ritmo
- Lenguaje
- Luz & sombra

### Part 2: The Design System (No Defaults)

Cómo construir una paleta que sea específica de tu producto:

- **Color:** No empieces con "qué colores se ven bien". Empieza con emoción, información, estados.
- **Typography:** Display face (con moderación) + body face + mono/data face
- **Type scale:** 3–4 tamaños relacionados, no números al azar

Incluye un **Color Personality Test** con preguntas concretas:

- ¿Ese color rojo/indigo es porque el sujeto lo necesita, o lo estoy copiando de otro proyecto?
- ¿Podría esta paleta funcionar para otra industria? Si sí, no es específica.

### Part 3: Motion & Interaction (The Signature)

La sección más técnica. Está dividida en 5 partes:

**3A: Animated Backgrounds — The Technical Playbook**
5 técnicas reales con CSS y parámetros ajustables:

1. **Dot grid** — Para herramientas y dashboards. Diagonal drift que lee como "sistemático"
2. **Scan lines** — Texture de pantalla CRT, muy sutil
3. **Moving gradient mesh** — Para apps creativas/orgánicas. Drift lento en 3 capas
4. **Diagonal stripes** — Para velocidad/urgencia
5. **Noise + canvas particles** — Para atmosfera inmersiva (costoso, usar con cuidado)

Cada técnica tiene parámetros: velocidad, opacidad, tamaño. Cómo ajustarlos sin que se vea peor.

**3B: State Machine Interactions**
Define 4 estados antes de codear:

- Idle (esperando)
- Active/Processing (algo pasa)
- Success/Result (listo)
- Error (algo salió mal)

Cada estado: apariencia visual distinta + transición hacia él + señal clara al usuario.

**3C–3E: Page Load, Hover States, Micro-interactions**
Técnicas específicas con timing:

- Animaciones de entrada: stagger solo los primeros 3 elementos, o una unidad completa
- Hover: no solo color — `translateY(-2px)` + shadow shift
- Micro: Loading bar precisa, success scale, error shake

### Part 4: Layout & Structure

Hierarchy mediante densidad y proximidad. Responsive thinking desde el inicio. La importancia de la restricción — gastar "boldness" en un lugar, todo lo demás quieto.

### Part 5: Building (No Templates)

Antes de escribir CSS, escribe una descripción de 1 párrafo:

1. ¿Qué es esto?
2. ¿Cómo debería sentirse?
3. ¿Qué UNA cosa lo hace único?

Luego sigue el plan. Crítica continuamente. Itera si algún color o animación se siente como default.

### Part 6: Critique Checklist

Una serie de preguntas que te obligan a estar específico:

- ¿Pasa el AI Slop Test?
- ¿Hay algo vivo cuando nada pasa? (background siempre respirando)
- ¿Es el fondo significativo o solo "oscuro"?
- ¿Cada animación comunica algo?
- ¿Hay una máquina de estados reales, no solo idle/hover?
- **¿Funcionaría este diseño para otro producto?** (Si sí, no es específico — itera)

### Part 7: Advanced Techniques

Clip-path masking, staggered animations con CSS variables, SVG morphing, ScrollTimeline API, Intersection Observer.

### Part 8: Writing for Interfaces

Las palabras son diseño. Button labels activos, errores que explican, empty states que invitan. Todo debe servir un propósito.

### Part 9: The Anti-Template Checklist

Una lista de 7 patrones que ves constantemente en diseños AI:

- Cream background + terracotta
- Near-black + acid green
- Hairline rules + zero border-radius
- Centered everything
- Generic gradient overlays
- Identical staggered animations
- Underused whitespace con sombras pesadas

### Part 10: Quick Workflow

6 pasos de principio a fin:

1. Lee el brief → Extrae DNA
2. Plan (color, tipo, layout, motion) → Revisa contra defaults
3. Revisa si es diferente
4. Construye con motion
5. Crítica
6. Ship

## Cómo usar esta skill

### Caso 1: Estoy haciendo una landing y no quiero que parezca generada por IA

1. Lee el Part 0 completo — memoriza los colores exactos que debes evitar
2. Lee el Part 1 — extrae el sujeto
3. Lee Part 2 (color) + Part 3A (backgrounds) — elige una técnica
4. Sigue el workflow del Part 10
5. Antes de terminar, corre el checklist del Part 6

### Caso 2: Tengo animaciones en mi sitio pero se sienten decorativas/genéricas

1. Lee la sección 3A — elige una técnica de background que tenga sentido
2. Lee 3B (state machine) — define los 4 estados de tu interfaz
3. Reemplaza las animaciones por las que tienen propósito
4. Crítica: ¿esto comunica o solo existe?

### Caso 3: No sé qué colores usar

1. Lee el "Color Personality Test" en Part 2
2. Responde cada pregunta concretamente
3. Busca 3 referencias del sujeto (no de otros diseños)
4. Deriva los colores de ahí, no de templates
5. Autotest: ¿funcionaría esto para otra industria? Si sí, cambia

### Caso 4: Tengo un feedback "se ve muy AI" pero no sé qué cambiar

1. Lee Part 0 — ¿cae en alguna categoría?
2. Si sí, identifica exactamente qué (color, layout, animación, patrón)
3. Cambia eso específicamente, no todo

## Técnicas de fondo: Cheat sheet rápido

```css
/* Dot grid (sistemático, preciso) */
.bg {
	background-image: radial-gradient(
		circle,
		rgba(COLOR, 0.13) 1px,
		transparent 1px
	);
	background-size: 26px 26px;
	animation: drift 35s linear infinite;
}

/* Scan lines (textura, física) */
.overlay {
	background: repeating-linear-gradient(
		0deg,
		transparent 0,
		transparent 2px,
		rgba(0, 0, 0, 0.045) 2px,
		rgba(0, 0, 0, 0.045) 4px
	);
}

/* Gradient mesh (orgánico, vivo) */
.mesh {
	background: radial-gradient(ellipse, rgba(COLOR, 0.08) 0%, transparent 65%);
	animation: meshDrift 22s ease-in-out infinite;
}

/* Diagonal stripes (velocidad) */
.bg {
	background: repeating-linear-gradient(
		-45deg,
		transparent 0px,
		transparent 18px,
		rgba(255, 255, 255, 0.015) 18px,
		rgba(255, 255, 255, 0.015) 19px
	);
}
```

## Easing Curves por personalidad

```
Playful:  cubic-bezier(0.34, 1.56, 0.64, 1)
Modern:   cubic-bezier(0.25, 0.46, 0.45, 0.94)
Smooth:   cubic-bezier(0.4, 0, 0.2, 1)
Sharp:    cubic-bezier(0.16, 1, 0.3, 1)
Subtle:   cubic-bezier(0.165, 0.84, 0.44, 1)
```

## Lo que NO es esta skill

- No es un design system de componentes (no hay buttons, cards, inputs prediseñados)
- No es un guide de accesibilidad (aunque hay menciones)
- No es un tutorial de Figma o herramientas
- No es "cómo copiar tal design famoso"
- No te dice qué fonts usar, qué tamaños, qué espaciados exactos (eso es context-dependent)

## Lo que SÍ es

- Un mental model para criticarte a ti mismo
- Una defensa contra templates
- Un playbook de técnicas reales que funcionan
- Un framework para derivar decisiones del sujeto

## Principios clave (tl;dr)

1. **Extrae el sujeto.** Un medico studio se ve diferente de un synth shop. El fondo debe reflejar eso.

2. **Evita los tells de AI.** Memoriza los colores `#6366f1`, blob orbs, glassmorphism. No uses ninguno a menos que lo justifiques explícitamente.

3. **El fondo siempre respira.** Algo tiene que moverse — dot grid, gradient mesh, scan line shifts. Un fondo completamente estático se siente muerto.

4. **Cada animación comunica.** Si no puedes explicar qué le está diciendo al usuario, no debería estar ahí.

5. **Máquina de estados, no hover/idle.** Define 4 estados. Transiciones entre ellos. Cada uno visualmente distinto.

6. **Colores derivados, no copiados.** Mira el sujeto. ¿Qué colores naturalmente pertenecen a ese mundo? Usa esos.

7. **Crítica despiadada.** Antes de terminar: ¿funcionaría este diseño para otro producto? Si sí, no es lo suficientemente específico.

## Ejemplo: YT Downloader

Brief: "Pegá un enlace. Te devolvemos el archivo."

**Sujeto:** Una herramienta instantánea, de bajo roce, utilitaria.

**DNA:** Mecanismo preciso. Sin fricción. Velocidad. Directa. Oscura (no es amigable, es seria).

**Color:** Rojo `#FF2D20` — no el rojo de YouTube, sino el rojo de "video" + "urgencia" + "precisión". Fondo `#06080F` — no navy default, sino black puro (no-nonsense).

**Fondo:** Dot grid animado (diagonal drift) — lee como "sistemático, preciso, mecánico". Scan lines encima — texture de pantalla.

**Animación:** Input focus: border glow con easing snap. Progress bar en etapas (no loop infinito que miente). Resultado aparece con spring bounce.

**Evitado:** Los blob orbs, `backdrop-filter: blur`, `#6366f1` purple, 3 feature cards con emojis, gradient text.

## Versión

v3.0 — Enero 2025

Incluye:

- Part 0: AI Slop detection (nuevo)
- Part 3A: 5 background animation techniques (expandido y específico)
- Color Personality Test (nuevo)
- State Machine section (nuevo)
- Critique checklist mejorado
