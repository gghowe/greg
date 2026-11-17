# Handoff — Greg's website demo

Last updated: November 16, 2026

## What this project is

Greg is starting a B2B 3D design and printing service and wants a website ready for **January 1, 2027**. Garrett is building it for him. The site is a service site, not a store: its main feature is a calculator that estimates what a printed part will cost, plus general information about the service. Greg wants it basic at first and able to grow.

Greg's own words and the full scope are in [greg-website-requirements.md](greg-website-requirements.md). Read that first.

## Where things stand

A clickable demo exists and Garrett has reviewed and approved it. It has not been shown to Greg yet, and it is not hosted anywhere yet. The folder is not a git repository.

| File | What it is |
|---|---|
| [greg-website-requirements.md](greg-website-requirements.md) | Greg's messages copied verbatim from the text thread, plus the goal, what is out of scope, and what is still undecided |
| [index.html](index.html) | The demo site. One self-contained file: HTML, CSS, and JavaScript, no build step. The only outside dependency is Google Fonts |

## What the demo contains

- **Sections:** navigation, hero, three services (design, prototyping, production), the cost estimator, a four-step process, a contact block, and a footer.
- **Deliberately left out:** any shop, product listings, portfolio, or eBay items. Greg ruled these out.
- **Four themes in one file**, switched with the pill at the bottom of the page:
  - Graphite: dark charcoal, brass accent
  - Paper: warm off-white, serif headlines, terracotta accent
  - Blueprint: deep navy with a faint grid, monospace labels
  - Studio: white, deep green accent, rounded cards
- A theme can be linked directly with `index.html?theme=paper` (or `graphite`, `blueprint`, `studio`). The last theme clicked is remembered in the browser.

## How the estimator works

The visitor enters material, overall size in millimeters, strength (infill), quantity, finish, design work, and turnaround. The page shows a price range, a per-part price, and a line-by-line breakdown. The "Request a firm quote" button opens an email with those choices filled in.

The math, in order:

1. Estimate the part's weight from its bounding box, an assumed 30% fill of that box, the infill setting, and the material's density.
2. Material cost is weight times a per-gram rate. Machine cost is print hours (weight divided by 12 grams per hour) times an hourly rate.
3. Finish adds a percentage. A volume discount applies at 10, 50, and 100 parts. Rush adds a percentage.
4. A flat setup fee and a flat design fee are added last.
5. The range shown is the total plus or minus 15%.

All of these numbers live in one `RATES` object near the bottom of [index.html](index.html).

## Placeholders that must be replaced before this is real

- **Every rate in the estimator.** They were invented for the demo. Greg has not supplied any pricing.
- **The business name "Layerworks."** It was made up, and nobody has checked whether a real company uses it. Greg has not said what his business is called.
- **The email address** `hello@example.com`. It appears in the contact block and in the estimator's quote button.
- **The marketing copy.** Lines such as "no minimum order" and "design included" were written for the demo. Greg has not confirmed any of them.

## Decisions still open

- **Which theme.** Garrett has not picked one, and Greg has not seen them.
- **Greg's real pricing**, and whether the estimator's inputs match how he actually prices jobs.
- **The rest of Greg's feature list.** He said he has "some things I want on it" and has not named them.
- **What the home page should do.** Garrett asked Greg; no answer yet.
- **Business name and domain.** Neither is chosen.
- **Price for the work.** Greg says he will pay; no number is agreed.

## Next steps

1. Host the demo on GitHub Pages so Greg can open it. The file is already named `index.html`, so it will be served from the repository root once Pages is turned on.
2. Send Greg the link and have him pick a theme.
3. Once a theme is chosen, remove the other three theme blocks and the switcher. Both the switcher's HTML and its script are marked "preview only" in comments.
4. Get the real business name, email, and pricing from Greg and replace the placeholders.
5. Collect the rest of Greg's feature list and decide what goes in the first version.

## Working notes

- Garrett runs all state-changing git commands himself. Give him the command; do not run it.
- The text-message screenshots this work started from were intentionally not saved. Do not add them to the project.
