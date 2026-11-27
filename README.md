# loc-upstream-dummy

Fake game VCS for the audio-manager pull, process, deliver loop.

## Layout

Pull reads two paths on each ref:

- `loc/strings.json` — string dump. Each row's `filename` is the source file. Ordinals restart inside that file, in array order.
- `loc/vo_ja.json` — JA VO manifest. Line order is the record order.

Push writes target text back into `loc/strings.json` by `string_id` and leaves the array order in place.

## Source files

| File | Branches | What differs |
|------|----------|----------------|
| `loc/ui.json` | all | `UI_OK` is OK / Okay / Ok. `UI_CANCEL` is Cancel, except summer `Close`. |
| `loc/items.json` | all | Hotfix drops a period. R2 renames the mana potion and adds Sunstone. |
| `loc/quest.json` | all | Intro VO. R1 and R2 tweak the ridge line. R2 adds a fourth line. |
| `loc/menu.json` | all | Same three labels on every branch. |
| `loc/combat.json` | all | Two VO lines, same source on every branch. |
| `loc/shop.json` | `release/r2` | One greeting, this branch only. |
| `loc/event.json` | `feature/event-summer` | Banner and vendor line, plus that line on the VO manifest. |

## Branches

| Branch | Intent |
|--------|--------|
| `main` | Shared baseline |
| `release/r1` | Softer `UI_OK`, ridge line tweak |
| `release/r2` | R1 base + Sunstone, fourth intro line, shop file |
| `release/hotfix` | `UI_OK` casing and a trimmed item description |
| `feature/event-summer` | Event file. `UI_CANCEL` source is `Close`, so it is not the Cancel unit. |
