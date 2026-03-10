---
task: Implement Taiwan travel frog library interactive website
slug: 20260311-120000_taiwan-travel-frog-website
effort: advanced
phase: execute
progress: 0/50
mode: interactive
started: 2026-03-11T12:00:00+08:00
updated: 2026-03-11T12:02:00+08:00
---

## Context

Build a single `index.html` file (all CSS/JS embedded) — a child-friendly interactive website for New Taipei City public library computers. Inspired by the Japanese game "旅かえる", a cartoon frog picks a daily New Taipei location from one of 3 picture books, and children help pack its luggage. The site rotates locations automatically by date, requires no login, no backend, no localStorage. Target: elementary school grades 1–6 using shared library computers.

### Risks
- CSS/SVG frog animation complexity: 3 states without external images
- Ensuring all 27 locations and 20 items are correctly populated
- Auto-reset timing and state machine edge cases
- iframe compatibility for Google Sites embedding
- Chinese font fallback if school computers can't access Google Fonts

### Plan
Build a single index.html using vanilla HTML/CSS/JS. Structure:
1. Data layer: LOCATIONS (27) + ITEMS (20) arrays
2. Logic layer: getTodayLocation, getRecommendedItems, handleItemClick, handlePackButton, resetGame, getRandomFeedback
3. Render layer: renderLocationCard, renderItemGrid, renderFrog, renderFeedback
4. CSS: Noto Sans TC + system-ui fallback, cartoon aesthetic, #4CAF50 primary
5. Frog: pure CSS/SVG - green circle face, big eyes, smile, 3 CSS keyframe states
6. Item grid: 5×4, hover tooltips, recommended highlight, selected state

## Criteria

- [ ] ISC-1: Page renders top header with title "台灣旅行樹蛙去新北～"
- [ ] ISC-2: Header displays today's date in Chinese format
- [ ] ISC-3: Left section contains frog animation area
- [ ] ISC-4: Right section contains location info card
- [ ] ISC-5: Middle section contains luggage packing area with item grid
- [ ] ISC-6: Bottom section shows packed items summary
- [ ] ISC-7: LOCATIONS array contains all 27 locations
- [ ] ISC-8: Each location has id, name, district, book, bookColor, bookName, description, weather, activity, emoji, hint
- [ ] ISC-9: ITEMS array contains all 20 items
- [ ] ISC-10: Each item has id, name, emoji, tags array
- [ ] ISC-11: getTodayLocation() calculates index from BASE_DATE 2025-01-01
- [ ] ISC-12: Same date always returns same location for all users
- [ ] ISC-13: Location rotates to next entry each calendar day
- [ ] ISC-14: Book badge displays with correct bookColor background
- [ ] ISC-15: Location name displays with emoji at 32px bold
- [ ] ISC-16: Description text displays at 18px line-height 1.8
- [ ] ISC-17: District info shows with 📍 emoji and 新北市 prefix
- [ ] ISC-18: Hint box displays below description with 💡 prefix
- [ ] ISC-19: details element present with summary click-to-expand
- [ ] ISC-20: Expanded details shows book name, cover color swatch, hint text
- [ ] ISC-21: 20 items displayed in 5-column × 4-row grid
- [ ] ISC-22: Each item cell shows 48px emoji and item name
- [ ] ISC-23: Recommended items have yellow background + star indicator
- [ ] ISC-24: Clicking item toggles selected state (green border + bg)
- [ ] ISC-25: Clicking already-selected item deselects it
- [ ] ISC-26: Pack button label shows count of currently selected items
- [ ] ISC-27: Clicking pack with 0 items shows shake animation + hint
- [ ] ISC-28: Clicking pack with 1+ items triggers pack animation
- [ ] ISC-29: Frog transitions to happy state briefly when item clicked
- [ ] ISC-30: Frog transitions to departing state after pack button
- [ ] ISC-31: Random feedback message from pool displays after packing
- [ ] ISC-32: Feedback message incorporates selected item name
- [ ] ISC-33: Feedback message incorporates today's location name
- [ ] ISC-34: Game auto-resets after 3 seconds post-packing
- [ ] ISC-35: After reset, all items return to unselected state
- [ ] ISC-36: After reset, frog returns to waiting state
- [ ] ISC-37: "再幫蛙蛙試試" message shown briefly after reset
- [ ] ISC-38: Frog rendered entirely in CSS/SVG without external images
- [ ] ISC-39: Frog is green with big round eyes and smile face
- [ ] ISC-40: Waiting state: frog on luggage with looping leg swing animation
- [ ] ISC-41: Happy state: frog jumps briefly on item click (0.3s keyframe)
- [ ] ISC-42: Departing state: frog waves hat with star sparkle effect
- [ ] ISC-43: Bottom summary shows emoji + name of last packed items list
- [ ] ISC-44: Before any packing, shows "還沒有人幫蛙蛙打包唷！快來選選看 👆"
- [ ] ISC-45: Single index.html file with all CSS/JS inline
- [ ] ISC-46: No localStorage calls anywhere in the JavaScript
- [ ] ISC-47: No framework imports (React/Vue/Angular)
- [ ] ISC-48: No external image src attributes
- [ ] ISC-49: Layout renders correctly at 1024px+ width
- [ ] ISC-50: Page functions correctly when embedded in iframe

## Decisions

## Verification
