# Order Tracking Screen

A mobile-first order tracking screen for an e-commerce app. Built with plain HTML, CSS and JavaScript. No build step and no dependencies.

## Run locally

```bash
git clone <your-repo-url>
cd order-tracking
# Option 1: open index.html directly in a browser
# Option 2: serve it
npx serve .        # or: python3 -m http.server 8080
```

## Deploy

- **Vercel / Netlify:** import the repo and deploy. No build command, publish directory `/`.
- **GitHub Pages:** Settings → Pages → Deploy from branch `main` / root.

## What it shows

Use the **Demo scenario** switcher at the top to see the same screen adapt to each state:

| Scenario | Behavior |
|---|---|
| **On time** | Normal flow, "Arriving today" with a courier contact action |
| **Delayed** | Amber alert, struck-through old ETA, revised ETA, delayed step highlighted, contact support and notify actions |
| **Not received** | Marked delivered, red flagged step, checklist of where to look, "I didn't receive it" report flow |
| **No tracking** | Friendly info state with an estimated date range and a "Notify me when tracking is ready" toggle, so no empty or broken area |

## Features

- Vertical delivery timeline (done, current, delayed, issue and pending states)
- Current status and estimated delivery at a glance
- Order and product summary with order details sheet
- Contact support sheet (chat, call, email) and report-issue flow with reasons
- Skeleton loading state on every scenario change
- Responsive from 320px to 430px, safe-area aware, centered on desktop
- Light and dark mode, accessible focus states, `aria-live`, dialog roles, Esc to close, reduced-motion support

## Design decisions

- **Status first.** A colored pill plus a plain-language headline answers "where is my order?" before any detail.
- **Color carries meaning, never alone.** Every state also has an icon and text.
- **Every problem state has a next step.** Delay has a notify option, a missed delivery has a report flow, missing tracking has a subscription.
- **Mock data only.** Scenarios live in the `S` object in `index.html`. Swap in an API response of the same shape to connect a backend.
