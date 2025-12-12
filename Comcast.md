# Comcast CRAN Engineering: The Platform That Outperformed Cisco Prime

## The Situation

**Date:** 2008-2015  
**Role:** Developer → Platform Architect  
**Company:** Comcast — CRAN (Cable Regional Area Network) Engineering

I started on the IT helpdesk. Built tools for project managers. When Gary came in as the new CRAN Director, he hired me to reverse-engineer Tableau for the data team. After automating that, I got a directive that would change everything:

**"Go find problems and fix them."**

I spent three weeks embedded with network engineers. What I found was chaos.

## The Problem

Comcast network engineering operated across **27 regions**. Each region maintained its own spreadsheet for network inventory:
- Devices
- Chassis
- Interfaces  
- IP allocations

**All 27 used different formats.**

The result: approximately **60% of Cisco and Juniper configurations deployed with errors**.
- Duplicate IPs
- Interface conflicts
- Stale data

These weren't theoretical problems. They caused **customer-facing outages**. Repeatedly.

## The Discovery

The root cause was inventory drift. Engineers were working from spreadsheets that didn't reflect reality. By the time a config was generated, deployed, and tested, the underlying data had already changed.

There was no single source of truth. No validation. No reconciliation.

Every deployment was a gamble.

## The Solution

### Phase 1: Standardization (6 weeks)

Consolidated all 27 regions to a single spreadsheet format. This alone was a political achievement — getting 27 regional teams to agree on anything.

### Phase 2: The Platform (3 weeks coordination + ongoing development)

Built a centralized inventory and configuration platform.

**Technical Stack:**
- **PHP API** (Zend Framework, started on PHP 4.2, evolved to 5.6)
- **MySQL database** mirroring the inventory hierarchy
- **Python 2.7** discovery engine
- **Template library** for 9 service types (VOD, CMTS, BGP, etc.)
- **BT/Diamond IPAM integration** for IP delegation
- **Cisco/Juniper config generation** with SMOP documentation

### The Discovery Engine

This was the core innovation.

- Connected to **~20,000 devices nightly** via SSH/Telnet
- Regex parsing of running configs
- Automated inventory reconciliation
- Cross-referenced what the database *thought* was deployed vs. what was *actually* deployed

**The Rate Limit Problem:**

RADIUS authentication limited us to 3 connections per second per account. At 20,000 devices, that was untenable.

Solution: Built a round-robin system across 15 service accounts. Parallelized the discovery. Hit every device every night.

## The Results

| Metric | Before | After |
|--------|--------|-------|
| **Config error rate** | ~60% | <3% |
| **Time saved** | — | ~150 man-hours/month |
| **Revenue protected** | — | Millions (prevented outage costs) |

### What This Enabled

- **VOD service expansion** — previously too unstable to scale
- **Netflix/Akamai/Comcast integration** — movie covers on set-top boxes
- **Reliable network growth** — new regions could onboard in days, not months

### Team Growth

Started as a solo developer at a helpdesk desk.

By the time I left: **60 people** on the platform team.

## The Kill Shot

Gary left in 2012. New director wanted offshore outsourcing.

Meanwhile, Cisco was selling **Cisco Prime** to Comcast as the enterprise network management solution.

**My platform outperformed Cisco Prime significantly.**

We began talks with Tail-F for a hybrid integration — best of both worlds. Then Cisco acquired Tail-F. Product dissolved.

The political calculus shifted. A homegrown platform outperforming a major vendor product wasn't an asset anymore. It was a liability.

**The deal was struck:** The entire department — approximately 300 people — was eliminated. Justified as "redundant to incoming Cisco Prime deployment."

A platform I built from a helpdesk desk in 2008 outperformed the vendor solution enough to become a political problem.

## Technical Stack Summary

**Backend:**
- PHP (Zend Framework)
- Python 2.7

**Database:**
- MySQL

**Discovery:**
- SSH/Telnet automation
- RADIUS authentication (round-robin across 15 accounts)
- Regex config parsing

**Integrations:**
- Cisco device management
- Juniper device management
- BT/Diamond IPAM
- SMOP documentation generation

**Scale:**
- ~20,000 devices
- 27 regions consolidated
- 9 service type templates

## Lessons

1. **Technical excellence doesn't protect you from politics.** The better the platform performed, the bigger the target it became.

2. **Discovery is everything.** A database is only as good as its reconciliation with reality. Nightly automated discovery was the foundation everything else stood on.

3. **Standardization before automation.** The 6 weeks spent getting 27 regions on the same spreadsheet format made everything after possible.

4. **Build for the problem you find, not the one you're told.** I was told to reverse-engineer Tableau. I found a 60% config error rate. I fixed that instead.

5. **Vendors aren't always better — but they're always political.** Cisco Prime was the "safe" choice even when it was the wrong choice.

---

*Wayne Renbjor (Wren.AI) — Solutions Architect, 18+ years*
[LinkedIn](https://linkedin.com/in/wrenbjor) | [GitHub](https://github.com/wrenbjor) | [Twitter/X](https://x.com/wren_ai) | [Tiktok](https://tiktok.com/@wren.ai)