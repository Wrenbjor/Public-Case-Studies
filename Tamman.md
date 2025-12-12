# Tamman: Building an Accessibility Powerhouse (Then Paying for a CEO Who Couldn't Keep Up)

## The Situation

**Date:** June 2018 - February 2020  
**Role:** Director of Development  
**Company:** Tamman — a Philadelphia-based agency specializing in web accessibility

By now I had a following. Developers who'd worked with me at Comcast followed me to ReminderMedia. Developers from ReminderMedia followed me to Tamman. Three of them made the jump with me this time.

This wasn't accidental. I'm fiercely loyal to my people. I protect them from bad management, fight for their growth, and give them space to do good work. In return, they follow me from company to company.

Tamman's founders — Jeff Tamborino and Michael Mangos — had built a respected accessibility-focused agency. Their main contract was with Bank of America, subcontracted through the bank's internal agency, ECS. They also had a SaaS product called SyncScripts.

Mike told me directly: **"We need to diversify beyond the bank. Help us bring in new business."**

That's what I was hired to do.

## The Team

When I arrived, the team was 6 developers and 1 QA. The lead dev, Joe Wollard, was already burnt out — one foot out the door. I supported him, pushed back against Mike's outdated approaches alongside him, but I was really just delaying his exit. I think he wanted to make sure the team would be in good hands before he left.

When Joe moved on, I brought in a senior developer who'd followed me from Comcast to ReminderMedia to Tamman. The cult continued.

## The Chaos I Inherited

Everything was manual.

The agency had an on-prem Proxmox cluster running GitLab, but the deployment process was:

1. Developer pushes code
2. Developer logs into GitLab manually to get PR link
3. Developer pastes link into Slack
4. Senior dev reviews and merges
5. Senior dev deploys via FTP/SSH by hand

Every. Single. Time.

## What I Built

### DevOps Automation

Implemented GitLab Runners and Ansible to automate the entire pipeline.

When a developer pushed code:
- System automatically built a test environment based on the ticket number
- Example: `bamf-10293.tamman.net`
- Launched a new Docker build on a Proxmox Linux guest
- Updated BIND (DNS) and Traefik (routing) automatically
- Anyone internal could now test a live page instantly

No more manual deploys. No more Slack links. No more FTP.

### Accessibility QA Automation

As we clamped down harder on WCAG compliance, I brought in my QA lead from ReminderMedia.

He built a custom automation framework using PHP and Codeception that:
- Ran spell checks and accessibility validations
- Integrated AXE and Lighthouse
- **Turned the entire WCAG 2.1 checklist into automated tests**

We weren't just checking boxes. We were programmatically verifying accessibility compliance before anything went live.

### Team Scale

Grew the team to **7 developers and 2 QA**.

Output: **8-10 landing pages or custom experiences every sprint** (two weeks).

We were a machine.

## The Work (That Won Awards We Never Got Credit For)

Bank of America had a strict rule for subcontractors: **no database access**.

So I devised a system using JSON files as pseudo-relational tables. Multiple JSON files cross-referenced each other. We even built admin interfaces that let bank employees update the data — all without touching a database.

### Merrill Lynch GFX Platform

A graphical Global Foreign Exchange platform. Interactive world map. Click a country to see:
- Flag and currency
- Exchange rates
- Transfer protocols (SWIFT, Wire, etc.)
- Country statistics

All powered by JSON. No database. Won awards for ECS (the bank's internal agency). Tamman's name appeared nowhere.

### Heritage Mortgage Timeline

"100 Years of Banking with Heritage" — a visual timeline interface.

Modeled after the original iTunes album cover flow. Swipe left or right, images ease in with information below. Smooth, polished, fully accessible.

No database. React, JavaScript, JSON.

### Banking & Finance 101

An animated educational course. Each page featured CSS animations — clouds floating, people walking, interactive elements throughout.

Built to teach financial literacy. Fully WCAG compliant.

### Susan G. Komen Pages

All of them. Every campaign page for the bank's Komen partnership.

### Cash Back Campaign Pages

The 1%, 2%, 3% cash back promotional pages. All of them.

### The Design System

I moved the team from rebuilding the same code every project to maintaining a **full design system**.

React components built **accessible-first**. When we moved them between pages, they just worked. No retrofitting. No accessibility audits after the fact.

## The Tension

I was hired to diversify. Instead, I made Bank of America look incredible.

Every new client I brought in, Mike found a way to not close the deal. I think he was scared to actually diversify. The bank was safe. The bank was predictable.

Meanwhile, I was pushing the team forward:
- Learning Flutter (write once, deploy to web + iOS + Android)
- Advocating for remote work (this was 2019)

Mike called Flutter "Flubber." He never paid attention to what it could do.

## The End

**February 2020.**

I forced one week of mandatory remote work as a test. Just to prove we could do it.

Mike exploded.

"How dare you just allow everyone to be remote? What got dropped?"

"Nothing got dropped."

"That's not the point. You waste time on the Flubber thing, you force devs remote... I don't see how we can keep working together."

He let me go.

**Three weeks later, COVID hit.**

The entire world went remote. The team I'd prepared was ready. Mike had to eat crow.

**Three months after that**, Mike asked the team: "Hey, what's this Flutter thing getting traction?"

One of my developers — one of the cult — replied:

"That's the thing you let Wayne go over. He built a sample app he wanted to show you and the bank. We could write one codebase and deploy to web and both mobile platforms."

Mike turned red and ended the meeting.

## Technical Stack Summary

**DevOps:**
- GitLab Runners
- Ansible automation
- Docker containers
- Proxmox virtualization
- BIND (DNS)
- Traefik (routing)
- Dynamic per-ticket test environments

**Frontend:**
- React
- JavaScript
- CSS animations
- JSON as pseudo-database
- Accessible-first component design system

**QA:**
- PHP / Codeception
- AXE integration
- Lighthouse integration
- Custom WCAG 2.1 automated test suite

**Accessibility:**
- WCAG 2.1 AA compliance
- Automated accessibility testing
- Design system with accessibility baked in

## Lessons

1. **You can pay for someone else's inability to adapt.** I was right about Flutter. I was right about remote work. Mike couldn't keep up, and I paid the price.

2. **Politics beats competence.** Mike didn't want to diversify. He wanted to say he wanted to diversify.

3. **Your people are your reputation.** The developers who follow you from company to company are proof that you're worth following.

4. **Prepare for the future anyway.** The remote work test I got fired for running saved the team three weeks later.

5. **Neophytes eventually catch up — after you've paid the price.** Mike eventually asked about Flutter. By then, I was gone.

---

*Wayne Renbjor (Wren.AI) — Solutions Architect, 18+ years*
[LinkedIn](https://linkedin.com/in/wrenbjor) | [GitHub](https://github.com/wrenbjor) | [Twitter/X](https://x.com/wren_ai) | [Tiktok](https://tiktok.com/@wren.ai)