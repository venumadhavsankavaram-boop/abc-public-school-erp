erp-template deploy package — ABC Public School
==================================================================

public/index.html, public/manifest.json and the four public/icon-*.png
files in this zip already carry this school's colours and branding.
Unzip this over a fresh clone of erp-template/ (replacing its public/
folder entirely) before that school's first deploy — no manual CSS edit
needed.

Three things this zip can't fill in for you, because they don't come
from the website content at all:

1. A Postgres database for this school (Neon) — set DATABASE_URL on the
   ERP's Render service to its connection string.

2. On the WEBSITE's Render Static Site → Settings → Headers, add:
     Path: /theme.json   Name: Access-Control-Allow-Origin   Value: *
   Without this one-time step, future colour changes never reach the
   ERP — it silently keeps today's colours as a fallback, no error.

3. Click "Register this school in vendor-dashboard" (next to this
   download, in the Website Builder) — after saving there, it shows a
   ready .env block with VENDOR_DASHBOARD_URL / VENDOR_SCHOOL_ID /
   VENDOR_API_KEY / WEBSITE_ORIGIN already filled in. Paste that whole
   block into the ERP's Render → Environment.

   Optional, only if this school uses them: RAZORPAY_KEY_ID,
   RAZORPAY_KEY_SECRET (online fee payment), BIOMETRIC_API_KEY
   (biometric attendance).
