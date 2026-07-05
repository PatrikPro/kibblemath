# KibbleMath — dog calculators

A static, dependency-free site: 6 dog calculators + info pages. No build step,
no backend, nothing to maintain. Hosting is free; your only cost is the domain.

**Live at:** https://kibblemath.com

## Preview locally (optional)
    cd kibblemath
    python3 -m http.server 8000
Then open http://localhost:8000

## 1) Pick and buy a domain (~$10/year)
First choice: **kibblemath.com**. Backups if taken: wagmath.com, pawsums.com,
muttmetrics.com. Register at Cloudflare Registrar or Porkbun (at-cost pricing).

If you change the brand name, rename everywhere with:
    grep -rl 'KibbleMath' . | xargs sed -i 's/KibbleMath/NewName/g'
    grep -rl 'Kibble<b>Math' . | xargs sed -i 's/Kibble<b>Math<\/b>/New<b>Name<\/b>/g'

## 2) Replace the placeholder domain (required before going live)
    grep -rl 'REPLACE-DOMAIN.com' . | xargs sed -i 's/REPLACE-DOMAIN.com/yourdomain.com/g'

Also open /privacy/index.html and fill in:
- [YOUR NAME]  -> your legal name
- [YOUR IČO]   -> your IČO
And decide your contact email (hello@yourdomain — free email forwarding is
included with Cloudflare "Email Routing").

## 3) Deploy (free)
**Fastest (2 min):** netlify.com -> "Deploy manually" -> drag the kibblemath
folder in. Done.
**Best long-term:** push this folder to a GitHub repo, then Cloudflare Pages ->
connect repo -> framework: None -> deploy. Every future edit = git push.

Then add your custom domain in the host's dashboard (HTTPS is automatic).

## 4) Search engines (day 1)
- Google Search Console: add your domain (DNS verification), then submit
  https://yourdomain.com/sitemap.xml
- Bing Webmaster Tools: sign in, import from Search Console (1 click).

## 5) Analytics (free, cookieless, no consent banner needed)
Cloudflare Web Analytics -> add site -> copy the JS snippet -> paste it right
before </body> on the pages (or one sed command; ask Claude). If you host on
Cloudflare Pages, you can enable it with one toggle instead, no snippet needed.

## Monetization plan (in order — don't rush this)
1. Now–month 2: nothing. Traffic first. Adding ads/affiliates to an empty site
   wastes approvals.
2. From first real traffic: Awin (Zooplus, Fressnapf/EU pet retailers) and/or
   Amazon Associates. IMPORTANT: Amazon closes accounts with no sales within
   180 days — apply only once you have visitors.
3. ~10k sessions/month: apply to Journey by Mediavine for display ads.

## Growth backlog (do with Claude, in this order)
- 10 supporting articles targeting long-tail questions (each links to a tool):
  "how many grams of food for a 10 kg dog", "dog food kJ to kcal", "puppy
  feeding schedule by age", "when do labradors stop growing", etc.
- More tools: cat versions of everything (cat calorie/age/food = 2x keywords),
  BCS (body condition) visual guide, kennel cost calculator.
- Translations later if desired (cs/de versions = new keyword space).

## Realistic expectations
New domains typically see near-zero Google traffic for 2–4 months. That's
normal, not failure. The compounding starts after indexing + content depth.
