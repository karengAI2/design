# Strata → MUI token mapping (v4)

**Status:** Draft for stakeholder discussion  
**Source:** Strata_design_tokens_v3.json — verified clean export  
**Export health:** All checks passing — no raw hex values, no unresolved references, both modes symmetrical at 150 tokens  
**Purpose:** Translation layer between Strata design tokens and MUI theme keys, enabling designers to work in Strata naming while engineering receives MUI-compatible output via an automated Style Dictionary pipeline.

---

## How to read this table

- **Dark / Light hex** columns show the resolved primitive value for each mode
- Values shown as `rgba()` are alpha-based (opacity steps) rather than solid colors — this is correct and intentional
- **MUI key** shows the closest palette mapping; `—` means no direct MUI palette key exists and the token would be applied via component override in the theme config
- **Notes** flags anything needing a decision or worth calling out

---

## Static — non-interactive surfaces

### Foreground (text and icons on static surfaces)

| Strata token | Dark hex | Light hex | MUI key | Notes |
|---|---|---|---|---|
| `static/foreground/default` | `#FAF2E9` | `#0A3235` | `palette.text.primary` | Correctly inverts between modes |
| `static/foreground/on-base` | `#0A3235` | `#FAF2E9` | — | Text on reversed surfaces; component override |
| `static/foreground/disabled` | `#858585` | `#858585` | `palette.text.disabled` | Same in both modes |
| `static/foreground/error` | `#FE908F` | `#FD4645` | — | Inline error text; component override |
| `static/foreground/opacity-50` | `rgba(cream, 0.5)` | `rgba(dark-teal, 0.5)` | `palette.text.secondary` | Subtle text |
| `static/foreground/opacity-55` | `rgba(cream, 0.55)` | `rgba(dark-teal, 0.55)` | — | ⚠️ Non-standard step — confirm distinct usage from opacity-50 |

### Background

| Strata token | Dark hex | Light hex | MUI key | Notes |
|---|---|---|---|---|
| `static/background/opacity-100/base` | `#032629` | `#FAF2E9` | `palette.background.default` | Primary page background |
| `static/background/opacity-100/reversed` | `#FAF2E9` | `#032629` | `palette.background.paper` | Inverted surface |
| `static/background/opacity-10/base` | `rgba(cream, 0.1)` | `rgba(extra-dark-teal, 0.1)` | — | Subtle tint; component override |
| `static/background/opacity-20/base` | `rgba(cream, 0.2)` | `rgba(extra-dark-teal, 0.2)` | — | Hover tint on surfaces |
| `static/background/opacity-4/base` | `rgba(cream, 0.04)` | `rgba(extra-dark-teal, 0.04)` | — | Lightest surface tint |
| `static/background/opacity-30–90/base` | rgba scale | rgba scale | — | Overlay/scrim scale; component overrides |
| `static/background/opacity-*/reversed` | Inverted of base | Inverted of base | — | All reversed variants invert the base values |

### Border

| Strata token | Dark hex | Light hex | MUI key | Notes |
|---|---|---|---|---|
| `static/border/opacity-20/base` | `rgba(cream, 0.2)` | `rgba(extra-dark-teal, 0.2)` | `palette.divider` | Primary divider/border |
| `static/border/opacity-10/base` | `rgba(cream, 0.1)` | `rgba(extra-dark-teal, 0.1)` | — | Subtle border |
| `static/border/opacity-100/base` | `#032629` | `#FAF2E9` | — | Full-opacity border; component override |
| `static/border/disabled/disabled` | `#AEAEAE` | `#AEAEAE` | — | Disabled border |
| `static/border/opacity-4–90/base` | rgba scale | rgba scale | — | Border opacity scale; component overrides |
| `static/border/opacity-*/reversed` | Inverted of base | Inverted of base | — | All reversed variants invert the base values |

---

## Action — interactive elements

### Links

| Strata token | Dark hex | Light hex | MUI key | Notes |
|---|---|---|---|---|
| `action/links/default` | `#0FCB8C` | `#F0529C` | `palette.primary.main` (light) | ⚠️ Color identity swaps between modes — confirm intentional |
| `action/links/reversed` | `#F0529C` | `#0FCB8C` | — | Inverse of default |

### Foreground (text and icons on interactive elements)

| Strata token | Dark hex | Light hex | MUI key | Notes |
|---|---|---|---|---|
| `action/foreground/base` | `#FAF2E9` | `#0A3235` | `palette.text.primary` | |
| `action/foreground/primary` | `#F0529C` | `#F0529C` | `palette.primary.main` | Same in both modes |
| `action/foreground/secondary` | `#0FCB8C` | `#0FCB8C` | `palette.secondary.main` | |
| `action/foreground/disabled` | `#717171` | `#999999` | `palette.action.disabled` | |
| `action/foreground/error` | `#FD6B6A` | `#FD4645` | `palette.error.main` | |
| `action/foreground/on-base` | `#0A3235` | `#FAF2E9` | — | Text on base-colored elements; component override |
| `action/foreground/on-primary` | `#032629` | `#032629` | `palette.primary.contrastText` | Text on pink buttons |
| `action/foreground/on-secondary` | `#032629` | `#032629` | `palette.secondary.contrastText` | Text on green buttons |
| `action/foreground/on-subtle` | `#0A3235` | `#FAF2E9` | — | Component override |
| `action/foreground/on-disabled` | `#717171` | `#717171` | `palette.action.disabled` | |
| `action/foreground/on-error` | `#FAF2E9` | `#FAF2E9` | `palette.error.contrastText` | |
| `action/foreground/icon` | `rgba(cream, 0.5)` | `rgba(dark-teal, 0.5)` | — | Default icon fill; component override |

### Background (button and element fills)

| Strata token | Dark hex | Light hex | MUI key | Notes |
|---|---|---|---|---|
| `action/background/primary/default` | `#F0529C` | `#F0529C` | `palette.primary.main` | |
| `action/background/primary/hover` | `#F375B0` | `#F375B0` | `palette.primary.dark` | |
| `action/background/secondary/default` | `#0FCB8C` | `#0FCB8C` | `palette.secondary.main` | |
| `action/background/secondary/hover` | `#3FD5A3` | `#3FD5A3` | `palette.secondary.dark` | |
| `action/background/base/default` | `#FAF2E9` | `#0A3235` | — | No MUI palette slot for this button style — ⚠️ needs decision |
| `action/background/base/hover` | `rgba(cream, 0.8)` | `rgba(dark-teal, 0.8)` | — | Component override |
| `action/background/subtle/default` | `rgba(cream, 0.5)` | `rgba(extra-dark-teal, 0.5)` | — | Subtle button fill |
| `action/background/subtle/hover` | `rgba(cream, 0.7)` | `rgba(extra-dark-teal, 0.7)` | — | |
| `action/background/extra-subtle/default` | `rgba(cream, 0.1)` | `rgba(extra-dark-teal, 0.1)` | — | |
| `action/background/extra-subtle/hover` | `rgba(cream, 0.2)` | `rgba(extra-dark-teal, 0.2)` | — | |
| `action/background/disabled` | `#AEAEAE` | `#AEAEAE` | `palette.action.disabledBackground` | |
| `action/background/error/default` | `#FD4645` | `#FD4645` | `palette.error.main` | |
| `action/background/error/hover` | `#FD6B6A` | `#FD6B6A` | `palette.error.dark` | |
| `action/background/text/hover` | `rgba(cream, 0.2)` | `rgba(dark-teal, 0.2)` | — | Text button hover fill; component override |
| `action/background/ghost/hover` | `rgba(cream, 0.04)` | `rgba(dark-teal, 0.04)` | — | Ghost button hover fill; component override |

### Border

| Strata token | Dark hex | Light hex | MUI key | Notes |
|---|---|---|---|---|
| `action/border/primary` | `#F0529C` | `#F0529C` | — | Outlined primary button border; component override |
| `action/border/secondary` | `#0FCB8C` | `#0FCB8C` | — | Outlined secondary button border |
| `action/border/base` | `#FAF2E9` | `#0A3235` | — | Base outlined button border |
| `action/border/error` | `#FE908F` | `#FD4645` | — | Error border |
| `action/border/disabled` | `#999999` | `#AEAEAE` | — | |
| `action/border/ghost/default` | `rgba(cream, 0.4)` | `#9FBABC` | — | Ghost button border |
| `action/border/ghost/base/default` | `rgba(cream, 0.8)` | `#407579` | — | |
| `action/border/ghost/base/hover` | `#FAF2E9` | `#105257` | — | |
| `action/border/ghost/primary/default` | `#F697C4` | `#F697C4` | — | |
| `action/border/ghost/primary/hover` | `#F0529C` | `#F0529C` | — | |
| `action/border/ghost/secondary/default` | `#6FE0BA` | `#6FE0BA` | — | |
| `action/border/ghost/secondary/hover` | `#0FCB8C` | `#0FCB8C` | — | |
| `action/border/ghost/subtle/default` | `rgba(cream, 0.2)` | `rgba(dark-teal, 0.2)` | — | |
| `action/border/ghost/subtle/hover` | `rgba(cream, 0.4)` | `rgba(dark-teal, 0.4)` | — | |
| `action/border/ghost/error/default` | `#FE908F` | `#FE908F` | — | |
| `action/border/ghost/error/hover` | `#FD4645` | `#FD4645` | — | |
| `action/border/ghost/disabled` | `#717171` | `#999999` | — | |

---

## Field — form inputs

### Foreground

| Strata token | Dark hex | Light hex | MUI key | Notes |
|---|---|---|---|---|
| `field/foreground/value` | `#FAF2E9` | `#0A3235` | — | Input text color; component override |
| `field/foreground/base/default` | `rgba(cream, 0.8)` | `rgba(dark-teal, 0.8)` | — | Base foreground state |
| `field/foreground/base/hover` | `#FAF2E9` | `#0A3235` | — | |
| `field/foreground/placeholder` | `rgba(cream, 0.5)` | `rgba(extra-dark-teal, 0.5)` | — | Placeholder text |
| `field/foreground/error` | `#FE908F` | `#FD4645` | — | |
| `field/foreground/disabled` | `#717171` | `#999999` | — | |
| `field/foreground/selected` | `#FAF2E9` | `#0A3235` | — | Selected text color |

### Label

| Strata token | Dark hex | Light hex | MUI key | Notes |
|---|---|---|---|---|
| `field/label/value` | `#0A3235` | `#FAF2E9` | — | ⚠️ Note: inverted from field/foreground/value — label sits outside the input |
| `field/label/helper` | `rgba(dark-teal, 0.7)` | `rgba(cream, 0.7)` | — | Helper/hint text |
| `field/label/error` | `#FE908F` | `#FD4645` | — | |
| `field/label/disabled` | `#717171` | `#999999` | — | |

### Background

| Strata token | Dark hex | Light hex | MUI key | Notes |
|---|---|---|---|---|
| `field/background/base/default` | `#0A3235` | `#FFFFFF` | — | Input fill; component override |
| `field/background/base/hover` | `rgba(cream, 0.1)` | `#E7EEEE` | — | |
| `field/background/disabled` | `#717171` | `#C2C2C2` | — | |
| `field/background/select` | `#FFFFFF` | `#F5F7F7` | — | Dropdown selected item background; uses dark-teal/04-tint in light mode |
| `field/background/ghost/hover` | `rgba(cream, 0.2)` | `rgba(dark-teal, 0.2)` | — | |

### Border

| Strata token | Dark hex | Light hex | MUI key | Notes |
|---|---|---|---|---|
| `field/border/base/default` | `rgba(cream, 0.2)` | `rgba(dark-teal, 0.2)` | — | Default input border |
| `field/border/base/hover` | `rgba(cream, 0.5)` | `#0A3235` | — | |
| `field/border/disabled` | `#999999` | `#999999` | — | Same in both modes |
| `field/border/error` | `#FE908F` | `#FD4645` | — | |
| `field/border/primary/default` | `#F375B0` | `#F375B0` | — | Focus border (primary) |
| `field/border/primary/hover` | `#F0529C` | `#F0529C` | — | |
| `field/border/secondary/default` | `#3FD5A3` | `#3FD5A3` | — | Focus border (secondary) |
| `field/border/secondary/hover` | `#0FCB8C` | `#0FCB8C` | — | |

### Icon

| Strata token | Dark hex | Light hex | MUI key | Notes |
|---|---|---|---|---|
| `field/icon/base` | `rgba(cream, 0.5)` | `#407579` | — | Default input icon |
| `field/icon/active` | `#FAF2E9` | `#105257` | — | Active/focused |
| `field/icon/primary` | `#F0529C` | `#F0529C` | — | |
| `field/icon/secondary` | `#0FCB8C` | `#0FCB8C` | — | |
| `field/icon/error` | `#FE908F` | `#FD4645` | — | |
| `field/icon/disabled` | `#717171` | `#C2C2C2` | — | |

---

## Feedback — status states

All four status colors confirmed in Layer 1. Values are identical in both modes unless noted.

### Error

| Strata token | Dark hex | Light hex | MUI key |
|---|---|---|---|
| `feedback/error/background` | `#FD4645` | `#FD4645` | `palette.error.main` |
| `feedback/error/border` | `#FE908F` | `#FE908F` | `palette.error.light` |
| `feedback/error/foreground` | `#FAF2E9` | `#FAF2E9` | `palette.error.contrastText` |
| `feedback/error/hovered/fill` | `#FD6B6A` | `#FD6B6A` | `palette.error.dark` |
| `feedback/error/hovered/stroke` | `#FD4645` | `#FD4645` | `palette.error.main` |

### Warning

| Strata token | Dark hex | Light hex | MUI key |
|---|---|---|---|
| `feedback/warning/fill` | `#FFA31C` | `#FFA31C` | `palette.warning.main` |
| `feedback/warning/stroke` | `#FFC877` | `#FFC877` | `palette.warning.light` |
| `feedback/warning/contrast` | `#032629` | `#032629` | `palette.warning.contrastText` |
| `feedback/hovered/fill` | `#FFB549` | `#FFB549` | `palette.warning.dark` |
| `feedback/hovered/stroke` | `#FFA31C` | `#FFA31C` | `palette.warning.main` |

### Confirmation (success)

| Strata token | Dark hex | Light hex | MUI key | Notes |
|---|---|---|---|---|
| `feedback/confirmation/fill` | `#549C35` | `#549C35` | `palette.success.main` | Note: distinct from brand green `#0FCB8C` |
| `feedback/confirmation/stroke` | `#98C486` | `#98C486` | `palette.success.light` | |
| `feedback/confirmation/contrast` | `#FAF2E9` | `#FAF2E9` | `palette.success.contrastText` | |
| `feedback/confirmation/hovered/fill` | `#76B05D` | `#76B05D` | `palette.success.dark` | |
| `feedback/confirmation/hovered/stroke` | `#549C35` | `#549C35` | `palette.success.main` | |

### Information

| Strata token | Dark hex | Light hex | MUI key |
|---|---|---|---|
| `feedback/information/fill` | `#2A88EF` | `#2A88EF` | `palette.info.main` |
| `feedback/information/stroke` | `#7FB8F5` | `#7FB8F5` | `palette.info.light` |
| `feedback/information/contrast` | `#032629` | `#032629` | `palette.info.contrastText` |
| `feedback/information/hovered/fill` | `#55A0F2` | `#55A0F2` | `palette.info.dark` |
| `feedback/information/hovered/stroke` | `#2A88EF` | `#2A88EF` | `palette.info.main` |

---

## Open questions for stakeholder meeting

1. **`action/links` color swap between modes** — in dark mode the default link is green, in light mode it's pink. If intentional, document it; if not, one mode needs correcting.

2. **`action/background/base`** — the teal/base button color has no MUI palette slot. Options: add a custom `palette.base` key to the MUI theme, map it to an existing slot, or handle entirely via component overrides. Needs an engineering decision.

3. **Field tokens and MUI** — most field tokens have no direct MUI palette equivalent and would be applied via MUI's `components` override section in `createTheme`. Engineering should confirm this approach works for their implementation pattern.

4. **Alpha-based tokens** — many tokens use `rgba()` rather than resolved hex. Style Dictionary handles this natively but the output format (CSS `rgba()` vs hex8) should be confirmed with engineering based on their target environment.

---

## Pipeline notes

- **File format:** JSON array of collection objects — Style Dictionary config will need to unwrap the array before processing
- **Mode handling:** Dark and light are nested under `color – semantic (palette).modes` — pipeline config should generate separate outputs per mode, or use Style Dictionary's built-in theming support
- **Hover pattern:** All interactive tokens follow a consistent `default`/`hover` sibling structure — no custom transforms needed for state handling
- **All references resolve cleanly** — no custom resolution logic required for the primitive lookup
