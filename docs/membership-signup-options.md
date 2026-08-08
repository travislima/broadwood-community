# Making it easy to join the BCRA from WhatsApp

The problem: pamphlets and paper debit order forms lose people. Most residents
live on WhatsApp, so the sign-up journey should be: **see a message → tap a
link → approve → done**, ideally without a human having to capture forms.

The association already collects R100/month by debit order from 48 members,
so someone on the committee already runs collections (through a bank or a
debit order bureau). That's the first thing to find out — **who processes the
current debit orders?** — because the cheapest upgrade is usually a feature
of whatever they already use.

## Option A — Electronic debit order mandates (best fit)

Debit order bureaus like [Netcash](https://netcash.co.za/what-is-an-emandate/)
offer **eMandates**: the committee sends a link (WhatsApp/SMS/email), the
resident fills in their details on a secure page, signs with an OTP, and —
for DebiCheck mandates — approves the R100/month debit order in their own
banking app. Fully paperless, PASA-compliant, and it lands in the same
debit order run the association already does.

- Resident experience: tap link in WhatsApp → 2-minute form → approve in
  banking app. Official and bank-verified, which builds trust.
- Cost: bureau service fees (often already being paid); no percentage cut.
- Action: ask the treasurer whether the current provider supports
  eMandates / DebiCheck mandate links. Netcash, and most SA bureaus, do.

## Option B — Card subscription link (fastest to launch)

[Payfast](https://payfast.io/features/subscriptions/) supports **recurring
billing**: create a R100/month subscription and share the payment link
directly in WhatsApp. Residents subscribe with a card in under a minute —
no forms, no committee admin. Also handles once-off donations.

- Cost: no monthly fee, roughly 3.2% + VAT per transaction (~R4 of each R100).
- Needs: association bank account + registration documents to open the
  Payfast account.
- This can run alongside Option A: "Debit order or card — your choice."

## Option C — Look official on WhatsApp itself (free, do regardless)

- Use the **WhatsApp Business app** (free) for the membership number: adds a
  business profile with the BCRA name, logo, description and website link,
  plus quick replies (e.g. a saved reply with the sign-up steps + links).
- Put the website and sign-up links in both **group descriptions** and a
  pinned/recurring message.
- A **QR code poster** (gate motifs, streetlight poles, Charlo Primary
  noticeboard) that opens WhatsApp with a pre-filled "I'd like to join"
  message — the website already generates that message automatically once
  `contactWhatsApp` is set.

## What NOT to do

**WhatsApp Business API / Flows / chatbots** (in-chat forms) are real but
priced for companies — R300–R5,000+ per month plus setup
([SA pricing overview](https://themessengernetwork.co.za/thought-leadership/whatsapp-business-api-pricing-south-africa/)).
Wrong fit for a volunteer association; the link-based options above achieve
the same outcome for near-zero cost. WhatsApp's built-in payments product
isn't available in South Africa.

## The recommended funnel

1. Resident sees a group message / poster / the website.
2. Taps through to the site's **Join** section (single link to share:
   `<site-url>/#join`).
3. Chooses **debit order** (eMandate link) or **card** (Payfast link) —
   both buttons appear automatically once the links are pasted into the
   config block at the top of `index.html` (`debitOrderLink`,
   `cardPaymentLink`).
4. Falls back to "message the membership contact on WhatsApp" for anyone
   who prefers a human.

POPIA note: whoever holds the member list should collect only what's needed
(name, address, contact, mandate) and say what it's used for — the eMandate
route handles consent properly by design.
