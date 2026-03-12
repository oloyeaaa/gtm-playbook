# SmartLead Campaign Pre-Publish Checklist

Run through this every time before publishing a campaign. Takes 5 minutes, prevents disasters.

## Variables & Personalisation
- [ ] Every `{{variable}}` has matching opening and closing braces
- [ ] Preview 3-5 leads to confirm variables resolve correctly (no blanks, no raw tags)
- [ ] Fallback/default values set for any variable that might be empty
- [ ] No accidental spaces inside braces (e.g. `{{ firstName }}` vs `{{firstName}}`)

## A/B Testing (Subject Lines)
- [ ] At least 2 subject line variants per segment (SmartLead supports A/B natively)
- [ ] Each variant tests ONE variable — don't change everything at once
- [ ] Split is even (50/50 for 2 variants, 33/33/33 for 3)
- [ ] Variants differ meaningfully — test angles, not just word swaps:
  - Pain point vs curiosity vs direct benefit
  - Question vs statement
  - With personalisation vs without
  - Short (3-5 words) vs medium (8-12 words)
- [ ] Winner metric: **reply rate** (open tracking off — adds HTML pixel, triggers spam filters)
- [ ] Plan to check results after 50+ sends per variant before calling a winner
- [ ] Winning subject line gets rolled into future campaigns as the new baseline

## Copy & Links
- [ ] Subject line(s) render correctly with variables
- [ ] All links working — click each one manually
- [ ] No tracking links pointing to localhost or broken UTMs
- [ ] Unsubscribe/opt-out link present and functional
- [ ] Spintax (if used) previewed for all variations — no orphaned `{` or `|`

## Sequence Logic
- [ ] Correct number of steps in the sequence
- [ ] Wait days between steps make sense (not too aggressive)
- [ ] Reply detection is on — stops sequence when lead replies
- [ ] "Send as new thread" vs "reply to previous" set intentionally per step

## Sending Settings
- [ ] Correct mailbox(es) assigned (check which of the 9 you're using)
- [ ] Daily send limit per mailbox is reasonable (ramp if new)
- [ ] Sending window matches recipient timezone / business hours
- [ ] Warmup still running on assigned mailboxes

## Lead List
- [ ] Correct list attached — spot-check 5 leads
- [ ] No duplicates across active campaigns
- [ ] Leads not already in another live sequence (overlap check)
- [ ] Email addresses validated (no obvious typos or catch-alls you want to skip)

## Final Sanity Check
- [ ] Send a test email to yourself from each step
- [ ] Read it on mobile — formatting holds up?
- [ ] Ask: "If I received this cold, would I read past line 1?"
