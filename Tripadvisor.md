# TripAdvisor (Cruise Critic): The "Worst Idea Ever" That Google Built Two Years Later

## The Situation

**Date:** August 2022 - August 2023  
**Role:** Senior Software Engineer  
**Company:** Cruise Critic — a subsidiary of TripAdvisor

I got here through Jim Yoast, a peer from my Comcast days. We still talk every week. I was in his wedding.

Cruise Critic needed someone with legacy PHP experience. The front end was modern — React and GraphQL — but huge parts of the site were still managed by a bespoke admin system written in PHP that hadn't aged well.

## What Was Broken

**The Article System**

The news department was stuck using an ancient interface to write articles. No rich formatting. Clunky workflow. They complained constantly, and rightfully so.

**The Cruise Data Pipeline (CoTA)**

"Cruise On TA" was a legacy Java app that needed to feed cruise data to the primary TripAdvisor site.

The TripAdvisor engineering leadership wouldn't let us build a REST API. No explanation given. Instead, we had to:
1. Create a daily data dump to CSV
2. Build an ingester for that CSV
3. Get sign-off on new tables in the primary TA database (took weeks)
4. Create a Java module to load the data and expose it to the frontend

A REST API would have taken days. This took months. But we got it done.

## What I Built

### StoryBlok Migration (3 months)

Transitioned the legacy article system to StoryBlok, a modern headless CMS.

**Results:**
- Article production time cut in half
- Rich text formatting finally available
- Better UX for readers
- News team stopped complaining

### CoTA Data Integration

Despite the bureaucratic obstacles, got the cruise data pipeline working again.

**Results:**
- Increased cruise traffic on the main TripAdvisor site
- Data flowing reliably via the convoluted CSV → ingester → Java module path

## The Vision That Was "The Worst Idea Ever"

In 2023, the company held an offsite. The prompt: **"If you could envision the future of the Cruise Critic website, what would it look like?"**

Most people mocked up updated versions of the current site. New colors, better layouts, same structure.

I had been playing with ChatGPT. I could see where AI was going.

**My pitch:**

Imagine we have nothing on the page. Just a text prompt.

An animated character — the "Cruise Director" — asks: *"Where do you want to go? Tell me about your vacation."*

As the user types, we use AI to search our articles and content dynamically. Instead of a static magazine-style homepage, we build the page around their input in real time.

User mentions Barbados? Pinterest-style cards fly in:
- "Places to eat in Barbados"
- "10 things to avoid when traveling to the Caribbean"  
- "First-time cruiser tips"

We pull social data to personalize further. Is this a mom? Surface family content. Honeymoon keywords? Romantic destinations.

This was RAG before RAG was a term. This was conversational search before Google launched AI Mode.

**The response:** "The worst idea ever."

Two years later, Google rebuilt their homepage around exactly this concept.

## The End

In August 2023, TripAdvisor replaced the CEO, CFO, and CMO simultaneously.

The new leadership cut over 300 people. I was one of them.

The company has been on a downward spiral since.

## Technical Stack Summary

**Frontend:**
- React
- GraphQL

**Backend:**
- Legacy PHP (bespoke admin system)
- Java microservices
- C# services (mixed architecture)

**Content:**
- StoryBlok (headless CMS)
- Legacy article system (sunset)

**Data:**
- CSV export pipeline (CoTA)
- Custom Java ingestion module
- TripAdvisor primary database integration

## Lessons

1. **Sometimes the obstacle is organizational, not technical.** A REST API would have been cleaner. Politics made us build a CSV pipeline instead.

2. **Legacy migrations are thankless but necessary.** The StoryBlok migration wasn't glamorous. It just made everyone's life better.

3. **Being early is the same as being wrong — until it isn't.** My "worst idea ever" became Google's 2025 homepage redesign.

4. **Leadership changes reset everything.** New C-suite, new priorities, new layoffs. Doesn't matter what you built.

5. **Stay connected to good people.** Jim got me in the door. We still talk every week. Relationships outlast jobs.

---

*Wayne Renbjor (Wren.AI) — Solutions Architect, 18+ years*
[LinkedIn](https://linkedin.com/in/wrenbjor) | [GitHub](https://github.com/wrenbjor) | [Twitter/X](https://x.com/wren_ai) | [Tiktok](https://tiktok.com/@wren.ai)