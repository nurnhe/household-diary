# Household Diary

Plan and tick off household chores, and keep a shopping list of the supplies you're running low on. A sister app to [Skin Diary](https://github.com/nurnhe/skin-diary), built the same way but with its own look: linen and forest green, Fraunces and Manrope.

**Use it as a phone app:** open https://nurnhe.github.io/household-diary/ in Chrome on Android, then tap ⋮ → **Install app** (or **Add to Home screen**). It opens full screen with its own icon and works offline.

## Files

- `household-diary.html` is the page itself. The same file is published as a Claude artifact.
- `build.py` wraps it into `index.html` with the app manifest and offline support. Run `python3 build.py` after editing `household-diary.html`.
- `manifest.webmanifest`, `sw.js` and `icons/` make it installable and work offline. Bump the cache name in `sw.js` on every change.

## Features

- **Phone layout:** a bottom tab bar with Today, Week, Chores and Supplies.
- **Today:** the chores that are due, grouped by area (Kitchen, Bathroom, Laundry, Bedroom, Home), with a checkbox and a "Move to tomorrow" button. Overdue chores say how late they are. A short shopping list sits beside them.
- **Recurring schedules:** each chore repeats every N days, counted from the day you last ticked it. Unticking puts it back.
- **Week:** seven day cards. Past days show what you ticked, coming days show what's planned.
- **Chores:** add, edit (name, area, how often, next due date, icon) and remove chores.
- **Supplies:** tap "Running low" to put something on the shopping list, and tick it off when you've bought it. The app then reminds you a few days before it usually runs out. You can add one-off items to the list and copy or share it.
- **Starter list:** new diaries start empty, with a one-tap typical list of 17 chores and 17 supplies to trim.

## Data

When the page runs as a Claude artifact, data is saved in the artifact's database (`chores/*`, `supplies/*`, `shopping/*`) and syncs across devices. Anywhere else, including the installed app, it saves to the browser's `localStorage` on that device, and **Chores → Backup** saves or restores a backup file.

## Credits

Icons are inlined SVG from:

- [Phosphor Icons](https://github.com/phosphor-icons/core) (MIT License)
- [IconPark](https://github.com/bytedance/IconPark) (Apache License 2.0)
- [Tabler Icons](https://github.com/tabler/tabler-icons) (MIT License)

Fonts: Fraunces and Manrope, from Google Fonts (SIL Open Font License).
