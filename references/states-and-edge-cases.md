# States and edge cases

Most prototypes are built for the one case where the data is tidy and everything works. Check every piece of data and every action on the screen against the lists below.

## For every piece of data shown

| State | What the person must see | Typical component kind |
|---|---|---|
| Loading | That something is coming, in the shape it will have | skeleton for content, spinner for a short action |
| Empty, first use | What will be here, why it is useful, one action to start | empty state with a primary button |
| Empty, no results | That the search or filter found nothing, and a way to clear it | empty state with "clear filters" |
| Empty, cleared by the user | A light confirmation, easy way to add again | empty state, quiet |
| Failed to load | What failed in plain words and a retry | banner or inline error with a retry action |
| No permission | Why it is unavailable and who can grant access | banner or empty state |
| Partial | Which part loaded and which did not | inline error in the failed part only |
| One item | Singular wording and a layout that does not look broken | none, check texts |
| Very many items | Paging, search or filtering; the screen stays usable | table with paginator, search |
| Stale | That the data may be out of date, with a refresh | hint or banner |

Resolve "component kind" to the real Rule component through the `rule-prototypes` map.

## For every action

- **Before:** is it clear what will happen and to what? Is the button disabled with a visible reason when it cannot be used?
- **During:** does the control show it is working, and is a second click harmless? The button shows loading and cannot be fired twice.
- **Success:** is the result visible where the person is looking, and does the screen reflect it without reload?
- **Failure:** does the person keep their input, see what went wrong next to where it went wrong, and have a next step?
- **Irreversible:** is there a confirmation that names the exact thing and count affected ("Delete 3 campaigns"), or an undo?
- **Interrupted:** closing the modal, leaving the page or losing the connection halfway does not leave things half done without telling the person. Unsaved changes warn before leaving.
- **Repeated or concurrent:** the same thing changed in another tab or by a colleague does not get silently overwritten.

## Data that breaks layouts

Check with realistic worst cases, not nonsense strings.

- Long names, long emails without spaces, long translated labels (German and Swedish run 30 to 40 percent longer than English).
- One-letter names, missing optional fields, missing avatar.
- Zero, one, and very large counts; negative and decimal numbers where they can occur.
- Non-Latin text and emoji in any user-entered field.
- Dates in other time zones, past dates, far-future dates.
- Plurals: "1 subscribers" is a bug. Use the project's plural handling.
- Dates and numbers formatted by locale, not hardcoded.

Text must truncate with a way to see the full value, or wrap, by decision and not by accident.

## First run and feature discovery

- Reach the first useful result fast. Ask only for what is needed to get there; everything else later.
- Teach in place, at the moment it is needed: an empty state that explains and starts the task beats a tour.
- Tours and multi-step intros must be skippable and must not block work.
- A new feature is announced once, where it lives, and can be dismissed for good.

## Slow and failing network

- Anything that can take more than about a second shows progress.
- Anything that can take more than about ten seconds lets the person keep working or cancel.
- A failed request never looks like an empty list.
