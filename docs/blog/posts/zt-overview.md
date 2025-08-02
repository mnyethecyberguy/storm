---
#draft: true
date: 2024-09-10
authors:
  - mnye
categories:
  - Zero Trust
  - Security Architecture
tags:
  - Zero Trust
  - Security Architecture
---

# From A to ZTA: Understanding Zero Trust

Attackers have a strategy, they have a plan.  We know what they are going to be doing, we have modeled these behaviors with MITRE ATTACK and the Killchain concept.  But we know how we traditionally have started to design from the outside, trying to keep them out.  This model, Zero Trust, is all about trying to address the adversary that is already on the network, because we know that's what is happening.

<!-- more -->
Many people are skeptical of zero trust or they will equate it to marketing. And what they are reacting to is a lot of the hype around zero trust that came because the original zero trust papers lived behind a paywall at Forrester, which is a research firm.  Many practitioners were not necessarily clients with Forrester, but every vendor was.  So every vendor would be talking about zero trust and that’s how many practitioners saw zero trust was through the stain-glassed windows of some vendor marketing.

Zero trust is a heavy topic, and I will do my best to breakthrough some of those stereotypes and misconceptions in this article.

## Zero Trust Definition

With any Zero Trust discussion, we need to start by getting the concepts and terminology under our belts so that we are all speaking the same language.

Forrester defines Zero Trust as:[^1]

> Zero Trust is an information security model that denies access to applications and data by default. Threat prevention is achieved by only granting access to networks and workloads utilizing policy informed by continuous, contextual, risk-based verification across users and their associated devices. Zero Trust advocates these three core principles: All entities are untrusted by default; least privilege access is enforced; and comprehensive security monitoring is implemented.

This definition as a security model is critical.  Zero Trust is not a product.  Rather it is a paradigm, or a collection of concepts and ideas to minimize uncertainty in a hostile network.  No single product or vendor will make you "Zero Trust" regardless of what their sales team tells you.

Zero Trust is based on the principle of "never trust, always verify", and aims to solve the inherent problems in placing trust in the network.  

## Core Tenets of Zero Trust

These are the tenets from the NIST special publication on Zero Trust Architecture.  These tenets mirror a lot of the key concepts from the definition above: least privilege, per-session, dynamic, strong authentication and authorization, telemetry, etc.  If you have not done so, I would strongly recommend familiarizing yourself with the concepts in this document.

![NIST Logo](../../assets/images/nist.png)

**NIST SP 800-207 Tenets of Zero Trust:**[^2]

- All data sources and computing services are considered **resources**
- All **communication is secured**, regardless of network location
- Access to individual enterprise resources is granted on a **per-session basis**
- Access to resources is determined by **dynamic policy**, including the **observable state** of client identity, application and the requesting asset, and it may include other behavioral and environmental attributes
- The enterprise monitors and measures the integrity and **security posture** of all owned and associated assets
- All resource **authentication** and **authorization** is dynamic and strictly **enforced before** access is allowed
- The enterprise collects **as much information as possible** about the current state of the network infrastructure and communications and uses it to improve its security posture

800-207 is a descriptive document, not prescriptive.  So it has definitions, tenets, and observed approaches, and details architectural components which we'll get to in a little bit.

## Zero Trust Maturity Models

Because Zero Trust is a strategic approach to cybersecurity, using a maturity model is a logical and effective way for organizations to assess their progress in adopting and implementing its principles. Maturity models aim to assist in the development of zero trust strategies and implementation plans, guiding resource allocation and prioritization, and promoting continuous improvement. Most maturity models for Zero Trust are broken down into 5 or 7 pillars, depending on whose model you are looking at.  

### CISA's Zero Trust Maturity Model (ZTMMv2)

CISA's Zero Trust Maturity Model (ZTMM)[^3], which includes five pillars and three cross-cutting capabilities, is based on the foundations of zero trust. Within each pillar, the maturity model provides specific examples of Traditional, Initial, Advanced, and Optimal zero trust architectures.

![CISA ZTMM](../../assets/images/zt-cisa-ztmm.png)

The 5 pillars here are: Identity, Devices, Networks, Applications & Workloads, and Data.  

- **Identity**: Focusing on user access management, continuous validation, and behavioral analysis.
- **Devices**: Inventorying, monitoring, and managing the security posture of all devices accessing the network.
- **Networks**: Securing communication regardless of location, with a focus on microsegmentation and encryption.
- **Applications and Workloads**: Securing access to and within applications and services, both on-premises and in the cloud.
- **Data**: Classifying, protecting, and monitoring sensitive data regardless of where it resides.

In the CISA model, you will see that Visibility and Analytics, Automation and Orchestration, and Governance are the foundation of the pillars, or "cross-cutting" capabilities of the pillars.  These capabilities enhance interoperability and effectiveness.

- **Visibility and Analytics**: Gaining insights into network activity, user behavior, and system performance.
- **Automation and Orchestration**: Automating processes and orchestrating responses to security incidents.
- **Governance**: Establishing and enforcing policies for Zero Trust implementation and compliance. 

Some other models will have these foundational layers pulled up as pillars, but these are the core competencies of Zero Trust and are critical when trying to improve maturity of your Zero Trust Architectures.

## Zero Trust Architecture

Analyzing the NIST NCCoE publication *Implementing a Zero Trust Architecture*[^4], we see a high-level representation of the logical components of a ZTA illustrated.  This diagram also shows the slicing between the control plane and data plane.

![Zero Trust Architecture Logical Components](../../assets/images/zt-arch-logical.png) 

In this graphic, we see the core components of the Policy Decision Point and Policy Enforcement Point, and then on the left we have functional components, which are really just different data sources or feeds that support the policy engine.

### Deployed Variations of the Abstract Architecture

### Device Agent/Gateway-Based

### Enclave-Based

### Resource Portal-Based

### 

## Zero Trust Terminology

`Policy Decision Point (PDP)`

: The Policy Engine, which is considered the Policy Decision Point, is responsible for the decision to grant access to a resource for a given subject.

`Policy Enforcement Point (PEP)`

: Responsible for enabling, monitoring, and eventually terminating connections between a subject and a resource.

`Policy Information Point (PIP)`

: An access control mechanism component that provides telemetry and other information generated by policy or collected by supporting components that the PDP needs for making policy decisions.

`Subject`

: A combination of user, application, service, and device. The thing that is going to be accessing, or requesting access to something else.

`Action`

: Granting, denying, or revoking access to a resource. This is where the Policy Enforcement Points are actually controlling the access. Allowing, and in some cases brokering, or restricting the access.

`Resource`

: All enterprise assets including data, services, applications, compute resources, virtual and cloud components. The things a subject is trying to access.

## Zero Trust Landscape

The products and solutions used to implement Zero Trust will vary based on the needs of your organizaton, your use cases, and data paths.  Users accessing resources in an on-premise datacenter would have a different data path than a service-to-service access architecture.  

## Defining the Zero Trust Protect Surface


## Additional References

[^1]:
    “The Definition of Modern Zero Trust”, David Holmes, Forrester (2022). <https://www.forrester.com/blogs/the-definition-of-modern-zero-trust/>
[^2]:
    NIST Special Publication 800-207: Zero Trust Architecture (2020). <https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-207.pdf>
[^3]:
    Zero Trust Maturity Model, Version 2.0.  CISA (2023). <https://www.cisa.gov/sites/default/files/2023-04/zero_trust_maturity_model_v2_508.pdf>
[^4]:
    Implementing a Zero Trust Architecture, NIST NCCoE (2020). <https://www.nccoe.nist.gov/sites/default/files/legacy-files/zta-project-description-final.pdf>
[^5]:
    NSTAC Report to the President on Zero Trust and Trusted Identity Management (2022). <https://www.cisa.gov/sites/default/files/publications/NSTAC%20Report%20to%20the%20President%20on%20Zero%20Trust%20and%20Trusted%20Identity%20Management.pdf>
[^6]:
    CSA Defining the Zero Trust Protect Surface (2024). <https://cloudsecurityalliance.org/artifacts/defining-the-zero-trust-protect-surface>
    