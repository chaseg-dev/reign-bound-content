# Reign Bound content

Text the Reign Bound app reads from the web, so it can change without a new app build.

## What's New screens: `whats-new.json`

The app checks this file when it opens. Each entry in `screens` is one What's New screen. A person sees each screen once.

**To edit:** open `whats-new.json` on github.com, click the pencil icon, make your change, and click **Commit changes**. The app picks it up within a few minutes.

### Fields for each screen

| Field | Required | What it does |
|---|---|---|
| `id` | yes | A unique name, like `holiday-hours-2026`. Never reuse one. Changing it makes the screen show again to everyone. |
| `badge` | no | The small teal label at the top, like "What's new in 1.1". |
| `title` | yes | The big headline. |
| `items` | yes | The rows. Each row has `symbol`, `title`, `text`, and optional `color` and `note`. |
| `buttonTitle` | no | The main button. Defaults to "Continue". |
| `buttonLink`, `buttonLinkTitle` | no | A second link, like "Learn more" to a kcls.org page. |
| `minAppVersion` | no | Only show on this app version or newer. Use for update notes. |
| `maxAppVersion` | no | Only show up to this app version. |
| `startDate`, `endDate` | no | Only show between these times, written like `2026-11-01T08:00:00Z` (that is midnight Pacific). |
| `homeBranchCodes` | no | Only show to people whose home branch is in this list, like `["1490"]`. |
| `showToNewInstalls` | no | `true` to also show update notes to people who just installed the app. |
| `priority` | no | If several screens qualify at once, the highest number shows first. |

### Rows

- `symbol`: an Apple SF Symbol name, like `books.vertical`, `calendar`, `map`, `sparkles`. Browse names in Apple's free SF Symbols app.
- `color`: `teal`, `gold`, `purple`, `green`, `blue`, `red`, or a hex code like `#006B61`.
- `note`: an optional small gray line under the text.

### Before you save

- Check the commas and quote marks. One missing comma breaks the whole file. If the file can't be read, the app quietly falls back to the copy built into the app, so nothing breaks for patrons, but your change won't show. Pasting the file into jsonlint.com is a quick check.
- See `examples/campaign-example.json` for a dated campaign screen.
