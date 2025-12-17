# BUSINESS PLAN - MEU PLANTÃO AMIGO (MPA)

## SaaS Platform for Collaborative Medical Support

---

## EXECUTIVE SUMMARY

### Overview

**Meu Plantão Amigo (MPA)** is a SaaS (Software as a Service) platform focused on providing real-time collaborative medical support, connecting resident and novice physicians with experienced specialists for quick interconsultations, as well as offering access to medical tools, educational content, and an integrated professional community.

### Value Proposition

Solve the **diagnostic insecurity** and **lack of immediate support** that novice physicians and residents face during shifts and consultations, offering:

- **Interconsultations** with approved specialists
- **Access to medical tools** (calculators, scores, protocols)
- **Curated educational content** (articles, videos, podcasts)
- **Blog for discussing medical topics** publishing posts and comments
- **Professional networking** between different seniority levels
- **Monetization for specialists** who offer support

### Business Model

**Freemium + Subscription + Marketplace**

- **Basic Plan (Free)**: Limited access to content and 3 consultations, 1-month trial period
- **Premium Plan (R$ 120/month)**: Limited interconsultations (10), exclusive content, priority service
- **Pay per use for interconsultations R$60 per interconsultation**: Use of interconsultations exceeding those included in the plan
- **Specialist Marketplace**: Remuneration for availability time for service

---

## MARKET ANALYSIS

### Identified Problem

Based on market research conducted (Forms.md - Sprint 5):

**Pains of Novice Physicians:**

1. **80% feel insecure** in clinical decisions during shifts
2. **Lack of immediate support** for discussing complex cases
3. **Medical information scattered** across multiple sources
4. **Absence of a structured channel** for validating conduct
5. **Difficulty networking** with specialists

**Digital Behavior:**

- **100% use medical apps** (Afya Whitebook 80%, Medway 60%)
- **Main resources used**: Prescription guide, diagnostic algorithms, ICD, medical calculators
- **80% value remuneration** for offering support to colleagues
- **100% see utility** in a second medical opinion

### Target Audience

#### Persona 1: Jorge - Resident Physician (Main User)

- **Profile**: 27 years old, recently graduated, works hospital shifts
- **Pains**: Diagnostic insecurity, lack of support, professional anxiety
- **Needs**:
  - Reliable channel to ask questions quickly
  - Access to organized and reliable content
  - Network with experienced physicians
  - Time optimization during shifts

#### Persona 2: Dr. Renato - Specialist Physician (Service Provider)

- **Profile**: 45+ years old, established specialist, interested in healthtech
- **Needs**:
  - Contact with physicians in training
  - Easy access to studies and discoveries
  - Optimization of time gaps between consultations
  - Extra income through mentorship

### Market Size (TAM/SAM/SOM)

**TAM (Total Addressable Market):**

- Brazil: ~500,000 active physicians (CFM 2024)
- Physicians with up to 10 years of training: ~150,000 (30%)
- Potential: 150,000 x R$ 120/month x 12 + 20% of excess interconsultations (R$ 120) = **R$ 432 million/year**

**SAM (Serviceable Available Market):**

- Digitally active physicians in large urban centers: ~50,000
- Potential: 50,000 x R$ 120/month x 12 + 20% of excess interconsultations (R$ 120) = **R$ 144 million/year**

**SOM (Serviceable Obtainable Market - Year 1):**

- Conservative goal: 1,000 premium users (2% of SAM)
- Revenue: 1,000 x R$ 120/month + R$120/user x 12 = **R$ 2.88 million/year\*\*

---

## PRODUCT AND SERVICES

### Implemented Features (MVP)

#### 1. **Interconsultation System**

**Status**: Implemented

- Interconsultation request with specialty selection
- Automatic matchmaking with available specialists
- Real-time chat with history
- Feedback and post-consultation evaluation
- Push notifications for responses

**Usage Flow**:

1. Resident physician requests interconsultation (specialty + case description)
2. System finds available specialist of the specialty
3. Push notification for specialist
4. Chat started automatically
5. Video call option if necessary
6. Feedback at the end

#### 2. **User and Specialist System** 

**Status**: Implemented

- Registration with authentication (Supabase Auth)
- Differentiated profiles: Resident Physician / Specialist
- Specialist registration with pending validation
- Profile photo upload
- Specialty management (55 medical specialties)

**Specialist Validation**:

- RQE verification
- Possibility of more than one specialty registration
- Well-defined status (approved, pending, canceled)

**Supported Specialties**:

- 55 medical specialties recognized by the CFM
- From Acupuncture to Urology
- Complete mapping in backend and mobile

#### 3. **Subscription System (Stripe Integration)** 

**Status**: Implemented

- Integration with Stripe Payment
- Two plans: Basic (Free) and Premium (R$ 120/month)
- Payment Intent for one-time payments
- Webhook for payment confirmation
- Automatic upgrade after confirmed payment

**Plans**:

| Feature               | Basic (Free for 30 days) | Premium (R$ 120) |
| --------------------- | ------------------------ | ---------------- |
| Interconsultations/mo | 3                        | Limited 10       |
| Content access        | Limited                  | Full             |
| Priority service      | ❌                       |               |
| Specialized support   | ❌                       |               |
| Push notifications    |                       |               |
| Chat with specialists |                       |               |

#### 4. **Educational Content Feed** 

**Status**: Implemented (MVP)

- Medical Articles Tab
- Educational Videos Tab
- Podcasts Tab
- Blog Tab with posts and comments
- Categorization by specialty
- Content type badges

**Content Roadmap**:

- [ ] Integration with medical content APIs (DynaMed, UpToDate)
- [ ] Favorites system
- [ ] Reading history
- [ ] Personalized recommendations by specialty

#### 5. **Push Notifications (Firebase)** 

**Status**: Implemented

- Firebase Cloud Messaging (FCM)
- Local and remote notifications
- Interconsultation response alerts
- New content notifications
- Deep linking for direct navigation

#### 6. **Clinical Calculators**

**Status**: Implemented

- Creatinine clearance (Cockcroft-Gault)
- Body surface area
- BMI and classification
- Medication dose by weight

### Planned Features (Roadmap)

####  **Profile and Gamification** (High Priority)

- User profile with photo
- Statistics: requested consultations, plan
- Level system (achievements):
  - 🟢 Novice Physician
  - 🔵 Intermediate Physician
  - 🟣 Advanced Physician
  - 🟠 Experienced Physician
  - 🔴 Expert Physician

**Roadmap**:

- [ ] Points for activities
- [ ] Badges by specialty
- [ ] Ranking of best-rated specialists

#### **Protocols and Guidelines** (High Priority)

- Integrated ICD-10 search
- Protocols by specialty (sepsis, stroke, AMI, etc.)
- Updated guidelines (SBC, SBP, AMB)
- Interactive flowcharts
- Offline-first for access during shifts

#### **AI for Differential Diagnosis** (Medium Priority)

- Suggestion of differential diagnoses based on symptoms
- Integration with trained medical LLM
- Responsibility disclaimer
- Decision support (not replacement)

#### **Prescription Guide** (High Priority)

- Complete digital leaflet
- Drug interactions
- Dosage by indication
- Renal/hepatic dose adjustment
- Generics and similars

#### 📊 **Specialist Dashboard** (Medium Priority)

- Management of received interconsultations
- Service history
- Earnings report
- Availability schedule
- Evaluation statistics

---

## TECHNICAL ARCHITECTURE

### Current Tech Stack

#### **Backend**

```python
Language: Python 3.11+
Framework: FastAPI
Database: PostgreSQL (Supabase)
Authentication: Supabase Auth
Queues: RabbitMQ
Storage: Supabase Storage (profile images)
Payments: Stripe API
Hosting: Railway
```

#### **Mobile**

```dart
Framework: Flutter 3.24+
Language: Dart
State Management: Provider
Authentication: SecureStorage (tokens)
Push Notifications: Firebase Cloud Messaging
Payments: flutter_stripe
Image Upload: image_picker
```

### Security and Compliance

#### **LGPD and Privacy**

- Secure authentication (JWT tokens)
- Encrypted storage (SecureStorage)
- Mandatory HTTPS
- ⏳ Consent form (in development)
- ⏳ Privacy policy
- ⏳ Anonymization of medical data

#### **Medical Regulation**

- **Disclaimer**: Platform does not replace medical consultation
- **Specialist validation**: Manual approval process
- ⏳ **CRM verification**: Integration with CFM API
- ⏳ **Consultation audit**: Complete log for compliance
- ⏳ **Medical terms of use**: Responsibility and ethics

#### **ISO 27001 and Data Security**

- ⏳ End-to-end encryption in messages
- ⏳ Automatic daily backup
- ⏳ Disaster recovery plan
- ⏳ Semiannual penetration tests

---

## REVENUE MODEL

### Revenue Sources

#### 1. **Recurring Subscriptions** (Main Revenue)

**Premium Plan: R$ 120/month**

- Limited interconsultations
- Exclusive content
- Priority service
- Specialized support
- Request for separate interconsultations

**Year 1 Projection**:
| Month | Free Users | Premium Users | MRR | ARR |
|-------|------------|---------------|-----|-----|
| 1 | 15 | 5 | R$ 600 | R$ 7,200 |
| 3 | 40 | 10 | R$ 1,200 | R$ 14,400 |
| 6 | 120 | 20 | R$ 2,400 | R$ 28,800 |
| 12 | 450 | 50 | R$ 6,000 | R$ 72,000 |

**Expected Conversion Rate**: 10% (conservative)
**Estimated Churn**: 5%/month

#### 2. **Interconsultation Marketplace** (Complementary Revenue)

**Model**: 20% commission on paid interconsultations

- Specialist charges R$ 50-200 per interconsultation
- MPA keeps 20% (R$ 10-40)
- Specialist receives 80% (R$ 40-160)

**Year 1 Projection**:

- 500 paid interconsultations/month
- Average ticket: R$ 100
- MPA Commission (20%): R$ 10,000/month
- **Annual Revenue**: R$ 120,000

#### 3. **Partnerships and Medical Advertising** (Future)

**Opportunities**:

- Pharmaceutical laboratories (native advertising)
- Medical equipment companies
- Educational platforms (affiliates)
- Congresses and medical events

**Estimate**: R$ 5,000-10,000/month after base of 10,000+ users

#### 4. **Corporate Licensing** (B2B)

**Model**: License for hospitals and clinics

- Hospitals pay monthly license for unlimited access for their physicians
- Value: R$ 500-2,000/month per institution
- Target: 50 hospitals in Year 2
- **Potential Revenue**: R$ 300,000-1,200,000/year

### Financial Projection (5 Years)

| Year | Premium Users | MRR        | ARR          | Marketplace Revenue | Total Revenue |
| ---- | ------------- | ---------- | ------------ | ------------------- | ------------- |
| 1    | 50            | R$ 6,000   | R$ 72,000    | R$ 12,000           | R$ 84,000     |
| 2    | 150           | R$ 18,000  | R$ 216,000   | R$ 36,000           | R$ 252,000    |
| 3    | 350           | R$ 42,000  | R$ 504,000   | R$ 84,000           | R$ 588,000    |
| 4    | 550           | R$ 66,000  | R$ 792,000   | R$ 132,000          | R$ 924,000    |
| 5    | 1,350         | R$ 162,000 | R$ 1,944,000 | R$ 324,000          | R$ 2,268,000  |

**Assumptions**:

- Organic growth + marketing
- Conversion rate: 10%
- Churn: 5%/month (improves to 3% after Year 2)
- Average ticket maintained
- Marketplace grows proportionally

---

## GO-TO-MARKET STRATEGY

### Phase 1: MVP and Validation (Months 1-3)

**Goal**: 100 active users, 10 paying

**Actions**:

1. **Closed beta with early adopters**

   - 50 resident physicians from partner hospitals
   - 10 manually validated specialists
   - Intensive feedback collection

2. **Usability tests**

   - 10 test sessions with real users
   - UX/UI adjustments based on feedback

3. **Hypothesis validation**
   - Free → premium conversion rate
   - Engagement with interconsultations
   - Utilization of educational content

### Phase 2: Initial Growth (Months 4-6)

**Goal**: 500 users, 50 paying

**Acquisition Channels**:

1. **Content Marketing**

   - Blog with SEO-optimized articles
   - YouTube: tutorials and clinical cases
   - Instagram: quick tips and medical curiosities
   - LinkedIn: professional networking

2. **Strategic Partnerships**

   - Medical schools (residency programs)
   - University hospitals
   - Medical specialty societies

3. **Ambassador Program**

   - Resident physician leaders as evangelists
   - Bonus: 1 month free for every 3 referrals

4. **ASO (App Store Optimization)**
   - Keyword optimization: "medical app", "interconsultation", "medical support"
   - Positive reviews and ratings incentivized

### Phase 3: Scale (Months 7-12)

**Goal**: 500 users, 50 paying

**Paid Channels**:

1. **Meta Ads (Instagram/Facebook)**

   - Segmentation: physicians 25-35 years old
   - Budget: R$ 5,000/month
   - Target CAC: R$ 50

2. **Google Ads**

   - Search: medical keywords
   - YouTube Ads: educational videos
   - Budget: R$ 3,000/month

3. **LinkedIn Ads**

   - Target: physicians graduated less than 5 years ago
   - Budget: R$ 2,000/month

4. **Medical Events**
   - Presence at resident congresses
   - Sponsorship of specialty events
   - Live app demos

**Key Metrics (KPIs)**:

- **CAC (Customer Acquisition Cost)**: < R$ 100
- **LTV (Lifetime Value)**: > R$ 600 (12 months of subscription)
- **LTV/CAC Ratio**: > 6
- **Churn Rate**: < 5%/month
- **NPS (Net Promoter Score)**: > 50
- **Free → Premium Conversion**: > 10%

---

## TEAM AND ORGANIZATION

### Current Team (MVP)

- 1 Product Owner
- 2 Full-Stack Developers (Python/Flutter)
- 1 UI/UX Designer
- 1 Medical Advisor (clinical validation)

### Required Team (Year 1)

**Technical Team**:

- 1 CTO / Tech Lead (Senior)
- 3 Backend Developers (Python/FastAPI)
- 2 Mobile Developers (Flutter)
- 1 DevOps Engineer
- 1 QA Engineer

**Product Team**:

- 1 Head of Product
- 1 Product Designer
- 1 UX Researcher

**Medical Content Team**:

- 1 Chief Medical Officer (CMO)
- 2 Medical content editors
- 10+ Collaborating specialists (freelance)

**Growth Team**:

- 1 Head of Growth
- 1 Growth Hacker / Performance Marketing
- 1 Social Media Manager
- 1 SEO/Content Specialist

**Operations Team**:

- 1 Customer Success Manager
- 2 Content moderators
- 1 Data Analyst

**Total**: ~12 people (Year 1 - Focused on Core)

### Organizational Structure

```
CEO / Founder
├── CTO (Technology)
│   ├── Backend Team
│   ├── Mobile Team
│   └── DevOps
├── CMO - Chief Medical Officer
│   ├── Medical Content
│   └── Clinical Validation
├── Head of Product
│   ├── Design
│   └── UX Research
├── Head of Growth
│   ├── Marketing
│   └── Sales (B2B)
└── COO (Operations)
    ├── Customer Success
    └── Data Analytics
```

---

## FINANCIAL PLAN

### Cost Structure (Year 1)

#### **Monthly Fixed Costs**

**Personnel** (70% of cost):
| Role | Quantity | Average Salary | Total/Month |
|------|----------|----------------|-------------|
| CTO | 1 | R$ 20,000 | R$ 20,000 |
| Senior Developers | 3 | R$ 12,000 | R$ 36,000 |
| Mid-level Developers | 2 | R$ 8,000 | R$ 16,000 |
| Head of Product | 1 | R$ 15,000 | R$ 15,000 |
| CMO (Physician) | 1 | R$ 18,000 | R$ 18,000 |
| Head of Growth | 1 | R$ 12,000 | R$ 12,000 |
| Customer Success | 1 | R$ 6,000 | R$ 6,000 |
| Designer | 1 | R$ 7,000 | R$ 7,000 |
| **Personnel Subtotal** | | | **R$ 130,000** |

**Infrastructure and Software**:
| Item | Cost/Month |
|------|------------|
| Railway (Backend hosting) | R$ 500 |
| Supabase (Database + Auth + Storage) | R$ 1,000 |
| Stripe (Payment) - 2.9% + R$ 0.39 | Variable |
| Firebase (Notifications) | R$ 300 |
| Vercel/AWS (CDN, static) | R$ 200 |
| Tools (Slack, Notion, Figma, etc.) | R$ 1,000 |
| **Infrastructure Subtotal** | **R$ 3,000** |

**Marketing and Sales**:
| Item | Cost/Month |
|------|------------|
| Meta Ads | R$ 5,000 |
| Google Ads | R$ 3,000 |
| LinkedIn Ads | R$ 2,000 |
| Content creation | R$ 3,000 |
| Events and partnerships | R$ 2,000 |
| **Marketing Subtotal** | **R$ 15,000** |

**Operational**:

- Office (coworking): R$ 5,000/month
- Legal and accounting: R$ 3,000/month
- Insurance and compliance: R$ 2,000/month
- **Operational Subtotal**: **R$ 10,000/month**

#### **Total Monthly Cost: R$ 158,000**

#### **Total Annual Cost: R$ 1,896,000**

### Investment Need

**Seed Round: R$ 2,500,000**

**Use of Funds**:

- 60% - Personnel (R$ 1,500,000)
- 20% - Marketing and Growth (R$ 500,000)
- 10% - Infrastructure and Technology (R$ 250,000)
- 10% - Operational reserve (R$ 250,000)

**Runway**: 15 months

### Break-Even Projection

**Required Monthly Revenue**: R$ 158,000
**Required Premium Users**: 1,317 (at R$ 120.00/month)

**Expected Break-Even**: Year 4-5

---

## MILESTONES AND ROADMAP

### Q1 2025 (Jan-Mar) - MVP Launch

- Closed beta with 100 users
- Interconsultation system working
- Stripe integration
- App published on Play Store and App Store
- **Goal**: 10 paying users

### Q2 2025 (Apr-Jun) - Product-Market Fit

- [ ] Implement medical calculators (top 10)
- [ ] Prescription guide MVP
- [ ] ICD-10 search system
- [ ] Ambassador program
- [ ] 500 organic downloads
- **Goal**: 50 paying users, NPS > 40

### Q3 2025 (Jul-Sep) - Growth

- [ ] Paid marketing campaign
- [ ] Partnerships with 5 hospitals/schools
- [ ] Blog with 20 SEO articles
- [ ] YouTube channel with 50 videos
- [ ] Clinical protocols (50+)
- **Goal**: 250 paying users

### Q4 2025 (Oct-Dec) - Scale

- [ ] AI for differential diagnosis (beta)
- [ ] Specialist dashboard
- [ ] Active interconsultation marketplace
- [ ] 5,000 total downloads
- [ ] Presence at 3 medical congresses
- **Goal**: 500 paying users

### 2026 - Consolidation

- [ ] B2B expansion (hospitals)
- [ ] Corporate licensing
- [ ] Certifications and partnerships with medical societies
- [ ] Internationalization (Portugal, Mexico)
- **Goal**: 2,000 paying users

---

## COMPETITIVE ADVANTAGES

### MPA Differentiators

#### 1. **Focus on Real-Time Interconsultations**

- Competitors focus on static content
- MPA connects physicians in real-time for urgent cases
- **Unique Value**: "Specialist in your pocket"

#### 2. **Mutual Support Community**

- Networking between different seniority levels
- Gamification and recognition
- Monetization for specialists (win-win)

#### 3. **Complete Integration**

- All-in-one: Interconsultations + Content + Tools
- Competitors are specialized in only one area
- Reduces need for multiple apps

#### 4. **Mobile-First and Medical UX**

- Interface optimized for use during shifts
- Offline mode for protocols
- Fast and intuitive navigation

#### 5. **Rigorous Specialist Validation**

- Manual approval process
- CRM verification (future)
- Reputation based on evaluations

### Competitor Analysis

| Competitor         | Main Focus                   | Price       | MPA Differentiator                |
| ------------------ | ---------------------------- | ----------- | --------------------------------- |
| **Afya Whitebook** | Protocols and prescriptions  | R$ 34.90/mo | MPA has live interconsultations   |
| **DynaMed**        | Evidence and guidelines      | R$ 199/mo   | MPA is more accessible and social |
| **Medway**         | Continuing medical education | R$ 89/mo    | MPA has real-time support         |
| **Figure 1**       | Clinical case community      | Free        | MPA has monetization and chat     |
| **Doximity**       | Medical networking (USA)     | Free        | MPA focuses on clinical support   |

**Positioning**: "The most complete collaborative medical support platform in Brazil"

---

## SUCCESS METRICS

### Product Metrics (Product-Market Fit)

#### **Engagement**

- **DAU/MAU (Daily/Monthly Active Users)**: > 30%
- **Sessions per user/week**: > 3
- **Average time per session**: > 5 minutes
- **Retention Rate (Day 30)**: > 40%

#### **Interconsultations**

- **Average response time**: < 15 minutes
- **Resolution rate**: > 80%
- **Average rating**: > 4.5/5 stars
- **% active specialists**: > 60%

#### **Conversion**

- **Free → Premium**: > 10%
- **Trial → Paid**: > 25%
- **Churn reactivation**: > 15%

### Business Metrics

#### **Revenue**

- **MRR (Monthly Recurring Revenue)**: R$ 6,000 (Year 1)
- **ARR (Annual Recurring Revenue)**: R$ 72,000 (Year 1)
- **ARPU (Average Revenue Per User)**: R$ 120.00
- **Revenue Churn**: < 5%

#### **CAC and LTV**

- **CAC (Customer Acquisition Cost)**: < R$ 100
- **LTV (Lifetime Value)**: > R$ 600
- **LTV/CAC Ratio**: > 6
- **Payback Period**: < 4 months

#### **Growth**

- **MoM Growth Rate**: 20%+
- **Viral Coefficient (K-factor)**: > 0.3
- **Organic vs Paid**: 60% organic (long term)

### Satisfaction Metrics

- **NPS (Net Promoter Score)**: > 50
- **CSAT (Customer Satisfaction)**: > 85%
- **App Store Rating**: > 4.5 stars
- **Support Ticket Resolution Time**: < 24h

---

## RISKS AND MITIGATIONS

### Identified Risks

#### 1. **Regulatory Risk** 🔴 HIGH

**Description**: Changes in telemedicine regulation by the CFM
**Impact**: May limit or prohibit remote interconsultations
**Mitigation**:

- Maintain clear disclaimer (does not replace in-person consultation)
- Lobby with medical entities
- Legal consulting specialized in digital health
- Professional liability insurance

#### 2. **Low Free → Premium Conversion** 🟡 MEDIUM

**Description**: Users do not see enough value to pay
**Impact**: Revenue below projected
**Mitigation**:

- A/B tests of pricing and features
- Limit more features of the free plan
- 14-day trial program
- Email marketing with success cases

#### 3. **Lack of Available Specialists** 🟡 MEDIUM

**Description**: Few specialists accepting interconsultations
**Impact**: High response time, dissatisfied users
**Mitigation**:

- Incentive program for specialists
- Gamification of services
- Partnerships with specialty societies
- Increase remuneration per interconsultation

#### 4. **Big Tech Competition** 🔴 HIGH

**Description**: Google, Amazon, or large players entering the market
**Impact**: Loss of market share
**Mitigation**:

- Build strong and engaged community
- Focus on niche (Brazilian physicians)
- Strategic partnerships with hospitals
- M&A as exit strategy

#### 5. **Privacy/Data Leak Problems** 🔴 CRITICAL

**Description**: Breach of sensitive medical data
**Impact**: Destroyed reputation, legal lawsuits
**Mitigation**:

- End-to-end encryption
- Quarterly security audits
- Certifications (ISO 27001, HIPAA-like)
- Cyber insurance
- Incident response plan

#### 6. **High Churn** 🟡 MEDIUM

**Description**: Users canceling subscription after a few months
**Impact**: Low LTV, stagnant growth
**Mitigation**:

- Robust onboarding in the first 7 days
- Proactive Customer Success
- Engagement notifications
- Loyalty program
- Cancellation surveys

### Contingency Plan

**If ARR < 50% of goal in Month 6**:

1. Pivot to B2B (hospitals) as main revenue
2. Reduce team by 30%
3. Focus on retention (pause acquisition)
4. Seek strategic partnership or acquisition

**If regulatory change prohibits telemedicine**:

1. Migrate to "asynchronous second opinion" model
2. Focus on continuing medical education
3. Pivot to support tools (calculators, protocols)

---

## EXIT STRATEGY

### Exit Options

#### 1. **Strategic Acquisition** (Probability: 60%)

**Potential Buyers**:

- **Afya Educação** (largest medical education group in Brazil)
- **Rede D'Or** (largest private hospital network)
- **Hospital Albert Einstein** (digital health innovation)
- **Hapvida/NotreDame Intermédica** (health operators)
- **Amazon (AWS Healthcare)** or **Google Health**

**Expected Valuation**:

- Multiple of 5-10x ARR
- With 10,000 premium users (ARR ~R$ 14.4M): **R$ 72-144 million**

**Timing**: Year 3-5

#### 2. **IPO (Public Offering)** (Probability: 10%)

**Requirements**:

- ARR > R$ 50 million
- 100,000+ active users
- Presence in 3+ countries
- Positive EBITDA

**Timing**: Year 7+

#### 3. **Merger with Competitor** (Probability: 20%)

**Scenario**: Consolidation of the healthtech market

- Merger with Medway, Whitebook, or similar
- Create Brazilian market leader

**Timing**: Year 4-6

#### 4. **Keep Independent (Bootstrapped)** (Probability: 10%)

**Scenario**: Sustainable organic growth

- Focus on profitability from early on
- Dividend distribution to founders
- Family technology business

## APPENDICES

### Appendix A: Supported Medical Specialties (55 total)

- Acupuncture
- Allergy and Immunology
- Anesthesiology
- Angiology
- Cardiology
- Cardiovascular Surgery
- Hand Surgery
- (...continues with all 55 specialties)

### Appendix B: Technologies and APIs

**Backend**:

- FastAPI (Python framework)
- PostgreSQL (Database)
- RabbitMQ (Message queue)
- Supabase (BaaS)
- Stripe (Payments)

**Mobile**:

- Flutter 3.24+
- firebase_messaging
- flutter_stripe
- image_picker
- http package

### Appendix C: Market Research

**5 respondents (physicians)**:

- 80% use medical apps daily
- 100% see utility in second opinion
- 80% value compensation for helping colleagues
- Most desired features: Calculators, ICD, Protocols

### Appendix D: User Stories and Requirements

- 15+ user stories documented (Sprint 2)
- Business requirements mapped
- Detailed personas (Jorge and Dr. Renato)

---

## CONCLUSION

**Meu Plantão Amigo** is more than a medical app - it is a **collaborative support platform** that solves real pains of novice physicians and creates a medical knowledge economy.

### Why invest in MPA?

**Real and Validated Problem**: 80% of physicians feel insecure in clinical decisions
**Growing Market**: 500,000 physicians in Brazil, healthtech growth
**Proven Business Model**: Recurring SaaS + Marketplace
**Ready Technology**: Functional MVP, 55 specialties, Stripe integration
**Qualified Team**: Developers + Physicians + Designers
**Competitive Advantage**: Unique with live interconsultations + community
**Scalable**: Digital model, high margin (70%+)
**Clear Exit Strategy**: M&A with large health players

### The Opportunity

The digital health market in Brazil is **exploding**:

- Telemedicine grew 300% post-pandemic
- Investments in healthtech: R$ 1.5 billion (2023)
- Physicians increasingly digital (80% use apps)

**MPA is positioned to capture this wave.**

---

**Version**: 1.0
**Date**: November 2025
**Author**: Meu Plantão Amigo Team
**Confidential**: This document contains proprietary information.
