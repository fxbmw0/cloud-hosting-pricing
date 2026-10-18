# cloud hosting services: managed vs unmanaged, real entry prices, and the hidden costs most roundups skip

Type "cloud hosting services" into a search engine and you get two products that barely overlap, both sold under the same label. One half of the results is managed hosting for websites and WordPress stores, where the provider patches, caches, and backs everything up for you. The other half is raw cloud servers: you get a root password, a blank machine, and total responsibility. Vultr sits firmly in the second camp, and that single distinction decides everything else — the price you'll actually pay, the skills you need, and whether a "$2.50" plan is usable for your project or a trap.

This guide separates the two camps, lays out what entry plans really cost as of late 2026, and covers the fine print that most top-ranking roundups skip: IPv4 add-ons, egress fees, backup upsells, and renewal jumps.

> **Quick take:** if you can work in a terminal and want the lowest sensible price per server, Vultr's cloud compute starts at **$2.50/month** (IPv6-only) or **$5/month** with IPv4, deployable across 30+ data center locations. If you never want to see a command line, a managed option like Cloudways ($11/mo) or Hostinger Cloud ($7.99/mo on a 48-month term) will save you from yourself. 👉 [Check Vultr's live pricing page for the current plan list](https://www.vultr.com/pricing/?ref=7268283)

## What "cloud hosting services" actually covers

Cloud hosting means your site or app runs on virtual servers drawing from a large shared pool of physical hardware. If one machine fails, your server restarts on another; if traffic spikes, you add CPU, RAM, or storage in minutes instead of migrating to a new box. That's the common thread. Where providers differ is in who runs the server.

In 2026 the market splits into three flavors, and mixing them up is the most common buying mistake:

- **Managed cloud hosting** — Cloudways, Kinsta, Hostinger Cloud. The provider handles the stack, security patches, caching, and backups. You manage the website.
- **Unmanaged cloud servers** — Vultr, DigitalOcean, Hetzner, Akamai Cloud, AWS Lightsail. You get root access to a virtual machine and do all server work yourself.
- **Hyperscale clouds** — AWS, Google Cloud, Microsoft Azure. Hundreds of services, per-second metering, and the steepest learning curve. These three hold about 63% of the market combined (28%, 15%, and 20% respectively in Q2 2026), but most small projects don't need that machinery.

Vultr is unmanaged. Everything below follows from that.

## Vultr's plans and entry pricing

Vultr's cheapest cloud compute plan costs $2.50/month if you accept an IPv6-only address, or $5/month with IPv4 included. Beyond the entry tier, the catalog scales up through higher-spec compute instances, plus separate bare metal and GPU lines — dozens of configurations rather than three fixed "plans." Comparison catalogs list the smallest instance at around 512 MB RAM, 1 vCPU, and 10 GB of NVMe storage, which is enough for a lightweight app, a reverse proxy, or a small self-hosted stack, and tight for a busy database.

Here's the verified entry picture:

| Plan line | Entry configuration | Starting price | Billing basis | Buy |
| --- | --- | --- | --- | --- |
| Cloud Compute (IPv6-only) | ~512 MB RAM, 1 vCPU, 10 GB NVMe SSD class | $2.50/mo | Monthly list price | [See current price](https://www.vultr.com/pricing/?ref=7268283) |
| Cloud Compute (with IPv4) | Entry VM with IPv4 address included | $5.00/mo | Monthly list price | [See current price](https://www.vultr.com/pricing/?ref=7268283) |
| Bare Metal | Dedicated physical servers | Varies by server — see live pricing | Monthly list price | [See options](https://www.vultr.com/pricing/?ref=7268283) |
| GPU Compute | GPU instances for AI/training | Varies by GPU type — see live pricing | Monthly list price | [See options](https://www.vultr.com/pricing/?ref=7268283) |

The IPv6 detail deserves its own paragraph, because it's the thing budget roundups gloss over. The $2.50 tier ships without an IPv4 address. Plenty of modern networks handle IPv6 fine, but some home connections, office networks, and older resolvers still don't — so a public site on the IPv6-only plan can be unreachable for part of your audience. For anything visitors need to reach reliably, the $5 tier with IPv4 is the practical floor. The $2.50 plan makes sense for experiments, internal tools, VPN endpoints, and IPv6-ready side projects. 👉 [See Vultr's IPv4 and IPv6 entry plans on the pricing page](https://www.vultr.com/pricing/?ref=7268283)

Two more things to know before you click. First, deployment location matters: Vultr runs 30+ data centers, and you should pick the one closest to your visitors rather than the default. Second, "unmanaged" is literal — updates, firewall, backups, and monitoring are your job from minute one.

## Why some 2026 price lists are already out of date

Memory and storage prices rose sharply in 2026 because AI data centers absorbed much of the world's DRAM and flash supply, and at least one major hosting provider passed those costs straight to customers. If a roundup you're reading still quotes 2025 prices, its budget math is probably wrong.

Hetzner is the clearest documented case: it raised prices on April 1, 2026, then again on June 15, 2026. The entry CX23 plan (2 vCPU, 4 GB RAM) went from €3.99 to €5.49 per month, while the AMD-based CPX22 jumped from €7.99 to €19.49. Vultr's entry pricing has held at $2.50/$5 through these checks, but the lesson generalizes: verify against the live pricing page before you budget, not against a months-old article.

The demand side explains why this isn't a blip. Cloud infrastructure spending hit $143.4 billion in Q2 2026, up about 43% year over year — the fastest growth in eight years, per Synergy Research Group. Gartner expects public cloud spending to grow another 21.3% in 2026. One more number worth internalizing, from Flexera's 2026 State of the Cloud survey: organizations estimate 29% of their cloud spend is wasted. Right-sizing your server matters as much as picking the provider.

## Managed vs unmanaged: where Vultr fits

Vultr's $2.50–$5 entry tiers buy you a virtual machine, and nothing else. Managed platforms buy you a working stack. Here's how the verified entry points compare across the market:

| Provider | Management | Entry price (checked Sept 2026) | Standout detail |
| --- | --- | --- | --- |
| DigitalOcean | Unmanaged | $4/mo (512 MB RAM, 1 vCPU, 10 GB SSD) | Per-second billing since Jan 1, 2026 |
| Akamai Cloud (Linode) | Unmanaged | $5/mo | Egress overage at $0.005/GB; backups cost extra on the smallest tier |
| Hetzner | Unmanaged | €5.49/mo + IPv4 | 2 vCPU, 4 GB RAM class; two price hikes in 2026 |
| AWS Lightsail | Unmanaged | $3.50/mo (512 MB RAM, 2 vCPU, 20 GB SSD) | Bundled AWS pricing; 3 months free on select bundles |
| Cloudways | Managed | $11/mo (1 GB RAM, 1 vCPU, 25 GB SSD) | Managed layer over DigitalOcean, AWS, Google Cloud, Vultr, or Linode; 3-day free trial, no card |
| Hostinger Cloud | Managed | $7.99/mo (48-month term) | Renews at $25.99/mo; 99.9% uptime, 30-day money-back |
| Kinsta | Managed WP | $35/mo | Fully managed WordPress on Google Cloud |

Notice the pricing model difference. Managed hosts lean on a promo-then-renewal structure: Hostinger Cloud looks like $7.99/month, but that's a 48-month commitment — roughly $384 over four years — after which renewal runs $25.99/month, about 3.3× the promo rate. Vultr's list price is the ongoing rate; there's no promo clock ticking toward a renewal jump. Over a multi-year horizon, that can make "cheap" managed plans more expensive than they first appear, and it's a math step most comparison posts never do for you.

Who should skip Vultr entirely? If your project is a WordPress site or WooCommerce store and you don't want to think about server caches, malware scanning, or backup schedules, an unmanaged VM will feel like buying a car with no seats. Managed options exist precisely for this, and it's telling that consumer-facing rating catalogs put managed hosts like ChemiCloud (91/100), InMotion (91/100), and SiteGround (90/100) at the top of their cloud rankings — raw dev clouds simply aren't built for casual site owners. But if you're a developer, an agency spinning up client staging servers, or someone self-hosting apps in Docker, root access is the feature, not a flaw. 👉 [Compare Vultr's compute plans and data center locations here](https://www.vultr.com/pricing/?ref=7268283)

## Five quick decision rules

No quiz, no funnel — just the short version:

1. **Cheapest workable dev VM, terminal-comfortable** → Vultr at $2.50/mo (IPv6-only) or $5/mo with IPv4.
2. **Public website for a mixed audience** → any plan that includes IPv4, such as Vultr's $5 tier.
3. **Non-technical WordPress or ecommerce** → managed: Cloudways at $11/mo, or Hostinger Cloud at $7.99/mo if you accept the $25.99 renewal and 48-month term.
4. **Bandwidth-heavy project** → weight egress fees first; Akamai's $0.005/GB overage is the benchmark to beat.
5. **Already inside the AWS ecosystem** → Lightsail at $3.50/mo. Need GPUs for AI work → compare Vultr's GPU line and bare metal against specialist providers.

## FAQ

**How much do cloud hosting services cost per month?**
Entry-level unmanaged servers run from $2.50/mo (Vultr, IPv6-only) to $6.49/mo depending on provider and IPv4 inclusion; managed cloud starts around $7.99–$11/mo; hyperscalers bill pay-as-you-go with no fixed floor. For a real total, add three things to the sticker price: IPv4, backups, and bandwidth overages. 👉 [See Vultr's full price list before you budget](https://www.vultr.com/pricing/?ref=7268283)

**What's the catch with the cheapest plans?**
Three recurring ones. The cheapest Vultr tier omits IPv4, which breaks reachability for some visitors. Some providers charge for backups as an add-on — Akamai's smallest shared-CPU tier is one documented example. And bandwidth allowances vary widely, so a "cheap" server with expensive egress can cost more than a pricier plan once traffic flows.

**Do cheap promo prices renew higher?**
On raw cloud platforms, generally no — you pay the list rate from day one. On managed hosting, often yes: Hostinger Cloud renews at $25.99/mo after the 48-month promo, and SiteGround's shared plans go from $2.99 to $17.99/mo. Always read the renewal line before committing to a long term.

**Cloud hosting vs a VPS — what's the difference?**
They overlap. A classic VPS is a reserved slice of one physical machine; cloud hosting runs your workload on virtual servers backed by a shared pool, with failover to other hardware if one machine dies. In practice, entry-level unmanaged "cloud" instances like Vultr's behave like very flexible VPSes — which is exactly why they suit developers who want VPS control without hardware limits.

**Is Vultr a good choice for beginners?**
If "beginner" means your first WordPress site, no — you'd be doing your own server administration, and a managed plan fits better. If it means your first VPS while learning server admin, Vultr is a reasonable on-ramp: low entry cost, 30+ locations, and you can destroy and rebuild instances cheaply while you practice.

## Before you order

Match the plan to what you'll actually run. Building apps, staging servers, or self-hosted tools and comfortable with a shell → Vultr's $5 IPv4 tier is the practical starting point, with $2.50 for experiments that can live on IPv6. Running a business site you don't want to administer → pick one of the managed options above and read the renewal price twice. Bandwidth-heavy workload → do the egress math before comparing sticker prices.

One last practical step, since 2026 has already produced two documented price-hike rounds at major providers: confirm the current numbers on the official pricing page before paying, because third-party roundups — this one included — can lag a price change by weeks. 👉 [Check Vultr's current plans and prices](https://bit.ly/VulTR)
