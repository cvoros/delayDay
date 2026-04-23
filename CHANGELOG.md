# Changelog

All notable changes to delayDay will be documented here.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [0.2.4] - 2026-04-23
### Fixed
- Pitcher panel and lineup panel disappearing in landscape mode on iPhone. Bumped mobile breakpoint from 580px to 768px so all iPhones in both orientations use the single-column layout.
### Added
- No-cache meta tags to force iOS Safari to always fetch the latest version.

---

## [0.2.3] - 2026-04-23
### Added
- Pitcher panel below the batting order on the left side. Shows current pitcher's name, season ERA, game line (IP/K/BB/H), total pitch count, and full pitch mix breakdown with count, percentage, mini bar chart, and average velocity per pitch type.

---

## [0.2.2] - 2026-04-23
### Changed
- Significantly increased font sizes throughout the app for mobile readability. Bumped 21 individual CSS font-size declarations including batter names, event results, descriptions, buttons, pitch pills, and lineup panel.

---

## [0.2.1] - 2026-04-23
### Changed
- Arrow keys rewired: → now calls nextBatter(), ← calls new prevBatter() function.
### Added
- prevBatter() function: if pitches are showing, clears back to batter card; if at batter card, goes back to previous batter's completed result.
- Updated keyboard shortcut hint line to reflect new arrow behavior.

---

## [0.2.0] - 2026-04-23
### Added
- Comprehensive code comments throughout the entire JavaScript codebase. Every major function has a header block explaining what it does, why it exists, and any non-obvious decisions.
- Inline comments on all state object fields.

---

## [0.1.9] - 2026-04-23
### Added
- Keyboard shortcuts: Space (next pitch), Enter (next batter), → (next batter), ← (prev inning), T (top half), B (bottom half).
- Keyboard hint line displayed below snap controls.
- George Springer added to cheaters list.

---

## [0.1.8] - 2026-04-22
### Fixed
- Mound visits, pitching changes, and substitutions were being treated as completed at-bats, causing the next real at-bat to auto-reveal its result. Added `isRealAtBatResult()` to distinguish real at-bat outcomes from game events.

---

## [0.1.7] - 2026-04-22
### Fixed
- Scoreboard R column was only counting runs from innings before the snap point. Runs from revealed plays beyond the snap (e.g. innings 8-9 when snapped to inning 1) are now included.

---

## [0.1.6] - 2026-04-22
### Fixed
- In-progress at-bats could auto-reveal their result when auto-refresh completed them on the field. Pressing "next batter" on a play with no result now holds until the play completes.
- Added `⟳ live...` indicator (amber) when caught up to a live at-bat waiting for the result.
- `resultRevealed` flag added so results only show on explicit button press, never via auto-refresh.

---

## [0.1.5] - 2026-04-22
### Fixed
- Auto-reveal bug: plays were sliding from `ahead` into `base` as the game progressed past the snap point, causing them to appear without a button press. Added `baselineCount` to freeze the snap baseline at load time.

---

## [0.1.4] - 2026-04-22
### Fixed
- Scoreboard not appearing when snapped to the start of a game (no completed innings yet).

---

## [0.1.3] - 2026-04-22
### Added
- Houston Astros displayed as "Houston Asterisks" throughout the app.
- Players involved in the 2017 sign-stealing scandal still active in 2026 (Jose Altuve, Carlos Correa, Alex Bregman) displayed as `[CHEATER]` in red.

---

## [0.1.2] - 2026-04-22
### Fixed
- Double-tap zoom on iOS when repeatedly pressing buttons. Applied `touch-action: manipulation` globally to all buttons.
### Changed
- Swapped button order: "next batter" on left, "⚾ next pitch" on right for better thumb ergonomics on mobile.
- Buttons always visible — dim to 35% opacity when caught up to live rather than disappearing. Shows "caught up to live · new plays won't auto-reveal" message.

---

## [0.1.1] - 2026-04-22
### Added
- iPhone home screen icon (`apple-touch-icon`) using baseball diamond with clock hands design.
- Favicon using same icon.
- Open Graph meta tags for social link previews.

---

## [0.1.0] - 2026-04-22
### Added
- Initial release.
- Today's and yesterday's game list pulling from MLB Stats API.
- Pitch-by-pitch reveal with type code, velocity, and color-coded call (ball, strike, foul, in play, HBP).
- Batter card showing AVG, OPS, and position.
- Pitcher line showing ERA.
- Batting order panel with live substitution tracking, R/H/AB summary.
- Spoiler-free score (hidden by default, show/hide toggle).
- Linescore showing only revealed innings.
- "next batter" and "⚾ next pitch" reveal buttons.
- Snap controls (inning + top/bot toggle) to set your position in the game.
- Auto-refresh every 30 seconds.
- Mobile optimized layout.
- Version number on home screen.
- GitHub Pages hosting with auto-deploy on push to main.
