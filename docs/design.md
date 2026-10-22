# design.md

## Vibe
Dark, bold, playful fintech. Big numbers, punchy copy, motion on every card. Feels like a story, not a spreadsheet.

## Tokens (adjust on Day 11)
- bg #0B0B12, surface #14141F, text #F5F5FA, muted #8B8BA3
- accent lime #C6FF3D, violet #7C5CFF, pink #FF4D8D
- Radius 24px cards, generous spacing, one accent color per card
- Fonts: Space Grotesk (headings, numbers), Inter (body), via next/font

## Layout
- Mobile-first (most users are on phones). Story format 9:16, swipe/tap to advance, progress bar on top.
- Desktop: centered 9:16 card on a blurred gradient background.

## Motion
- Numbers count up. Cards slide in with spring easing. Max 600ms per transition.
- Respect prefers-reduced-motion.

## Copy tone
Witty, light Hinglish flavor, never shaming. Example: "Swiggy knows you better than your family." No judging amounts.

## The 8 cards (MVP)
1. Intro: total spent + number of payments
2. Your #1 merchant ("your regular")
3. Top categories (bars)
4. Late-night spender (time-of-day heat strip)
5. Weekend vs weekday split
6. Biggest single payment
7. Busiest day / month
8. Spending personality (rule-based archetype) + share button

## Share card
1080x1920 PNG, one card or a summary card, domain watermark bottom. No raw merchant names beyond top 3 (privacy by default), with a "hide amounts" toggle.

## Landing page
Hero with live animated demo using fake data, "100% in your browser" badge, 3-step how it works, FAQ, how-to-export links.

## Accessibility
Contrast AA, keyboard navigation for cards, alt text on share image, reduced motion.

## Design skills (Claude teaches one per UI day, and uses them to review screenshots)
1. **Hierarchy:** one hero element per screen. If everything is loud, nothing is. Squint test: can you still tell what matters?
2. **Spacing:** use an 8px scale (8/16/24/32/48). Consistent gaps feel professional. Group related things closer than unrelated things.
3. **Type:** max 2 fonts, 3-4 sizes. Big numbers = display font, tight tracking. Body 16px+ on mobile, line-height ~1.5.
4. **Color:** 60% background, 30% surface, 10% accent. One accent per card. Check contrast.
5. **Motion:** every animation must explain something (count-up = value, slide = next). Under 600ms, ease-out/spring, respect reduced motion.
6. **Copy:** write like a funny friend, not a bank. Short, specific, never shaming. Real numbers beat adjectives.
7. **Details that feel human:** slightly imperfect touches (a sticker-style badge, a hand-drawn underline, an emoji used with intent), custom empty/error states with personality, satisfying micro-interactions.
8. **Mobile first:** thumb-reachable actions, 44px tap targets, test at 375px width.

## Anti-generic checklist (reject if it fails)
- Looks like a template? Add one distinctive element (shape, texture, sticker, oversized type).
- Default purple-blue gradient, glassmorphism everywhere, or emoji-as-icons for everything? Rethink.
- Everything centered with equal weight? Create contrast in size and position.
- Placeholder or lorem copy anywhere? Replace with real copy.

## Design confirmation gate
For each new screen/card: taste options -> preview in chat -> my approval -> then build -> screenshot review. Record approved decisions below.

## Approved decisions
(empty. Claude adds each approved choice here during wrap-up)
