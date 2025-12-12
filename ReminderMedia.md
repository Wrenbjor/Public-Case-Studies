# ReminderMedia: Building a $28M Platform From the Ashes

## The Situation

**Date:** February 2016  
**Role:** Software Development Lead / IT Director  
**Company:** ReminderMedia — a print magazine marketing company serving real estate agents and small businesses

I was hired to "help lead a software team." What I walked into was a political coup.

My presence was orchestrated to remove the existing VP of IT. Day one came with inherited tension, a dev team of six in a windowless room, and a CEO, Steven Acree, so toxic he had parked his desk directly outside the dev room to monitor them.

His first request: install keyloggers to count how many times per day developers were committing code.

I told him that was a poor way to measure productivity. By day five, I had to demand he return to his original office and give me space to work with the team.

## The Crisis

Within one week of starting, almost the entire development team quit simultaneously.

They had followed the previous VP to his new company.

I now had:
- **No team**
- A legacy system built on XRMS — an open-source platform that died in 2008
- **5-hour deployment times** due to test bloat (15-20 tests for 5-line functions, tests nested inside tests asserting that other tests asserted true)
- A deadline of **6 months** to build a digital magazine platform from scratch
- 300 PCs requiring desktop attrition planning
- A CEO who wanted keyloggers

## The Legacy Nightmare

The entire business ran on XRMS. Thousands of print magazines shipped monthly. Clients customized front covers, back covers, inside and outside spreads. Everything funneled to a ProStream print system.

The codebase was untouchable. A single developer had instituted a testing regime so extreme that simple changes took multiple days. Deployment was a 5+ hour process. If something broke in production after all those tests passed, you were looking at another 5+ hours minimum before a fix could go live.

I was originally told to build the new digital product inside XRMS.

I refused.

## The Greenfield Decision

I convinced the C-suite to let me build greenfield. New architecture. New stack. Clean separation from the legacy system.

They agreed, but the deadline stayed: **6 months.**

It took 10.

Not because of technical complexity. Because the CEO couldn't stop interfering. He would go around the PM and assign work directly to developers. He undermined every process I tried to implement. Priorities shifted weekly based on his whims.

Despite the chaos, we delivered.

So I began simultaneously:
1. Rebuilding the entire development team from scratch
2. Interviewing stakeholders across the company to define requirements
3. Designing the platform architecture
4. Managing IT infrastructure for 300+ employees

## What We Built

### Platform Architecture

- **7 microservices** with full API design and state flow diagrams
- **Laravel 5** backend (learned its new internal architecture on the fly)
- **JWT token authentication** 
- **Custom magazine renderer** — a FusionPro replacement built in Python using ImageMagick
- **October CMS** with a custom plugin for magazine display and client self-service
- **Contact management service** for tracking subscriber behavior
- **Email service** wrapping Campaigner's API (their UI couldn't handle sub-client email workflows)
- **Tracking pixel system** for email engagement analytics

### Infrastructure

- **2-petabyte storage array** with 10G fiber backbone for the Digital Asset Management system
- **BIND** for internal DNS
- **Traefik** for routing
- **Docker containers** deployed via **Ansible** through **GitLab CI**
- **Blue/green deployment** with round-robin switching — zero downtime releases

This was critical. With the legacy system, a failed deployment meant 5+ hours of downtime. With blue/green, we could deploy, validate, and roll back in minutes if needed.

### Legacy System Rehabilitation

I made it a mandate: for every new feature built into XRMS, developers were required to cut dead tests.

**Over one year:**
- Removed **15,000+ useless tests**
- Reduced deployment time from **5 hours to under 30 minutes**

## The Results (Year One)

| Metric | Result |
|--------|--------|
| **Revenue added** | $28 million |
| **Magazine visits** | 4+ million |
| **Emails sent** | 1+ million |
| **Cloud costs** | $0 (entirely self-hosted) |
| **Deployment downtime** | Zero (blue/green) |

Additional capabilities delivered:
- Blog branding system
- Social media post management
- Full client self-service for magazine customization

## The End

Throughout my tenure, I held the line between an unrealistic, toxic CEO and a team trying to do good work.

After delivering:
- A fully functional development team
- A QA team
- Automated deployment infrastructure
- A platform generating $28M annually

...I was secretly replaced.

A consultant was brought in under the same pretense I had been — unaware he was there to take over. After I was let go, he discovered what had happened and also left.

They were left without leadership. The same pattern they used on the previous VP, they used on me.

## Technical Stack Summary

**Backend:**
- Laravel 5 (PHP)
- Python (ImageMagick integration)
- 7 microservices architecture

**Frontend:**
- October CMS
- Custom plugin development

**Infrastructure:**
- Docker containers
- GitLab CI/CD
- Ansible automation
- Traefik (routing)
- BIND (DNS)
- 2PB storage array
- 10G fiber backbone

**Integrations:**
- Campaigner API (email)
- ProStream (print fulfillment)
- XRMS (legacy system mapping)

**DevOps:**
- Blue/green deployment
- Zero-downtime releases
- Automated testing pipeline

## Lessons

1. **Politics will kill good work.** Building something excellent doesn't protect you from organizational dysfunction.

2. **Greenfield isn't always a luxury — sometimes it's survival.** Convincing leadership to let me build new instead of patching the old was the decision that made everything else possible.

3. **Test discipline matters, but test theater is debt.** 15,000 deleted tests. Not one of them was catching real bugs.

4. **Protect the team.** They're the ones doing the work. A leader's job is to give them space to do it.

5. **Document everything.** When you leave — voluntarily or not — the work should speak for itself.

---

*Wayne Renbjor (Wren.AI) — Solutions Architect, 18+ years*
[LinkedIn](https://linkedin.com/in/wrenbjor) | [GitHub](https://github.com/wrenbjor) | [Twitter/X](https://x.com/wren_ai) | [Tiktok](https://tiktok.com/@wren.ai)