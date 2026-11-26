# loc-upstream-dummy

Fake game VCS for audio-manager branching + two-pull tests.

## Layout

- `loc/strings.json` — string dump (`{"strings":[...]}`) for `POST /api/loc/games/{id}/dump`
- `loc/vo_ja.json` — JA VO manifest (`{"lines":[...]}`) for `POST /api/loc/games/{id}/vo-manifest?locale=ja`

## Branches

| Branch | Intent |
|--------|--------|
| `main` | Shared baseline |
| `release/r1` | Patch one UI string + dialogue tweak |
| `release/r2` | R1 base + new item + VO line |
| `release/hotfix` | Typo fix only on `UI_OK` |
| `feature/event-summer` | Seasonal strings added |

Minor text diffs are intentional so loc branch isolation / merge experiments are visible.
