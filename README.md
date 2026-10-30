# Disneyland Macro Tracker

A phone web app for logging what you eat at Disneyland Resort (Disneyland Park and Disney California Adventure). Check off menu items for each day, set quantities, and see the day's calories, protein, fat, carbs and calories per gram of protein. Filter the menu by food and by restaurant.

Live app: https://fox294.github.io/disneyland-macro-tracker/

## Requirements
- Android phone with Chrome (desktop Chrome and Edge also install it).
- Internet for the first visit. After that it works offline.

## Install on a phone
1. Open https://fox294.github.io/disneyland-macro-tracker/ in Chrome.
2. Tap **Install app** at the top of the page, or Chrome's three-dot menu, then **Install app** (older versions say **Add to Home screen**).
3. Open it once while online so it caches itself for offline use.

## Where your data lives
| Data | Where it is | In this repo? |
|---|---|---|
| Your daily log | The phone's browser storage for this web address | No. It never leaves the phone. |
| Backups | JSON files you save with **History > Back up log** (to Downloads) | No |
| Menu items and estimates | Built into `index.html` | Yes |

The log belongs to this exact web address. If the app moves to a different address, back up first and use **Restore from backup** there. Clearing Chrome's site data for this address deletes the log.

## About the numbers
Disney does not publish nutrition data for park food. All but four items are estimates built from USDA FoodData Central records and assumed portions, with frying oil and cooking fat counted; treat them as plus or minus 25 percent. The Starbucks egg bites use Starbucks' published panels; the Mickey bar and Toll House cookie sandwich use grocery-pack labels. Menus as of October 2026.

## Files
- `index.html`: the app, with the menu data built in
- `index.template.html`: the same page with a `__DATA__` placeholder, for rebuilding when the menu data changes
- `manifest.webmanifest`, `sw.js`, `icon-*.png`, `apple-touch-icon.png`: what Chrome needs to install the app and run it offline
- `.nojekyll`: tells GitHub Pages to serve the files as they are

## Updating
Edit and push to `main`; GitHub Pages republishes within a minute or two. When `index.html` changes, also change `VERSION` in `sw.js` so installed copies pick up the update. The installed app loads the new version the next time it opens online.

## Removing it
Long-press the app icon and choose Uninstall (or remove it under Chrome's site settings). Uninstalling can delete the log, so back up first.
