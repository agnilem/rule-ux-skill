# Forms and access

Stack-neutral rules. In Rule they are mostly satisfied by using the existing form components correctly; a finding here usually means a component was bypassed or misconfigured.

## Forms

- Every control has a visible label. A placeholder is an example, never the label.
- The label is clickable and focuses the control. Checkbox and radio labels are part of the hit target.
- The control matches the data: a date picker for dates, a select for a fixed list, a toggle for on and off, a segmented control for two to four views. Free text only when the value is truly free.
- Correct input type and autocomplete, so the right keyboard and browser help appear.
- Never block paste.
- Required and optional are marked the same way across the form. Prefer marking the rarer of the two.
- Ask for as little as possible. Each field must be needed for this step.
- Group related fields; order follows how people think about the task, not the database.
- Defaults are the choice most people need, and never a choice that costs or risks something.
- Validate when the person leaves a field or submits, not on every keystroke while they are still typing.
- Errors sit next to the field, say what is wrong and how to fix it, and stay until fixed. On submit, focus goes to the first error.
- The submit button stays enabled until the request starts, then shows loading. A disabled submit with no explanation is a finding.
- Input survives an error. Nothing the person typed is lost on a failed submit.
- Leaving with unsaved changes warns first.
- The submit label says what will happen: "Schedule campaign", not "Continue" or "OK".

## Keyboard

- Everything that can be clicked can be reached with Tab and activated with Enter or Space.
- Focus order follows reading order.
- Focus is always visible. Never remove the focus outline without a replacement.
- Opening a modal moves focus into it; Tab stays inside; Escape closes it; focus returns to what opened it.
- Menus and lists support arrow keys; Enter selects; Escape closes.
- Sticky headers and footers do not cover the focused element.

## Screen readers and semantics

- Buttons are buttons and links are links. A clickable `div` is a finding.
- Icon-only buttons have an accessible name and a tooltip.
- Decorative icons are hidden from assistive tech; meaningful images have alt text.
- Messages that appear without a page change (saved, error, validation) are announced.
- Headings are in order and describe the section.

## Perception

- Meaning is never carried by color alone: status has a label or icon as well.
- Text and controls keep enough contrast to be read. Report it only as "people cannot read this", and propose the existing token or variant that fixes it, never a new color.
- Targets are large enough to hit and not crowded against a destructive neighbor.
- Nothing essential is available only on hover.

## Navigation and state

- State that people would want to share or return to (tab, filter, page, open item) is in the URL.
- Navigation uses real links so open-in-new-tab works.
- Destructive actions need a confirmation or an undo window, never immediate.
- The back button and browser back do what the person expects.

## Motion

- Respect the reduced-motion setting.
- Animation never delays an action the person repeats many times a day.
