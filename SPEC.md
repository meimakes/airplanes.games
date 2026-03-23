# airplanes.games — Site Spec

Build a static site for airplanes.games with a launcher page (index.html) and 5 games.
All games are pure HTML/CSS/JS — zero dependencies. Touch-friendly, mobile-first.
Use the Fredoka Google Font throughout.

## Assets
9 real plane images in assets/ (plane-1.png through plane-9.png). Use these as img tags in the games — NOT canvas-drawn planes. The images are PNGs with transparency.

Plane names for display:
- plane-1.png: Cessna
- plane-2.png: Spitfire  
- plane-3.png: F-16
- plane-4.png: Helicopter
- plane-5.png: Airbus A380
- plane-6.png: Boeing 747
- plane-7.png: Concorde
- plane-8.png: Antonov (Side)
- plane-9.png: Antonov (Bottom)

## Launcher (index.html)
Clean, parent-friendly launcher page. Light/bright daytime theme (NOT dark).
Each game gets a card with:
- Game name + icon
- A tag showing developmental benefit (e.g. "Pattern Recognition", "Counting", "Problem Solving", "Spatial Reasoning", "Matching")
- Difficulty rating as dots (1-3 filled dots)
- Links to the game HTML file

Games on the launcher:
1. Landing Path (/landing-path.html) — Spatial Reasoning — ●●○
2. Pattern Lab (/pattern-lab.html) — Pattern Recognition — ●○○ to ●●●○ (show ●●○)
3. Logic Hangar (/logic-hangar.html) — Matching & Sorting — ●●○
4. Flight Path (/flight-path.html) — Problem Solving — ●●●
5. Cargo Count (/cargo-count.html) — Counting — ●○○

## Game 1: Landing Path (landing-path.html)
Already exists as landing-path.html. Leave it mostly as-is but:
- Make sure the daytime theme is consistent
- Add a home button (link back to index.html) in top-left corner

## Game 2: Pattern Lab (pattern-lab.html)
Pattern completion. Show 6 airplane images in a row, last one is hidden behind a "?" slot.
3 airplane choices below — drag the correct one into the empty slot.

4 difficulty levels:
1. Simple (AB): A, B, A, B, A, ?
2. Doubles (AABB): A, A, B, B, A, ?
3. Complex (ABC): A, B, C, A, B, ?
4. Mirror (ABA): A, B, A, A, B, ?

Use random plane images each round. Wrong = shake. Correct = confetti + big emoji.
Auto-advance after 3 correct in a row per level.
Home button top-left.

## Game 3: Logic Hangar (logic-hangar.html)
Matching/sorting on a tarmac. Show 3-4 hangars with a plane image on each sign.
Shuffled plane cards below — drag each to its matching hangar.

4 levels:
1. 3 hangars, color-coded outlines on cards to help match
2. 4 hangars, color assist
3. 3 hangars, NO color assist
4. 4 hangars, no assist

Wrong drops shake. All correct = celebration.
Home button top-left.

## Game 4: Flight Path (flight-path.html)
Maze navigation. Randomly generated maze, airplane at START (bottom-left), runway at GOAL (top-right).
Storm clouds ⛈️ as obstacles. Arrow buttons on screen + keyboard arrows/WASD.
Blue trail shows where they've been.

4 levels:
1. Cadet: 5×5, 2 storms
2. Pilot: 6×6, 3 storms
3. Captain: 7×7, 4 storms
4. Ace: 8×8, 5 storms

Recursive backtracking maze gen. Storms placed so maze is always solvable.
Move counter shown. Home button top-left.

## Game 5: Cargo Count (cargo-count.html)
Counting game. Brown cargo boxes (📦 emoji or styled divs) bounce in one by one.
Kid taps the correct number from choices below.

4 levels:
1. Tiny Cargo: 1-3 boxes, 3 choices
2. Small Load: 2-5 boxes, 4 choices
3. Big Haul: 3-7 boxes, 5 choices
4. Full Flight: 4-10 boxes, 5 choices

Wrong = shake + "Try again!". Streak counter 🔥, auto-advance after 3 correct.
Faint airplane silhouette in background. Home button top-left.

## Design Rules
- ALL games: daytime theme (blue sky, bright colors — NO dark/night themes)
- ALL games: touch-friendly, large tap targets
- ALL games: home button (🏠) top-left linking to index.html
- ALL games: Fredoka font
- ALL games: confetti celebration on level completion
- ALL games: Web Audio API for sound effects
- Plane images should be sized appropriately (max ~120px height in cards, ~80px in game pieces)
- Mobile-first responsive design
