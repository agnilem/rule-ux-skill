# Clarity and control

Ten checks based on Nielsen's usability heuristics, plus Steve Krug's rules for self-evident interfaces. For each, the question to ask and what a failure usually looks like in a product like Rule.

## The ten checks

1. **The system says what is going on.** After every action the person sees a result within about a second: saved, sending, failed. Failure: a button that does nothing visible; a long operation with no progress; a status that is only correct after reload.
2. **It speaks the person's language.** Words come from the user's work (campaign, subscriber, segment), not from the code or the database. Failure: internal names, ids, status codes, abbreviations only the team knows.
3. **There is always a way out.** Cancel, back, close and undo are present and do what they say. Leaving does not silently lose work. Failure: a modal with no Cancel; a wizard that cannot go back; Cancel that also discards saved data.
4. **Same thing, same way.** The same action has the same name, place and look everywhere. Standard patterns behave the standard way. Failure: "Remove" here and "Delete" there for the same thing; primary button on the left in one modal and on the right in another.
5. **Mistakes are prevented, not just reported.** Impossible options are disabled or absent, risky ones ask first, formats are constrained by the control. Failure: a date in the past can be picked and fails on submit; a destructive action fires on one click.
6. **Nothing has to be remembered.** What the person needs to decide is on the screen at the moment of deciding. Failure: a confirmation that does not name what will be affected; a value to copy from another page; an option whose effect is only explained in docs.
7. **Fast for people who do it daily.** Sensible defaults, keyboard support, bulk actions, remembering the last choice. Failure: the common case needs the most clicks; the default is the rare option.
8. **Only what is needed for this step.** Every extra option, text or control competes with the main action. Failure: three equal choices where one is right for most people; help text that restates the label.
9. **Errors explain and help.** An error says what happened, in plain words, next to where it happened, and what to do now. Failure: "Something went wrong"; an error in a snackbar that disappears before it can be read; a field marked red with no reason.
10. **Help is where the question arises.** A short hint next to the control beats a link to documentation. Failure: an unusual concept with no explanation; a hint that only appears on hover for a critical choice.

## Krug's rules

- **Do not make me think.** A person should know what a screen is and what to do without reading it carefully. Every question in their head ("is this a button?", "what does this option do to my campaign?") is a cost.
- **Clicks are fine if each one is obvious.** Three unambiguous steps beat one screen that requires a decision the person cannot make.
- **Cut the words.** People scan. Remove greetings, instructions that restate the UI, and anything that would be read by nobody.
- **The trunk test.** Dropped on this screen with no context, can the person answer: where am I, what is this, what can I do here, how do I go back?

## When checks pull against each other

- Preventing errors (5) vs speed for daily users (7): confirm only what cannot be undone. Prefer undo over a confirmation for everything else.
- Showing everything needed (6) vs only what is needed (8): show what the decision depends on; hide what it does not.
- Consistency (4) vs a better local solution: stay consistent unless the consistent pattern actively causes mistakes here, and then say so in the report.

## Patterns that trick people (always level 3 or 4)

Pre-checked options that cost the user something, a decline option that is harder to find than the accept option, wording that makes "no" sound shameful, a destructive default, hidden consequences revealed only after the action.
