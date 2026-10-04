# RuralRunoff Pro — Demo

A browser-based peak discharge calculator for rural catchments, built on the Rational Method.

**▶ Try the demo:** https://pmdsc2020.github.io/rural-runoff-demo/

Built for watershed and NRM practitioners who need a defensible peak discharge figure for sizing waste weirs, spillways, culverts and drainage works — and need to show the working.

---

## What it computes

| Step | Method |
|------|--------|
| Slope | S = ΔH / L |
| Time of concentration | Kirpich (SI): t<sub>c</sub> = 0.0195 · L<sup>0.77</sup> · S<sup>-0.385</sup>, floored at 5 min |
| Rainfall intensity | Entered directly, or from an IDF formula: I = a·T<sup>m</sup> / (t<sub>c</sub> + b)<sup>n</sup> |
| Peak discharge | Rational method: Q = C · I · A / 360 (A in ha, I in mm/hr, Q in m³/s) |

Every intermediate substitution is printed out, so the calculation can be checked rather than trusted.

### Try it with these numbers

| Input | Value |
|-------|-------|
| Drainage area | 2.5 km² |
| Runoff coefficient C | 0.35 |
| Flow path length L | 1500 m |
| Elevation drop ΔH | 25 m |
| IDF coefficients | a = 1200, b = 15, m = 0.20, n = 0.75 |
| Return period | 10 years |

Expected: S = 0.0167 m/m, t<sub>c</sub> = 26.3 min, I = 116.7 mm/hr, **Q = 28.4 m³/s**

---

## Demo vs full version

The demo is not a teaser — the hydrology is complete and the numbers it produces are the real ones. What it leaves out is the record-keeping side.

| | Demo | Full |
|---|---|---|
| Rational method calculation | ✅ | ✅ |
| Step-by-step trace | ✅ | ✅ |
| Kirpich t<sub>c</sub>, IDF and direct intensity | ✅ | ✅ |
| Sanity warnings and validation | ✅ | ✅ |
| Outlet GPS capture | ✅ | ✅ |
| Copy summary as text | ✅ | ✅ |
| Composite C builder | 3 sub-areas | Unlimited |
| Save and reload catchments | — | ✅ |
| Print / PDF export for estimates | — | ✅ |
| JSON data export | — | ✅ |
| Editable regional IDF coefficient sets | — | ✅ |

**To request the full version:** message me on LinkedIn, or call **7720045808**. Free to any practitioner or organisation doing watershed work — I just like knowing where it ends up.

---

## Before you rely on any output

- **The IDF coefficients in the demo are placeholders.** Replace a, b, m, n with values fitted for your region before using IDF mode for design. The defaults produce a number, not a defensible one.
- The Rational Method assumes uniform rainfall over the catchment for a duration equal to t<sub>c</sub>. It is generally accepted up to about 25 km²; the tool warns you beyond that, where SCS-CN or a unit hydrograph is more appropriate.
- Kirpich was calibrated on small agricultural catchments with defined channels. For flat or heavily vegetated overland paths, use a different t<sub>c</sub> method and enter intensity directly.
- Runoff coefficient presets are typical published ranges. Adjust for local soil, slope and antecedent moisture.

An aid to calculation, not a substitute for engineering judgement. Check the output against your own working before it enters a sanctioned estimate.

---

## Technical

One self-contained HTML page. No framework, no build step, no server, no analytics, no external requests. Works offline once loaded, on desktop and on a phone, in light and dark mode. Nothing you enter leaves your device.

---

## Author

**Jitendra Sonawane**, Agriculture Engineer
District Programme Integrator, Development Support Centre (DSC), Nandurbar, Maharashtra

Fifteen years in rural livelihoods, watershed management and Participatory Irrigation Management.

See `NOTICE.md` for terms of use.
