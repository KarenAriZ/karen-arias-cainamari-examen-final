# Copilot instructions

## Project structure and architecture

- The application is a self-contained static prototype in the root `index.html`. Its markup, design system, and behavior all live in that file; there is no build pipeline or server.
- The page is organized as a narrow, mobile-oriented dashboard: virtual card and balances, simulated recharge form, pending-activation notice, and recharge history.
- The inline script is an immediately invoked function in strict mode. It owns the application state, reads and writes `localStorage`, attaches event handlers, and renders the balance and history into the page.
- Persisted state uses the `mi-metropolitano-demo-v1` key. It contains a card number, available balance, and history records with an ID, amount, status (`active` or `pending`), and ISO timestamp. Defaults provide the initial sample card and transactions.
- A recharge is first staged for confirmation, then stored as pending without changing the available balance. Simulated activation changes pending entries to active and adds their amounts to the balance. These are demonstration-only operations; do not introduce real payment or transit-system integrations.

## Build, test, and lint

- There are no package manifests, build scripts, test runner, or lint configuration in this project; no automated test or single-test command is defined.
- Run the prototype by opening `index.html` directly in a browser (for example, `Start-Process .\index.html` in PowerShell).
- Validate changes with a browser smoke test: check the recharge form and validation, confirmation, pending-to-active flow, history filter, reload persistence, keyboard focus, and narrow/mobile layout. Keep any generated test data local and restore the prior `localStorage` state after testing.

## Codebase conventions

- Keep the app dependency-free and self-contained in `index.html`; use inline CSS, JavaScript, and SVG rather than introducing a framework or remote asset.
- User-facing copy is in Spanish. Format amounts in Peruvian soles (`S/`) and history dates with `Intl.DateTimeFormat("es-PE", ...)`.
- Use the existing CSS custom properties for colors and surfaces. Dark mode is driven by `prefers-color-scheme: dark`; reduced-motion preferences are handled in CSS. Maintain readable contrast in both themes.
- Keep controls keyboard-accessible with native buttons, inputs, and selects, visible `:focus-visible` styling, and labels or ARIA names. Mark decorative SVGs as hidden from assistive technology; convey transaction state in text as well as color/icon.
- Keep state transitions consistent across persistence and rendering: validate loaded local data, use `saveState()` for mutations, render after successful updates, and surface storage failures to the user. Preserve the `active` / `pending` status values because the balance, notice, filter, labels, and icons depend on them.
- Build dynamic history rows with DOM elements and `textContent`; SVG markup is selected only from the fixed inline templates for the two known statuses.
