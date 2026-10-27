# Civ V Road Planner

Plan Civilization V road networks on a hex map. Place cities, mountains and water, then compare three networks: the fewest road tiles, the fastest travel, and a balance of the two.

## Use it

Open `index.html` in a browser. There is no build step and nothing to install.

- Pick a brush (City, Mountain, Water, Land) and click or drag on the map. Keys 1–4 switch brushes.
- Pick Move (key 5) to scroll the map without painting. On phones the map keeps tappable hexes and scrolls inside its frame.
- Painting a tile with the brush it already has turns it back into land.
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
