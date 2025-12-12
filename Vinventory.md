# VINventory: The Revolution That Never Was (And Maybe a Car Parts Cartel)

## The Situation

**Date:** December 2020 - August 2022  
**Role:** Technical Co-founder (in theory)  
**Company:** VINventory — a startup attempting to revolutionize auto salvage yard inventory

Chris brought me on as "the tech" for a two-person startup. We'd known each other for years, always planned to work together. This was finally that venture.

Chris had partnered with someone named Josh. From the start, whenever Josh was in the room or anything about their side deals came up, I was told "don't worry about it."

That was the first red flag. There would be more.

## The Technology (This Part Was Real)

Josh and Chris were trying to acquire a product called VINData, created by Terry Lindel.

Terry is a genuine genius. He helped invent PCR DNA testing. He also spent time in the auto industry, working with John Hollander of Hollander YMS — the largest software inventory system for salvage yards in the country.

**The problem Terry solved:**

Salvage yard inventory was entirely manual. A yard gets a car, strips it for parts, lists them — but they don't actually know the OEM part numbers. They guess at prices. Everything is approximation.

Terry figured out how to use collision data from MOTOR, pair it with engine specs, and **reverse-engineer the complete OEM parts list for any vehicle based solely on its VIN.**

This was unprecedented. Only car manufacturers knew what OEM parts were on a specific vehicle. They kept it secret deliberately.

**Why it mattered:**

Take the tow hook on a 2019 Ford F-150.

Dealers price it at $30-80. Hollander didn't even have a category for it — just "MISC," price whatever you want.

The actual Ford OEM part? **$250.**

And because salvage yards are pulling *original* OEM parts off vehicles — not remanufactured — there's no stigma. It's the real thing.

For yards, this was instant money. "Shut up and take my money" deals.

## The Cartel Discovery

While building scraping tools, we discovered something disturbing.

**The same part, from the same source, showed different prices depending on where you searched from.**

- Rural Illinois searching a NYC dealer site: intake manifold shows $500
- Los Angeles searching the same site, same part: $850

This wasn't random. It was systematic. Pricing varied by source region and economic status of the area.

Terry's goal wasn't just inventory — he wanted to expose the price distribution nationwide. Show yards (and consumers) they were being played.

**The vendors did not like this.**

They especially didn't like that we could connect a VIN to OEM parts. This was always an uphill battle. Someone was protecting the pricing game.

## The Con

I was in startup mode. Building landing pages, doing presentations on features like carburetor reclaims. Bringing in what I thought was operating cash.

I'd build a landing page, told it was "part of my day-to-day responsibilities."

Later I found out they charged the client **$30,000** for that site.

I saw none of it.

**The RotoRecyclers moment:**

They asked me to build a site for a new venture — formalizing rotor scrap collection into a branded business.

By now, I'd learned my lesson. I told them upfront: I want revenue. A cut.

Josh was furious.

Then I discovered they already had **six paying clients at $2,000/month each** — doing everything by hand while I was building the POC. I was left completely out of the loop.

100% of the business was me building software. I was getting peanuts.

I told them good luck and walked.

## The Aftermath

About a year later, I talked to Terry.

He filled me in:
- Massive back debt I never knew about
- They weren't paying their MOTOR licensing costs
- They were trying to take the software from Terry
- I was a pawn the entire time

I had suspected something wasn't right. I'd started delaying asks, running things by Terry before acting. But I didn't see the full picture until it was over.

VINData could have been huge. Revolutionary tech that exposed pricing manipulation and gave small yards real power.

Instead, it's sitting idle.

## Technical Stack Summary

**Platform:**
- Custom landing pages
- Scraping infrastructure
- VIN-to-OEM mapping engine (Terry's core tech)

**Data Sources:**
- MOTOR collision data
- Engine specification databases
- Multi-region price scraping

**Integrations:**
- Hollander YMS ecosystem
- Dealer service site APIs (scraped)

## Lessons

1. **"Don't worry about it" is always a red flag.** When partners hide things from the person building the product, they're hiding things for a reason.

2. **Know what your work is worth.** A $30,000 landing page isn't "day-to-day duties." I was being exploited and didn't see it.

3. **Revolutionary tech means nothing with bad actors.** VINData could have changed an industry. Josh and Chris buried it.

4. **Trust but verify with the source.** Running things by Terry before acting probably saved me from worse.

5. **Some industries protect their pricing games.** The regional price manipulation we found wasn't a bug. Someone benefits from that opacity.

---

*Wayne Renbjor (Wren.AI) — Solutions Architect, 18+ years*
[LinkedIn](https://linkedin.com/in/wrenbjor) | [GitHub](https://github.com/wrenbjor) | [Twitter/X](https://x.com/wren_ai) | [Tiktok](https://tiktok.com/@wren.ai)