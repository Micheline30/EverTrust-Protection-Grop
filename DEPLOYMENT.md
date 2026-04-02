# Evertrust Platform — Deployment Guide

## Platform Structure
```
evertrust-platform/
├── admin/index.html       ← YOUR admin dashboard (you only)
├── agency/index.html      ← Agency login portal (your clients)
└── dialer/index.html      ← The dialer tool (agents access via agency portal)
```

## What Each File Does

| File | Who Uses It | What It Does |
|------|-------------|--------------|
| admin/index.html | You (Evertrust) | Manage all agencies, billing, seats, analytics |
| agency/index.html | Each agency's agents | Login, dashboard, launch dialer |
| dialer/index.html | Agents | The full dialer tool |

---

## Step 1 — Deploy for Free on Netlify (Recommended)

1. Go to **netlify.com** → Sign up free
2. Drag & drop the entire `evertrust-platform/` folder onto their deploy zone
3. You'll get a URL like: `https://evertrust-platform.netlify.app`
4. (Optional) Connect a custom domain like `app.evertrust.com` for $0 extra

Your URLs will be:
- Admin: `https://your-site.netlify.app/admin/`
- Agency portal: `https://your-site.netlify.app/agency/`
- Dialer: `https://your-site.netlify.app/dialer/`

---

## Step 2 — Pricing Setup

### Standard Plan — $45/seat/month
- Agencies buy seats from you directly
- Send them the agency portal URL + login credentials you create for them

### White-Label Plan — $65/seat/month
- Same as Standard
- Additionally customize the agency/index.html with their logo/brand before delivery

### Collect Payment (Free options)
- **Gumroad**: Create a product, set recurring billing, share link
- **Stripe Payment Links**: No website needed, just share a link
- **PayPal**: Quickest to set up if you already have an account

---

## Step 3 — Onboarding a New Agency

1. Collect payment (Gumroad/Stripe link)
2. Open `admin/index.html` → click "+ Add Agency" → fill in their details
3. Create their login credentials (you manage these manually for now)
4. Send them:
   - Agency portal URL
   - Their email + temporary password
   - A short onboarding guide (see template below)

---

## Agency Onboarding Email Template

> Subject: Your Dialer Access is Ready — [Agency Name]
>
> Hi [Contact Name],
>
> Your account is set up and ready to go. Here's everything you need:
>
> **Portal URL:** https://your-site.netlify.app/agency/
> **Email:** [their email]
> **Temp Password:** [set a temp password]
>
> From the portal you can:
> - Launch the dialer directly
> - Import your lead CSV
> - Manage your team seats (Admin accounts only)
>
> I recommend starting with our outbound opening script — it's designed specifically for life insurance old-lead reactivation.
>
> If you have any questions, reply to this email or text me at [your number].
>
> — Evertrust Legacy Protection Group

---

## Step 4 — Upgrading (When You're Ready)

Once you have 5+ paying agencies, these upgrades become worth it:

| Upgrade | Tool | Cost | What it adds |
|---------|------|------|--------------|
| Real user database | Supabase | Free tier | Agents manage their own passwords |
| Automated billing | Stripe | 2.9% + 30¢ | Auto-charge agencies monthly |
| Custom domain | Namecheap | ~$12/yr | app.evertrust.com |
| Email automation | Mailchimp | Free to 500 | Auto onboarding emails |

---

## Admin Credentials (Change These!)
- Email: `admin@evertrust.com`
- Password: `admin123`

## Agency Demo Credentials
- Admin: `admin@agency.com` / `admin123`
- Agent: `agent@agency.com` / `agent123`

> ⚠️ Before going live, update the hardcoded credentials in both HTML files.

---

## Revenue Calculator

| Agencies | Avg Seats | Plan | MRR |
|----------|-----------|------|-----|
| 5 | 4 | Standard ($45) | $900 |
| 10 | 5 | Standard ($45) | $2,250 |
| 10 | 5 | White-Label ($65) | $3,250 |
| 20 | 6 | Mixed avg ($55) | $6,600 |

**At 20 agencies you're at ~$80K ARR from a product that cost you $0 to build.**
