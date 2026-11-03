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
- **Menu**: every item, filterable by food, restaurant, park (Disneyland, California Adventure, Grand Californian or Downtown Disney) and area (land, such as Galaxy's Edge or Cars Land, using Disney's own land names). Tapping Food or Restaurant opens a scrolling list that narrows with every letter you type and only shows what fits your other filters; tap a row to pick it. Matches outside your Park or Area filter are listed after a divider instead of hidden, and picking one switches the filter to all parks. Words can come in any order, so "pepper pasta" finds Pepper Particle Pasta. Sort by kcal per gram of protein, protein, calories, area, restaurant or name. Each dish appears once, with its side; to leave the side off, tick the dish and untick the side under **Adjust ingredients**. Tick what you ate. Tap an item's name to see its parts and their calories.
- **Day log**: the selected day's items, quantities and the MacroFactor Quick Add list. Quantity pickers offer ×0.25 to ×4, or **Custom…** for any multiplier from 0.01 to 20 (for example 0.33 or 2.5); type it and press Enter or tap elsewhere. Tap **Adjust ingredients** under a logged item to untick any part you skipped (a side, sauce, topping, bun) or give one part its own multiplier, such as sauce ×2 or fries ×0.5; the item's numbers update and the change shows in brackets, for example "[no fries; dipping sauce x2]". A side made of several pieces, such as toast with butter or a house salad with its dressing, is one row with its own tick and multiplier, and its pieces are listed under it so you can still drop just the butter. Cooking oil, cooking butter and breading can't be left off, so they are counted and marked "included", with no tick box; a side's cooking oil goes with the side. The same controls appear when you open a ticked item in Menu. Starbucks and grocery-label items can't be adjusted because their numbers come from a published panel, not parts.
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
Disney does not publish nutrition data for park, hotel or its own Downtown Disney food. Items tagged **Published** use the operator's own figures: Starbucks (starbucks.com item pages), Wetzel's Pretzels (nutrition guide v.061325) and Earl of Sandwich (the July 7, 2022 guide its website links; three sausage breakfast carb values in that PDF are impossible for their calories and are not on the Downtown Disney menu). The Mickey bar and Toll House cookie sandwich use grocery-pack labels. Everything else is an estimate built from USDA FoodData Central records and assumed portions, with frying oil and cooking fat counted; treat estimates as plus or minus 25 percent. Menus match Disney's official online menus as read on November 3, 2026: park quick-service restaurants, snack spots and Galaxy's Edge; every Grand Californian venue (GCH Craftsman Grill and Bar, Hearthstone Lounge, Napa Rose, In-Room Dining and Storytellers Cafe buffet servings); and Downtown Disney's quick-service and snack spots (table-service Downtown Disney restaurants are being added next). Park table-service restaurants other than the Cafe Orleans Monte Cristo, alcohol, kids' meals and Starbucks drinks are not included. When Disney drops a dish it leaves the menu here too; anything you already logged keeps its numbers and stays in Recent. The separate "(no fries)"-style versions were removed on November 2, 2026; days that already use one keep its numbers.

## Files
- `index.html`: the app, with the menu data built in
- `index.template.html`: the same page with a `__DATA__` placeholder, for rebuilding when the menu data changes
- `manifest.webmanifest`, `sw.js`, `icon-*.png`, `apple-touch-icon.png`: what Chrome needs to install the app and run it offline
- `.nojekyll`: tells GitHub Pages to serve the files as they are

## Updating
Edit and push to `main`; GitHub Pages republishes within a minute or two. When `index.html` changes, also change `VERSION` in `sw.js` so installed copies pick up the update. The installed app loads the new version the next time it opens online.

## Removing it
Long-press the app icon and choose Uninstall (or remove it under Chrome's site settings). Uninstalling can delete the log, so back up first.
