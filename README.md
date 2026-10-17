# PickEdge-MLBB-Hero-Counter
<p>
  PickEdge - MLBB Hero Counter is a counter-pick tool for a game called Mobile Legends: Bang Bang.
  The goal is to allow players to utilise this during the ban-pick phase which is time sensitive, deciding which hero counters the enemy's picks is half strategy, half guesswork. PickEdge will elimina[...]
</p>

<p>
  The objective is to enable new players that are currently learning the game to be able to have fun and learn at the same time without stress.
</p>

<p>
  PickEdge can be utilised on a variety of mobile devices and website!
</p>

<p>
  Check it out: <a href="https://pickedge-mlbbherocounter.netlify.app/">PickEdge - MLBB Hero Counter</a>
</p>

## What's new in this version

- **Responsive layout** — the app is a single scrolling column on phones,
  and automatically switches to a fixed sidebar (recommendations) + fluid
  main area (search/picker) from tablet-landscape widths up (≥900px). The
  hero grid and suggestion list use CSS auto-fill grids, so column counts
  scale continuously with screen width rather than jumping at fixed
  breakpoints — same HTML and CSS handles phone, tablet, and laptop.
- **Item attribution** — "Items to consider" now shows which enemy hero(es)
  recommend each item (e.g. "Blade Armour — vs Miya"), instead of an
  unlabeled list.
- **Lane-based recommendations** — the team comp now gives one pick per
  LANE (EXP, Jungle, Mid, Gold, Roam) plus two alternates, and the ranked
  list has a lane filter. A hero is only ever suggested for a lane they
  actually play (e.g. Alice is an EXP/Jungle hero, so she is never
  suggested for Mid). Tapping a team-comp row jumps the list to that lane.
  See "How recommendations are scored" below.
- **Role legend** — a small always-visible key maps each role to its color,
  since the avatar background colors are otherwise unexplained.
- **New hero icon set** — replaced the earlier auto-cropped splash art with
  the official square hero icons you provided, which are much more
  consistently framed.

## How recommendations are scored

For each lane, heroes are ranked in this order (see `engine.js`):

1. **Lane** — only heroes who play that lane are considered. Hero class
   (Mage, Tank, ...) is not used as a position.
2. **Counters** — direct counter relationships from the hero list. A counter
   counts in full when the two heroes share a lane (a true lane opponent) and
   at 60% otherwise (it still helps in team fights).
3. **Hero attributes** — each hero's "strong against" trait and specialties
   are matched against the enemy picks (squishy, mobile, tanky, melee,
   immobile, no-CC). Capped at 2 points so it refines the ranking but never
   outweighs a real counter.
4. **Owned heroes** — +1 for heroes you starred.

Ties go to the hero whose primary lane is the one being filled. When there is
no counter data and no attribute match, the row says "no clear counter —
flexible pick" instead of pretending to be a strong recommendation.

## Modes, themes and saved settings

- **Quick mode** - tap the enemy heroes, get counters, a lane plan and items.
- **Ban-Pick mode** - walks the whole draft: bans alternate (Epic 3, Legend 4, Mythic and higher 5 per side), then picks go 1-2-2-2-2-1. Choose your rank and side (Blue picks first). Tap a hero to record each ban/pick (yours or the enemy's); Undo steps back. On your turn, suggestions can be locked in with one tap.
  - Ban suggestions: heroes that counter your starred heroes, then heroes that counter the most others (bans happen before picks, so star your mains).
  - Pick suggestions: same lane-first engine, limited to lanes your team still needs, hiding banned/taken heroes; with no enemy picks yet it shows hard-to-counter heroes.
- **Theme** - dark by default, light via the header button.
- Rank, side, mode, theme and starred heroes are remembered on the device.
- On phones the page has a bottom Heroes / Results switch; the enemy strip (Quick) or step bar (Ban-Pick) stays visible while scrolling.


## Website View
[![PickEdge Website View](Images/website.png)](https://pickedge-mlbbherocounter.netlify.app/)

## Mobile View
[![PickEdge Phone View](Images/mobile.png)](https://pickedge-mlbbherocounter.netlify.app/)
