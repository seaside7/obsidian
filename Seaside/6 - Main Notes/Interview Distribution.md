
## 🧩 What does Distribusion do? (Simple explanation)

Distribusion Technologies GmbH is a **B2B travel technology company** that helps **ground transportation providers** (buses, trains, ferries) **sell their tickets digitally** across many global distribution channels.

In short:

> **Distribusion connects transport operators to the world’s travel platforms via APIs.**

---

## 🏗️ The core problem they solve

Many bus / rail / ferry operators:

- Still use **legacy systems**
    
- Don’t have modern APIs
    
- Can’t easily sell tickets on platforms like:
    
    - Booking.com
        
    - Expedia
        
    - Trainline
        
    - Omio
        
    - Corporate travel tools
        

Distribusion acts as a **technical bridge**.

---

## 🔌 How their platform works (important for TPM role)

### 1️⃣ Supply side (operators)

- Bus, rail, ferry companies connect **once** to Distribusion
    
- Distribusion handles:
    
    - Inventory
        
    - Pricing
        
    - Schedules
        
    - Availability
        
    - Ticketing rules

are the suppliers is using their system or using distribution supply system? like reddoorz 

### 2️⃣ Distribusion API (the core product)

- Normalizes **many different transport systems** into **one unified API**
    
- Handles:
    
    - Real-time availability
        
    - Booking & ticket issuance
        
    - Cancellations & changes
        
    - Settlement & reporting
        

This is where **API integrations & technical product management** are critical.

### 3️⃣ Demand side (partners)

- Online travel agencies (OTAs)
    
- Meta-search engines
    
- Corporate travel platforms
    
- Mobility-as-a-Service (MaaS) apps
    

They integrate **once** and get access to **hundreds of transport providers globally**.

---

## 💼 How Distribusion makes money

Primarily:

- **Commission per ticket sold**
    
- B2B platform fees
    
- Enterprise partnerships
    

No consumer app — they are **pure B2B infrastructure**.

---

## 🌍 Why they are strong as a business

You can safely say:

- Global footprint (Europe, LATAM, Asia)
    
- Strong network effects (more operators ↔ more channels)
    
- Mission-critical APIs (downtime = lost revenue)
    
- High switching costs once integrated
    
- Clear focus on **scalable platform architecture**
    

---

## 🎯 Why YOUR background fits (talking point)

This aligns perfectly with your experience in:

- API platforms (Finantier)
    
- Complex integrations
    
- Data-heavy systems
    
- Multi-stakeholder environments
    
- Technical + product bridge roles
    

You can say something like:

> “Distribusion reminds me of large-scale platform products I’ve worked on, where the main challenge is standardizing complex systems into reliable APIs that many partners depend on.”

---


# 1️⃣ RedDoorz — API integrations with multiple OTAs

_(Travel distribution story → very relevant to Distribusion)_

### How to frame it (30–60 seconds)

> At **RedDoorz**, I owned product strategy and delivery for integrations between our internal systems and multiple OTA partners such as **Traveloka**, **Booking.com**, and **tiket.com**.
> 
> Each partner had different API capabilities, data models, and operational constraints. My role was to define a standardized internal contract for inventory, pricing, availability, and booking flows, while allowing partner-specific adaptations without fragmenting the core platform.

### Go slightly deeper (if they ask “how?”)

**Key challenges you handled:**

- Different OTA expectations for:
    
    - Availability updates
        
    - Pricing rules
        
    - Cancellation / refund logic
        
- Rate limits & sync frequency
    
- Inconsistent error handling
    

**Your approach (TPM-style):**

> I worked with engineering to define a stable internal API contract and treated each OTA as a “channel adapter” rather than a custom build. We prioritized backward compatibility, clear versioning, and operational visibility so issues could be diagnosed quickly without breaking other integrations.


# 2️⃣ Finantier — Credit scoring platform for many fintech clients

_(API + data platform story → shows depth)_

### How to frame it (30–60 seconds)

> At **Finantier**, I led the product development of a credit scoring platform that served multiple fintech and lending partners. The system consumed transaction-level data from different sources and transformed it into standardized risk and behavioral signals that clients could integrate via APIs.

### What makes this relevant

- Multi-tenant platform
    
- Data normalization
    
- External consumers depending on your API

### The real TPM value you add (important)

**Core problem you solved:**

- Every fintech wanted:
    
    - Different scoring logic
        
    - Different thresholds
        
    - Different data visibility
        

**Your product decision:**

> Instead of building custom scoring logic per client, we created a configurable scoring framework with a shared core model and client-specific parameters. This allowed us to scale integrations without increasing operational complexity or technical debt.

That sentence alone is **gold** for a platform interview.


# 3️⃣ How to connect BOTH stories to Distribusion (say this explicitly)

If they ask _“How does your past experience relate to this role?”_, use this:

> What excites me about Distribusion is that the core challenge is very familiar to me: connecting many external partners through a stable, well-designed API while managing complexity behind the scenes. At RedDoorz, this was OTAs; at Finantier, fintech clients. The domain is different, but the product and platform problems are fundamentally the same.


## What is API fragmentation? (simple definition)

**API fragmentation** happens when an API loses its consistency because **too many special cases, custom behaviors, or incompatible versions** are added over time.


## 🧠 What Cuong will likely ask you

Be ready for:

- Why Distribusion?
    
- Experience with APIs / integrations
    
- Working with external partners
    
- Handling trade-offs between flexibility vs standardization
    
- Technical communication with engineers
    

---

## ✅ Next step (I recommend)

If you want, next I can:

- Draft **your answer to “Why Distribusion?”**
    
- Prepare **API-integration interview questions**
    
- Simulate the **30-minute call** (realistic)
    
- Help you prepare **questions to ask Cuong** (very important)
    


Distribusion stands out to me as a true infrastructure platform. I’m drawn to products where APIs are the core business, not just an implementation detail. The challenges around large-scale integrations, data consistency, and reliability across global partners are very similar to platforms I’ve worked on before, just in a different domain. I’m excited by the opportunity to work on a system that directly enables global mobility at scale.


Great — this is exactly the right thing to prepare for **Distribusion**.

Below is a **realistic API-integration interview pack**, based on what **Technical Product Managers** are actually asked (not coding questions, but **system + judgment questions**).

I’ll show you:

1. What these questions **look like**
    
2. What interviewers are **really testing**
    
3. **Model answers** you can adapt (not memorize)
    

---

# 🧩 What API-integration interviews are like (important)

They are **NOT** testing:

- Syntax
    
- Coding
    
- Framework knowledge
    

They **ARE** testing:

- System thinking
    
- Trade-offs
    
- Scalability
    
- Partner empathy
    
- Risk management
    

Think **“platform owner mindset.”**

---

# 1️⃣ Core API Integration Questions (VERY COMMON)

### ❓ “How do you design an API that many partners integrate with?”

**What they want to hear:**

- Consistency
    
- Stability
    
- Backward compatibility
    

**Strong answer:**

> I start by defining a clear core contract that covers the most common use cases. I prioritize stability and backward compatibility, and treat the API as a long-term product. Partner-specific needs are handled through configuration or extensions rather than changing the core behavior.

---

### ❓ “How do you handle partners with very different capabilities?”

**What they’re testing:** standardization vs flexibility

**Strong answer:**

> I try to normalize as much as possible internally, so partners interact with a consistent interface. When partners have limitations, we adapt internally through adapters or transformation layers instead of exposing complexity in the API.

---

# 2️⃣ Versioning & Breaking Changes (they LOVE this)

### ❓ “How do you manage API versioning?”

**Good TPM answer:**

> I treat versioning as a communication problem as much as a technical one. We minimize breaking changes, introduce new versions only when necessary, provide clear deprecation timelines, and support parallel versions long enough for partners to migrate safely.

🚩 Red flag if someone says “just release v2 and move on”.

---

### ❓ “What do you do when a breaking change is unavoidable?”

**Strong answer:**

> I make the trade-off explicit, document the impact clearly, communicate early, and work with partners on migration plans. The goal is to protect trust, even if change is necessary.

---

# 3️⃣ Error Handling & Reliability (very relevant for Distribusion)

### ❓ “How should APIs handle errors for external partners?”

**What they want:**

- Predictability
    
- Debuggability
    

**Strong answer:**

> Errors should be consistent, well-structured, and actionable. Partners should be able to understand whether an issue is temporary, permanent, or due to invalid input, without needing internal context.

---

### ❓ “What happens if one partner sends bad data?”

**Strong answer:**

> The platform should be resilient by isolating failures. One partner’s issues should not impact others, and validation should happen as early as possible to prevent bad data from propagating.

---

# 4️⃣ Rate Limits, Performance & Scale

### ❓ “How do you think about rate limiting?”

**Good answer:**

> Rate limits protect platform stability. I see them as part of the product contract, not just a technical safeguard. Limits should be documented, predictable, and aligned with partner usage patterns.

---

### ❓ “How do you balance performance vs data freshness?”

**Strong answer:**

> It depends on use cases. For search and availability, freshness matters more; for reporting, latency is acceptable. My role is to help make these trade-offs explicit so expectations are aligned.

---

# 5️⃣ Partner Requests & API Fragmentation (VERY IMPORTANT)

### ❓ “A partner asks for custom behavior — what do you do?”

**What they’re testing:** governance

**Strong answer:**

> I evaluate whether the request represents a common future need or a one-off. If it’s common, it belongs in the roadmap. If not, I look for extension or configuration options rather than altering the core API, to avoid fragmentation.

---

### ❓ “How do you say no to partners?”

**Excellent answer:**

> By explaining trade-offs clearly and offering alternatives. Saying no is easier when partners understand the long-term cost of special-case behavior.

---

# 6️⃣ Incident & Failure Scenarios (very realistic)

### ❓ “An API outage impacts multiple partners — what do you do?”

**Strong answer structure:**

1. Stabilize the system
    
2. Communicate clearly
    
3. Diagnose root cause
    
4. Prevent recurrence
    

**Example answer:**

> First we stabilize and reduce impact, then communicate transparently with partners. After recovery, we conduct a post-incident review to improve monitoring, resilience, or processes.

---

# 7️⃣ Data Normalization (VERY relevant to you)

### ❓ “Different partners send different data formats — how do you handle this?”

**Strong answer:**

> We normalize data internally into a common model and avoid exposing partner-specific quirks externally. This keeps the API simple and scalable.

---

# 8️⃣ Interviewer’s REAL question behind all of this

They are asking:

> “Can we trust you to protect our platform while keeping partners successful?”

Your background with:

- RedDoorz OTAs
    
- Finantier fintech clients  
    already proves this.
    

---

# 🧠 3 One-liners to memorize (very useful)

1️⃣

> I treat APIs as long-lived products, not just technical interfaces.

2️⃣

> Standardization with controlled flexibility is key to scaling integrations.

3️⃣

> Most API problems are communication and governance problems, not technical ones.