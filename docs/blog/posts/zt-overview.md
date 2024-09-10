---
#draft: true
date: 2024-09-010
authors:
  - mnye
categories:
  - Zero Trust
  - Cloud Security
  - Security Architecture
  - NIST
  - CISA
---

# Demistifying Zero Trust

Attackers have a strategy, they have a plan.  We know what they are going to be doing, we have modeled these behaviors with MITRE ATTACK and the Killchain concept.  But we know how we traditionally have started to design from the outside, trying to keep them out.  This model, Zero Trust, is all about trying to address the adversary that is already on the network, because we know that's what is happening.

<!-- more -->
Many people skeptical of zero trust or they will equate it to marketing. And what they are reacting to is a lot of the hype around zero trust that came because the original zero trust papers lived behind a paywall at Forrester, which is a research firm, and many practitioners were not necessarily clients with Forrester but every vendor was.  So every vendor would be talking about zero trust and that’s how many practitioners saw zero trust was through the stain-glassed windows of some vendor marketing.  So they came to equivocate it with that.

## Zero Trust Definition

Forrester defines Zero Trust as a security model that assumes nothing is inherently trusted and instead verifies everything that attempts to access sensitive resources. Zero Trust is based on the principle of "never trust, always verify".

## Core Tenets of Zero Trust

These are the tenets from the NIST special publication on Zero Trust Architecture.  These tenets mirror a lot of the key concepts from the definition above: least privilege, per-session, dynamic, strong authentication and authorization, telemetry, etc.

![NIST Logo](https://github.com/mnyethecyberguy/storm/blob/gh-pages/assets/images/nist.png)

**NIST SP 800-207 Tenets of Zero Trust:**[^1]
- All data sources and computing services are considered resources
- All communication is secured, regardless of network location
- Access to individual enterprise resources is granted on a per-session basis
- Access to resources is determined by dynamic policy, including the observable state of client identity, application and the requesting asset, and it may include other behavioral and environmental attributes
- The enterprise monitors and measures the integrity and security posture of all owned and associated assets
- All resource authentication and authorization is dynamic and strictly enforced before access is allowed
- The enterprise collects as much information as possible about the current state of the network infrastructure and communications and uses it to improve its security posture

800-207 is a descriptive document, not prescriptive.  So it has definitions, tenets, and observed approaches, and details architectural components which we'll get to in a little bit.

## Zero Trust Maturity Models


## Zero Trust Architecture


## Zero Trust Terminology


## Why Zero Trust?


## Additional References

[^1]: “The Definition of Modern Zero Trust”, Forrester (2022)
[^2]: 
[^3]: 
[^4]: 
[^5]: 