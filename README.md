# Civ V Road Planner

Plan Civilization V road networks on a hex map. Place cities, mountains and water, then compare three networks: the fewest road tiles, the fastest travel, and a balance of the two.

## Use it

Open `index.html` in a browser. There is no build step and nothing to install.

- Pick a brush (City, Mountain, Water, Land, Road) and click or drag on the map. Keys 1–5 switch brushes.
- The Road brush forces a road onto a tile. Every plan includes forced roads, connects them, and counts them as road tiles.
- On touch screens, tap or drag sideways to paint; swiping up or down scrolls the page. When the map is wider than the screen, a Move brush appears for scrolling it sideways.
- Painting a tile with the brush it already has turns it back into land.
- Use the Shift arrows (or arrow keys) to move everything on the map one tile. Cities never fall off the edge.
- Pick a map size or enter a custom one, from 4 × 4 up to 50 × 50.
- Choose a road plan from the dropdown above the map. Balanced has a shortcut value you can step up or down.
- Pick a cell in the travel table to trace that route on the map.
- Your map is saved in your browser's local storage.

## The three plans

| Plan | What it does |
|---|---|
| Fewest roads | Minimum Steiner tree connecting every city. Exact (Dreyfus–Wagner) for up to 12 cities, approximate above that. Among equally small networks, road segments are re-laid to shorten trips. |
| Fastest travel | Every pair of cities gets its shortest land route, overlapping where possible, then unneeded tiles are pruned. |
| Balanced | Starts from Fewest roads and greedily adds shortcuts. A shortcut is built only if it saves enough total travel per new tile (set by the slider) and cuts at least one trip by 2 or more tiles. |

## Rules

- Roads can use any land tile. Mountains and water block them.
- City tiles count as road at no cost.
- Travel is measured in tiles moved along roads. Total travel sums every city pair.
- Upkeep assumes 1 gold per road tile per turn.
