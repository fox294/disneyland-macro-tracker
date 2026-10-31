# Disneyland Macro Tracker

A phone web app for logging what you eat at Disneyland Resort (Disneyland Park, Disney California Adventure and Disney's Grand Californian Hotel & Spa). Check off menu items for each day, set quantities, and see the day's calories, protein, fat, carbs and calories per gram of protein. Filter the menu by food and by restaurant.

Live app: https://fox294.github.io/disneyland-macro-tracker/

## Requirements
- Android phone with Chrome (desktop Chrome and Edge also install it).
- Internet for the first visit. After that it works offline.

## Install on a phone
1. Open https://fox294.github.io/disneyland-macro-tracker/ in Chrome.
2. Tap **Install app** at the top of the page, or Chrome's three-dot menu, then **Install app** (older versions say **Add to Home screen**).
3. Open it once while online so it caches itself for offline use.

## Tabs
- **Menu**: every item, filterable by food, restaurant, park and area (land, such as Galaxy's Edge or Cars Land, using Disney's own land names). Sort by kcal per gram of protein, protein, calories, area, restaurant or name. Every dish that comes with a side also has a version without it, such as "(no fries)", "(no rice or beans)", "(no crackers)" or "(no bread bowl)"; the side is removed and nothing is substituted. Tick what you ate.
- **Day log**: the selected day's items, quantities and the MacroFactor Quick Add list.
- **Recent**: items you've logged before, newest first, one row per item (hand-added items included). Tick to add one to the selected day at quantity 1.
- **History**: one row per logged day with its totals. Tap a day to open it. Backup and restore live here.

## Moving entries into MacroFactor
MacroFactor has no import for food entries, so the Day log tab has an **Enter in MacroFactor** list. In MacroFactor tap + then **Quick Add**; in this app tap each value (calories, protein, fat, carbs) to copy it, paste it into the matching Quick Add field, then tick **Entered**. Changing an item's quantity clears its tick.

## Where your data lives
| Data | Where it is | In this repo? |
|---|---|---|
| Your daily log | The phone's browser storage for this web address | No. It never leaves the phone. |
| Backups | JSON files you save with **History > Back up log** (to Downloads) | No |
| Menu items and estimates | Built into `index.html` | Yes |

The log belongs to this exact web address. If the app moves to a different address, back up first and use **Restore from backup** there. Clearing Chrome's site data for this address deletes the log.

## About the numbers
Disney does not publish nutrition data for park or hotel food. All but four items are estimates built from USDA FoodData Central records and assumed portions, with frying oil and cooking fat counted; treat them as plus or minus 25 percent. The Starbucks egg bites use Starbucks' published panels; the Mickey bar and Toll House cookie sandwich use grocery-pack labels. Menus match Disney's official online menus as read on October 31, 2026 (park quick-service restaurants, snack spots and Galaxy's Edge, plus every Grand Californian venue: GCH Craftsman Grill and Bar, Hearthstone Lounge, Napa Rose, In-Room Dining and Storytellers Cafe buffet servings; park table-service restaurants other than the Cafe Orleans Monte Cristo, alcohol, kids' meals and Starbucks drinks are not included). When Disney drops a dish it leaves the menu here too; anything you already logged keeps its numbers and stays in Recent.

## Files
- `index.html`: the app, with the menu data built in
- `index.template.html`: the same page with a `__DATA__` placeholder, for rebuilding when the menu data changes
- `manifest.webmanifest`, `sw.js`, `icon-*.png`, `apple-touch-icon.png`: what Chrome needs to install the app and run it offline
- `.nojekyll`: tells GitHub Pages to serve the files as they are

## Updating
Edit and push to `main`; GitHub Pages republishes within a minute or two. When `index.html` changes, also change `VERSION` in `sw.js` so installed copies pick up the update. The installed app loads the new version the next time it opens online.

## Removing it
Long-press the app icon and choose Uninstall (or remove it under Chrome's site settings). Uninstalling can delete the log, so back up first.
