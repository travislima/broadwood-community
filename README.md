# Broadwood/Charlo Residents Association — website

A single-page brochure site for the BCRA (Broadwood & Charlo, Gqeberha / Port
Elizabeth). It encourages residents to join the association at R100 a month,
shows what the money funds, and acts as a quick reference for the community
WhatsApp groups and important phone numbers.

**No build step, no dependencies.** It's one HTML file and one CSS file,
designed to be hosted free on GitHub Pages and edited by hand.

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
| `paidMembers` | Households currently paying by debit order (the big progress number). |
| `memberGoal` | Total properties in the area (currently 800). |
| `contactName` | Name of the person who signs members up, e.g. `"Jane Doe"`. |
| `contactWhatsApp` | Their WhatsApp number, digits only with country code, e.g. `"27821234567"`. Adds "Message … on WhatsApp" buttons with a pre-filled sign-up message. |
| `emergencyGroupLink` | WhatsApp invite link for the Emergency group (Group info → Invite via link). |
| `socialGroupLink` | WhatsApp invite link for the Social group. |
| `facebookLink` | URL of the association's Facebook page. |
| `citywideNumber` | CityWide Security control room number, e.g. `"041 123 4567"`. |
| `sapsStationNumber` | SAPS Walmer CSC — pre-filled with `041 581 0747` from the emergency group's rules. |
| `municipalityNumber` | Nelson Mandela Bay faults/call-centre number. |
| `bank.*` | Account name, bank, account number, branch code and suggested reference for debit orders and once-off donations. |
| `photos` | Photos for the "Our neighbourhood" section. Upload images to an `images/` folder in this repo (on GitHub: **Add file → Upload files**), then add one line per photo: `{ src: "images/name.jpg", caption: "..." }`. The section stays hidden until at least one photo is listed. Use real photos from the community — clean-ups, streets, camera installations. Keep each under ~500 KB so the page stays fast. |

Any field left as `""` shows a sensible placeholder ("To be confirmed" /
"To be added") instead of a broken link — so the site is safe to publish
before all the details are in.

### Before going live — checklist

- [ ] Get the committee's permission before publishing anyone's name or
      phone number, and fill in `contactName` / `contactWhatsApp`.
- [ ] Fill in the banking details (`bank.*`) — verify them with the treasurer.
- [ ] Add the WhatsApp group invite links, or leave the "ask an admin" fallback.
- [ ] Fill in the CityWide control-room and municipality numbers after
      verifying them by phone. The SAPS Walmer CSC number (041 581 0747)
      comes from the emergency group's rules — worth a quick verification
      call too. (National numbers 10111 / 112 / 10177 are already on the site.)
- [ ] Update `paidMembers` whenever the count changes — it's the single most
      persuasive number on the page.

## Editing anything else

- All page text is plain HTML in `index.html`, organised into clearly
  commented sections (Hero, Stats, Progress, What we do, Join, Groups,
  Important numbers, FAQ).
- Colours, fonts and layout are in `style.css` (colour variables at the top).
- The illustrations are inline SVG — no image files to manage.
