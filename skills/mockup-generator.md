https://www.figma.com/design/E0KNkqNGoDtoJ0hatLjZKi/Domain?node-id=17321-35855&p=f&t=4P5IyicN0dPYEIoF-0

# Mockups: edit a template while sending, then save and send

> Base: Figma *Domain › Template messages*, section 3 "Notify an applicant" (frames 3.3, 3.4, 3.7, 3.8) and 2.10 "Edit template".
> Low-fi mockups that reuse the existing centred modal: title, "Use template" selector, Subject, Message, one-way caption, Cancel / Send.
> Clickable version (options A–D): [mockup-template-save-send.html](mockup-template-save-send.html)

## Scenario

Clara White (recruiter) opens **Contact Hugo Müller**, picks the template **"Rejection message"**, and adapts the text. She wants to send the message **and** keep her changes for next time, without leaving the modal.

---

## Step 1: template applied (all options)

Change compared with Figma: the selector shows the applied template's name. Today it always reads "Use template".

```
┌──────────────────────────────────────────────────────────────────────────────┐
│  Contact Hugo Müller                                                         │
│                                                                              │
│  [ Rejection message  ▾ ]                                                    │
│                                                                              │
│  Subject                                                                     │
│  ┌────────────────────────────────────────────────────────────────────────┐  │
│  │ Your application at Buch AG                                            │  │
│  └────────────────────────────────────────────────────────────────────────┘  │
│  Message                                                                     │
│  ┌────────────────────────────────────────────────────────────────────────┐  │
│  │ [+ Variable] [Link]                                                    │  │
│  │ Hello (Recipient first name) (Recipient last name),                    │  │
│  │ Thank you for your application for the Buchhandlung (m/f/d), 80-100%.  │  │
│  │ After careful consideration, we have decided to proceed with other …   │  │
│  │ Clara White                                                            │  │
│  └────────────────────────────────────────────────────────────────────────┘  │
│                                                                              │
│  ⓘ This is a one-way message. Add your email …          [ Cancel ] [ Send ➤ ]│
└──────────────────────────────────────────────────────────────────────────────┘
```

## Step 2: the recruiter edits the text (all options)

As soon as the subject or message differs from the saved template:
- The selector shows an **"Edited"** tag.
- A **"Reset to template"** link appears.
- The save options below appear.

```
│  [ Rejection message · Edited  ▾ ]                      ↺ Reset to template  │
│  …                                                                           │
│  │ After careful consideration, we have decided to proceed with other …   │  │
│  │ We will keep your profile in our talent pool for 6 months.  ← new text │  │
```

---

## Step 3: save options

### Option A: "Also update the template" checkbox (name not editable)

```
│  ⓘ This is a one-way message. Add your email …                               │
│ ──────────────────────────────────────────────────────────────────────────── │
│  ☑ Also update the template "Rejection message"                              │
│                                                   [ Cancel ] [ Save & send ➤ ]│
```

- Unchecked by default, so a plain Send leaves the template untouched.
- When checked, the primary button becomes **"Save & send"**.
- Toast: ✓ *Message sent to Hugo Müller. Template "Rejection message" updated.*
- **+** Simplest: one checkbox and one click.
- **−** Can't keep the original and a variant side by side; no renaming.

### Option B: update, or save as a new template (name editable only for the new one) ★ recommended

```
│  ☑ Save these changes as a template                                          │
│      (•) Update "Rejection message"                                          │
│      ( ) Save as a new template                                              │
│                                                   [ Cancel ] [ Save & send ➤ ]│
```

When the recruiter selects "Save as a new template":

```
│  ☑ Save these changes as a template                                          │
│      ( ) Update "Rejection message"                                          │
│      (•) Save as a new template                                              │
│          Template name *                                                     │
│          ┌────────────────────────────────────┐                              │
│          │ Rejection message (copy)           │                              │
│          └────────────────────────────────────┘                              │
│          ⚠ A template with this name already exists.   ← only if duplicate   │
│                                                   [ Cancel ] [ Save & send ➤ ]│
```

- The name field appears **only** for a new template. It is required, prefilled with "(copy)", and must be unique.
- The existing template keeps its name. Renaming stays in *Manage templates › Edit* (2.10).
- Toasts:
  - Update: ✓ *Message sent to Hugo Müller. Template "Rejection message" updated.*
  - New: ✓ *Message sent to Hugo Müller. Template "Rejection – talent pool" created.*
- **+** Covers both intents: "fix my template" and "variant for this case". Low risk of overwriting by mistake.
- **−** One more decision than Option A.

### Option C: full control, the existing template can be renamed too

```
│  ☑ Save these changes as a template                                          │
│      (•) Update existing template        ( ) Save as a new template          │
│      Template name *                                                         │
│      ┌────────────────────────────────────┐                                  │
│      │ Rejection message ✎                │  ← prefilled, editable           │
│      └────────────────────────────────────┘                                  │
│                                                   [ Cancel ] [ Save & send ➤ ]│
```

- "Update" with a changed name **renames** the existing template, and the change shows in *Manage templates*.
- **+** No detour to Manage templates.
- **−** A management action hidden in the send flow; risk of accidental renames, especially if templates are shared; more validation states to design and test.

### Option D: split button (compact, reuses frame 3.8)

```
│                                          [ Cancel ] [ Send ➤ │ ▾ ]           │
│                                                     ┌────────────────────────┐│
│                                                     │ Send only              ││
│                                                     │ Update template & send ││
│                                                     │ Save as new & send…    ││
│                                                     └────────────────────────┘│
```

"Save as new & send…" opens the existing **"Create new template"** modal (3.8), prefilled with the edited subject and message:

```
┌──────────────────────────────────────────────────────────────────────────────┐
│  Create new template                                                         │
│  Template name *     [ Rejection message (copy)                ]             │
│  Subject             [ Your application at Buch AG             ]             │
│  Message             [ …edited text…                           ]             │
│                                       [ Back to message ] [ Save & send ➤ ]  │
└──────────────────────────────────────────────────────────────────────────────┘
```

- **+** Smallest footprint and reuses an existing screen.
- **−** Hidden behind a chevron, so harder to discover. Is a split button available in the design system? (GAP)

---

## Comparison

| | A: Checkbox | B: Update or new ★ | C: Full control | D: Split button |
|---|---|---|---|---|
| Name editable | No | New template only | Always (incl. rename) | New template only |
| Keep original + variant | No | Yes | Yes | Yes |
| Clicks to save & send | 2 | 2–3 | 2–3 | 2–4 |
| Discoverability | High | High | High | Low |
| Risk of unwanted overwrite | Medium | Low | High | Low |
| Design / dev effort | Low | Medium | High | Medium |

**Recommendation: Option B.** It covers both real intents, keeps renaming in *Manage templates* where it belongs, and makes accidental overwrites unlikely.

---

## Edge cases to cover

| Case | Behaviour |
|---|---|
| Edit contains the applicant's own data (e.g. "Hugo" typed as text) | Before saving, warn: *"Your changes include 'Hugo'. Use the variable (Recipient first name) so the template works for every applicant."* Options: **Replace with variable** / **Save anyway**. |
| Templates shared with colleagues (GAP) | Under "Update", add the caption *"Changes apply to everyone in your company using this template."* |
| Switching template after editing | Confirm: *"Replace your changes with 'Pending review'?"* [Keep editing] [Replace]. |
| Reset to template | Restores the saved text and removes the "Edited" tag. No confirmation needed if undo is available. |
| Message sent but template save failed | Never block the send. Toast: *"Message sent. We couldn't update the template."* [Retry]. |
| Cancel with edits | The template is not changed. |
| Bulk send (4.2, "Contact 9 applicants") | Same save section; button reads **"Save & send to 9"**. |
| Decline flow (5.2 "Decline – edit content") | Same pattern. |
| Mobile | The save section stacks above full-width buttons. |

## Open questions

1. Are templates personal or shared across the company? This drives the warning and the permissions.
2. Who can update a shared template: any recruiter, or admins only?
3. Is there a maximum number of templates? "Manage message templates (40)" suggests a large list, so "Save as new" could clutter it.
4. Tracking: which events do we need (template edited, updated, saved as new, reset)?

## Figma inconsistencies spotted (for the designer)

- The selector always reads "Use template", even after a template is applied.
- The link tool and the Send icon are missing in 3.7.
- The template list differs between 3.4 and 3.6, and 3.4 lists "Rejection message" twice.
- The toast in 3.6 says "My awesome template", but the created template is "Document missing".
- 2.10: the template named "Acceptance message" contains a rejection text, and its variable chips are labelled "First name" instead of "Recipient first name".