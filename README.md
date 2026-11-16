# Windows VPS hosting: what a plan really costs per month, why the Windows license can outprice the server, and how to size one for .NET, SQL Server or multi-user RDP

A usable Windows VPS starts somewhere between $8.50 and $26 a month, and the gap between those two figures is usually about whether the Microsoft license sits inside the headline price or on a separate line. Vultr puts it on a separate line: its Windows page lists a 1 vCPU / 2 GB instance at $10/month and a $16/month license next to it, so the number that actually leaves your account is $26.

That structure repeats across every size Vultr sells, and it explains why a cheap Windows quote can double by the time you reach checkout. What follows is Vultr's full Windows plan list with both lines added up, how to read per-month pricing from Liquid Web, Contabo and Fasthosts without getting caught by the billing period, where RDP and bandwidth charges show up later, and what the $300 new-account credit is genuinely worth.

> **If you want the short version:** for one ASP.NET site, a small SQL Server database, or a desktop for one or two people, the 2 vCPU / 4 GB size at **$52/month total** ($20 instance + $32 license) is the smallest configuration with room to work. The $26 plan is a test box, not a production one.
> 👉 [See Vultr's current Windows plan list and deploy one](https://www.vultr.com/servers/windows?ref=9738262-9J)

## Vultr's Windows plans, with the license counted in

Vultr treats Windows as a Cloud Compute instance plus a license that steps up by core count: roughly $16 per vCPU, so a 4-core machine carries a $64 license and an 8-core machine carries $128. The eight sizes below are the ones listed on its Windows server page, with the two lines combined.

| vCPU / RAM | SSD / bandwidth | Instance + license | Total per month | Order |
| --- | --- | --- | --- | --- |
| 1 vCPU / 2 GB | 55 GB / 2 TB | $10 + $16 | **$26** | [ Deploy this size](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 2 vCPU / 2 GB | 65 GB / 3 TB | $15 + $32 | **$47** | [ Deploy this size](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 2 vCPU / 4 GB | 80 GB / 3 TB | $20 + $32 | **$52** | [ Deploy this size](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 4 vCPU / 8 GB | 160 GB / 4 TB | $40 + $64 | **$104** | [ Deploy this size](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 6 vCPU / 16 GB | 320 GB / 5 TB | $80 + $96 | **$176** | [ Deploy this size](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 8 vCPU / 32 GB | 640 GB / 6 TB | $160 + $128 | **$288** | [ Deploy this size](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 16 vCPU / 64 GB | 1280 GB / 10 TB | $320 + $256 | **$576** | [ Deploy this size](https://www.vultr.com/servers/windows?ref=9738262-9J) |
| 24 vCPU / 96 GB | 1600 GB / 15 TB | $640 + $384 | **$1,024** | [ Deploy this size](https://www.vultr.com/servers/windows?ref=9738262-9J) |

Two details worth noting before you pick a row. Billing runs hourly against a monthly cap, so spinning up the $52 plan for a two-day migration test costs a few dollars instead of a full month. And the license at the bottom of the range is not a rounding error: on the $26 plan it accounts for 62% of the bill.

The available images cover Windows Server 2025, 2022, 2019 and 2016 in both Standard and Datacenter editions, plus Core variants without the desktop shell. Vultr provisions the license automatically with the image, and an existing Windows license you already own cannot be transferred onto a Vultr instance. If you are carrying a volume license from an old datacenter contract, that matters.

## What "$119 per month" and "€5.50 per month" actually mean

Three hosts can print a monthly price and mean three different things, and this is where most Windows VPS comparisons fall apart.

Liquid Web advertises a 4 GB Windows VPS at $119/month with "15% off for 24 mos." The same card says "You pay $2,856 today," which is $119 × 24. The monthly figure is a two-year prepayment divided by 24. The 8 GB tier works the same way at $142.80/month, or $3,427.20 up front, and the 16 GB tier at $181.05/month, or $4,345.20. In exchange you get Plesk Obsidian, 100 GB of Acronis backups, DDoS protection, and a choice of fully managed, core managed or unmanaged service.

Contabo's Cloud VPS line is priced "for the first 24 months." The 4 vCPU / 8 GB plan lists at €5.50/month on a 24-month commitment, and the discount built into that number only holds while the contract runs.

Fasthosts shows £14/month for its 2 vCPU / 4 GB VPS, labelled "for 3 months." Month four reverts to £22. The same pattern applies up the range: £27 for three months, then £42; £52, then £78.

Vultr sits outside all three conventions. There is no term, no prepayment and no promotional rate that expires in month four. The $26 is $26 next month as well, which is the main argument for paying more at the entry level than Contabo charges.

When you compare any two Windows VPS quotes, ask how many months the advertised rate covers and what gets charged on day one. Those two answers turn most of these prices into different products.

## Is the Windows license included, and why is Windows dearer than Linux?

Atlantic.Net publishes the clearest explanation of the price gap: Linux VPS from $4/month, Windows VPS from $15/month, with the difference attributed to the Microsoft license fee built into the price. That is the industry norm. You are not paying three times more for hardware.

Vultr's version of the same thing is more transparent because it is itemised. The instance is one charge, the license is another, and both appear on the invoice so you can see what a downgrade to Linux would save. The trade-off is that the headline number looks worse than competitors who fold the license in and quote a single figure.

Either way, the license is included in the sense that you never buy a key separately, and it is excluded in the sense that it is a real, per-core cost you pay every month. Budget for it as part of the server price, not as a one-off.

## Sizing the plan to what you're actually running

**A test box, a build agent, or one low-traffic ASP.NET site:** 1 vCPU / 2 GB at $26/month. Windows Server plus IIS plus Windows Update leaves very little headroom on 2 GB, so treat this as a staging environment rather than something customer-facing.

**One production site with SQL Server Express:** 2 vCPU / 4 GB at $52/month. SQL Server Express caps itself at 10 GB per database and 1 GB of RAM, which suits small internal tools and low-traffic sites without a license purchase of its own.

**SQL Server Standard, or a dozen internal users hitting a line-of-business app:** 4 vCPU / 8 GB at $104, moving to 6 vCPU / 16 GB at $176 if the database is larger than a few gigabytes or reports get heavy. SQL Server Standard licensing is a separate purchase and dwarfs the VPS cost at this tier, so size the machine around the database, not the other way round.

**Multi-user remote desktop:** Windows Server includes two concurrent sessions for administration only. Serving more people requires Remote Desktop Services client access licenses bought separately, and hosts that sell into this market say so plainly in their plan descriptions. Count users before you count cores, and remember each signed-in desktop session consumes RAM on top of the OS.

**High-traffic e-commerce or a busy API:** 8 vCPU / 32 GB at $288 and up. At this level the license is a smaller share of the bill, and the question shifts from cost to whether you want managed support at all.

## Bandwidth: "unlimited" almost always has a footnote

OVHcloud advertises unlimited traffic with an asterisk that excludes its Asia-Pacific datacentres. Contabo prints "Unlimited Traffic*" and leaves the asterisk unexpanded on the plan page. Atlantic.Net allows unlimited inbound but charges $0.02 per GB once the free outbound allowance is used, plus $3.65/month for each extra IPv4 address and 20% of the server price for optional daily backups (minimum $1).

Vultr gives each plan a number instead: 2 TB on the entry size, rising to 15 TB on the 24-core machine. A stated allowance is easier to plan against than an asterisk, even when the allowance is smaller than "unlimited."

Also worth pricing in: Vultr's automatic backups are an optional paid add-on rather than part of the plan, and the service is unmanaged. You patch Windows, harden RDP, and configure IIS yourself. Support runs through tickets, with no phone line, and Vultr's Trustpilot score sits at 1.6 out of 5 across 585 reviews. That is what self-service hosting looks like when something breaks at 3 a.m., and it is the honest trade for the price.

## How the other Windows VPS hosts compare

| Provider | Windows entry price (as listed) | Billing basis | Best fit |
| --- | --- | --- | --- |
| Vultr | $26/mo total (1 vCPU / 2 GB, 55 GB SSD, 2 TB) | Hourly, monthly cap, no contract | Frequent redeploys, 32 locations in 19 countries, itemised licensing |
| OVHcloud | From $8.50/mo (4 vCores / 8 GB / 75 GB NVMe) | Monthly, 99.9% SLA | European hosting, generous specs at low cost, but unlimited traffic excludes APAC |
| Contabo | €5.50/mo list (4 vCPU / 8 GB / 100 GB SSD, 200 Mbit/s) | 24-month term, unmanaged | Lowest cost per GB of RAM if you can commit two years |
| Atlantic.Net | From $15/mo | Monthly, metered extras | Legacy Windows images back to 2008 R2, transparent overage pricing |
| Fasthosts | £14/mo for 3 months, then £22 (2 vCPU / 4 GB / 120 GB NVMe) | 1 or 12-month contract | UK, German, Spanish or US datacentres on a short commitment |
| Liquid Web | $119/mo on a 2-year prepay, $2,856 today (2 vCPU / 4 GB) | 24-month prepayment | Managed Windows with Plesk and backups, when you want someone else to run it |

Read that table with the previous section in mind. Contabo's €5.50 and Liquid Web's $119 are not describing the same kind of purchase, and neither is directly comparable to Vultr's $26 until you convert all three to "total charged in year one."

## What the $300 credit actually pays for

Vultr's coupons page lists several new-customer offers at once. The $300 credit comes from code **FLY300VULTR**; there are also 250VULTRFLY for $250, FLYTWOHUNDRED for $200, and VULTRMATCH, which matches your first deposit dollar for dollar up to $100. Every one of them carries the same terms: new customers only, promotional credit applies to select products only, and they cannot be combined with another offer. Pick one.

Two things the coupon page does not spell out, and both change the maths. Credit expiry is not stated there, so confirm the window before you build a plan around the balance. And "select products only" may or may not cover the Windows license line, which is worth checking before you assume the credit is paying for your whole server.

Run the numbers against real plans and the credit reads as trial budget rather than a discount on a year. At $26/month, $300 covers about eleven months of the entry Windows machine. At $52/month it covers under six. At $104/month it disappears in under three. If the credit expires in 30 days, as promotional balances usually do, then what you are really buying is five weeks of unrestricted testing on hardware you would otherwise rent by the hour.

That is still useful. Deploy the $52 plan, install your application, run a load test, and shut it down. You will know more about whether Vultr fits your stack than any review can tell you.

👉 [Check the live credit codes and terms on Vultr's coupons page](https://www.vultr.com/coupons?ref=9738262-9J)

## When Vultr is the wrong pick

If you want someone else to patch Windows, tune IIS and answer the phone, Liquid Web's managed tiers are built for that and priced accordingly. If the lowest possible cost per gigabyte of RAM is the deciding factor and a two-year contract does not scare you, Contabo's arithmetic is hard to beat. If your software only runs on Windows Server 2008 R2 or 2012 R2, Atlantic.Net still lists images going back to 2008 R2 SP1, while Vultr starts at 2016. And if you need a European provider with a published SLA and datacentres close to EU users, OVHcloud starts at $8.50/month with 8 GB of RAM.

Vultr's case rests on three things: hourly billing with no term, Windows 2025 images available on day one, and a license cost you can see before you buy instead of discovering it in a quote.

## Picking a plan, and what to confirm before you pay

Match the workload, not the brochure. A test box or a single small site goes on the $26 plan. A production site with a database goes on $52, and a database larger than a few gigabytes pushes you to $104 or $176. Multi-user remote desktop needs RDS licenses priced separately no matter which host you choose, and high-traffic commerce starts at $288.

Three questions to settle before entering card details, with any provider:

1. What is charged today, and what does the same plan cost in month 13?
2. Which Windows Server version and edition does the default image give you, and does the application support it?
3. Is the Windows license part of the advertised price, and is it covered by whatever credit you are applying?

Get those three answers and the comparison stops being about headline prices. Vultr answers the second and third on its own pages, which is more than most of its cheaper competitors do.

👉 [Start from Vultr's Windows server list and pick a size](https://bit.ly/VuLtr)
