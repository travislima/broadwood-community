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

### Custom domain (optional)

1. Buy a domain (e.g. `bcra.org.za`).
2. In **Settings → Pages → Custom domain**, enter the domain and follow
   GitHub's DNS instructions (a CNAME record pointing to
   `<username>.github.io`).
3. Tick **Enforce HTTPS** once the certificate is issued.

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
| `debitOrderLink` | Self-service e-mandate link from the debit order provider (see `docs/membership-signup-options.md`). Shows a "Set up my debit order online" button when filled. |
| `cardPaymentLink` | Recurring card subscription link (e.g. Payfast R100/month). Shows a "Subscribe with my card" button when filled. |
| `emergencyGroupLink` / `securityGroupLink` / `socialGroupLink` | Optional WhatsApp invite links (Group info → Invite via link). If set, the group button links straight to the group; otherwise it falls back to a pre-filled "please add me" WhatsApp message (needs `contactWhatsApp`). |
| `annualDonors` | Households that supported the association with once-off/annual donations this past year. Shows a thank-you line in the donations panel; leave `0` to hide it until the committee provides the number. |
| `citywideNumber` | CityWide Security control room number, e.g. `"041 123 4567"`. Fills the dashed card and makes it tap-to-call. |
| `sapsStationNumber` | SAPS Walmer CSC — pre-filled with `041 581 0747` from the emergency group's rules. |
| `municipalityNumber` | Nelson Mandela Bay faults/call-centre number. |
| `bank.*` | Account name, bank, account number and branch code for debit orders and once-off donations. |

Any field left as `""` shows a sensible placeholder ("To be confirmed" /
dashed "To be added" card / "ask an admin" fallback) instead of a broken
link — so the site is safe to publish before all the details are in.

### Before going live — checklist

- [ ] Set `contactWhatsApp` to the real membership number (get the
      committee's permission first). **Do not launch a join campaign
      without this** — it's the whole funnel.
- [ ] Fill in the banking details (`bank.*`) — verify them with the treasurer.
- [ ] Fill in the CityWide control-room and municipality numbers after
      verifying them by phone. The SAPS Walmer CSC number (041 581 0747)
      comes from the emergency group's rules — worth a verification call too.
- [ ] Confirm the milestone labels (100 / 200 / 400 households) and the
      "How do I know the money is well spent?" FAQ wording with the
      committee — the FAQ has a "to be confirmed" note to remove.
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
