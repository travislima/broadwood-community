# Broadwood/Charlo Residents Association — website

A single-page site for the BCRA (Broadwood & Charlo, Gqeberha / Port
Elizabeth). It encourages residents to join the association at R100 a month,
shows what the money funds, and acts as a quick reference for the community
WhatsApp groups and important phone numbers.

**No build step, no dependencies.** Plain HTML and CSS, designed to be
hosted free on GitHub Pages and edited by hand.

## Files

- `index.html` — the whole site (content + a config block at the top)
- `style.css` — styling
- `map.html` — the interactive Broadwood/Charlo map shown in the hero
  (Leaflet + OpenStreetMap, loaded in an iframe)
- `photos/` — real community photos (`big-park-tree.jpg` is used as the
  quote-band background; the others are kept for future use)
- `docs/membership-signup-options.md` — research on making sign-up easy
  from WhatsApp (e-mandates, Payfast, WhatsApp Business)

## How to publish (GitHub Pages)

1. On GitHub, go to **Settings → Pages**.
2. Under *Build and deployment*, set **Source** to `Deploy from a branch`,
   choose the `main` branch and the `/ (root)` folder, and save.
3. After a minute the site is live at `https://<username>.github.io/broadwood-community/`.

### Custom domain

The site's custom domain is **broadwoodcharlo.co.za** (the `CNAME` file in
this repo). DNS at the registrar: four A records on the apex pointing to
GitHub Pages (185.199.108.153 / .109. / .110. / .111.) and a `www` CNAME
record pointing to `travislima.github.io`. In **Settings → Pages**, the
custom domain should show as verified with **Enforce HTTPS** ticked. If
the domain ever lapses or moves, the site remains reachable at
`https://travislima.github.io/broadwood-community/`.

## How to update the site

Everything that changes over time lives in **one block at the top of
`index.html`**, marked `✏️ EDIT HERE`. Edit it directly on GitHub (open
`index.html`, click the pencil icon, commit) — no tools needed.

| Field | What it is |
| --- | --- |
| `paidMembers` | Households currently paying by debit order (drives every progress number on the page). |
| `memberGoal` | Total properties in the area (currently 800). |
| `cameraCount` | Monitored cameras up and running (currently 15). |
| `contactWhatsApp` | The membership contact's WhatsApp number, digits only with country code, e.g. `"27821234567"`. Once set, every Join button and both "Request to be added" buttons become WhatsApp deep links with pre-filled messages. Until then, Join buttons scroll to the membership section and a "details coming soon" note shows. |
| `debitOrderFormUrl` / `donationFormUrl` | The association's sign-up forms. Upload the PDFs to a `forms/` folder in this repo, then set e.g. `"forms/debit-order.pdf"` — "Get the … form" buttons appear in the membership section. |
| `debitOrderLink` | Self-service e-mandate link from the debit order provider (see `docs/membership-signup-options.md`). Shows a "Set up my debit order online" button when filled. |
| `cardPaymentLink` | Recurring card subscription link (e.g. Payfast R100/month). Shows a "Subscribe with my card" button when filled. |
| `emergencyGroupLink` / `securityGroupLink` / `socialGroupLink` | Optional WhatsApp invite links (Group info → Invite via link). If set, the group button links straight to the group; otherwise it falls back to a pre-filled "please add me" WhatsApp message (needs `contactWhatsApp`). |
| `annualDonors` | Households that supported the association with once-off/annual donations this past year. At `0` the donations panel shows a generic thank-you; set the real number (ask the committee) and the line becomes specific, e.g. "23 households supported us…". |
| `sapsStationNumber` | SAPS Walmer CSC — pre-filled with `041 581 0747` from the emergency group's rules. |
| `bank.*` | Account name, bank, account number and branch code for debit orders and once-off donations. |

Any field left as `""` shows a sensible placeholder ("To be confirmed" /
dashed "To be added" card / "ask an admin" fallback) instead of a broken
link — so the site is safe to publish before all the details are in.

### Launch checklist

- [x] `contactWhatsApp` — set to 083 200 5932 (bcramembership), from the
      association's official forms.
- [x] Banking details — Bidvest Bank business account, from the official
      membership & donation form.
- [x] Sign-up forms — both PDFs live in `forms/` and linked from the
      membership section.
- [ ] Verify the SAPS Walmer CSC number (041 581 0747) with a quick call —
      it comes from the emergency group's rules. (CityWide and municipality
      number cards were removed for launch; they can be re-added later as
      extra cards in the Important numbers section.)
- [ ] Confirm the milestone labels (100 / 200 / 400 households) and the
      "How do I know the money is well spent?" FAQ wording with the
      committee — the FAQ has a "to be confirmed" note to remove.
- [ ] Ask the committee for a Netcash eMandate link (they use Netcash
      DebiCheck) and set `debitOrderLink` — residents could then sign up
      fully online without printing the form.
- [ ] Update `paidMembers` whenever the count changes — it's the single
      most persuasive number on the page.

## Editing anything else

- All page text is plain HTML in `index.html`, organised into clearly
  commented sections (Nav, Hero, Stats, Where we stand, What we do, Quote,
  Join, Groups, Numbers, FAQ, Footer, Mobile join bar).
- Colours and fonts are CSS variables at the top of `style.css`
  (Lora for headings, Karla for body text, via Google Fonts).
- The map (centre point, boundary circle, labels) is a small script at the
  bottom of `map.html`.
