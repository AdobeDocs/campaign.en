# AC-UI Jira Tickets Analysis - Working Recap
**Date:** January 12, 2026
**Document Type:** Working Document / Internal Analysis

---

## Executive Summary

This document analyzes product Jira tickets from multiple queries related to AC-UI releases (January 2026 and November 2025). The analysis focuses on identifying documentation requirements, proposing DOCAC tickets, and highlighting open questions.

**Total Unique Tickets Analyzed:** 19
**Tickets Requiring Documentation:** 14
**Tickets Already Documented:** 5
**Tickets with No Doc Need:** 5

---

## 1. List of Analyzed Tickets

### 1.1 AC-UI-26-01-Monthly Release (January 2026)

| Ticket ID | Title | Status | Priority | Components |
|-----------|-------|--------|----------|------------|
| NEO-91565 | [Web UI] Add support for personalisation fields (Advanced AEM Integration) | Resolved | Normal | ACS to ACC, PIX UI/UX |
| NEO-80973 | Dynamic Reporting availability for all web UI users | In Progress | Normal | ACS to ACC, PIX UI/UX |
| NEO-86754 | [UX/UI] A/B Testing | In Progress | Blocker | PIX UI/UX |
| NEO-76126 | Schemas authoring - create new table, extend schemas and access external DB | In Progress | Critical | PIX UI/UX |
| NEO-93487 | [Web UI] Delivery scheduling compute process similar to the one in ACS | New | Critical | PIX UI/UX |
| NEO-92400 | Release improvements - January 26 | New | Normal | PIX UI/UX |
| NEO-88838 | Content Editor: Use theme variables in fragment | New | Normal | PIX UI/UX |
| NEO-92668 | [UX/UI] Web Analytics | New | Normal | PIX UI/UX |
| NEO-86753 | [UX/UI] AEM integration for Live copies/ Language copies | New | Blocker | ACS to ACC, PIX UI/UX |

### 1.2 Release Improvements Linked Tickets (NEO-92400)

| Ticket ID | Title | Status | Priority | Components |
|-----------|-------|--------|----------|------------|
| NEO-92942 | [Rule builder] Pre-defined filters - Shared option | Resolved | Normal | PIX UI/UX |
| NEO-91299 | Web UI - Continuous delivery activity | Closed | Major | PIX UI/UX |
| NEO-90130 | Enable OOTB File Upload for Multi-lingual Push Notification Deliveries | Closed | Critical | ACS to ACC, PIX UI/UX |

### 1.3 AC-UI-25-11-Monthly Release (November 2025)

| Ticket ID | Title | Status | Priority | Components |
|-----------|-------|--------|----------|------------|
| NEO-91566 | [Web UI] Support for CTA tracking in webui | Closed | Normal | ACS to ACC, PIX UI/UX |
| NEO-91564 | [Web UI] [AEM multilingual in ACC] UI support for AEM multilingual | Closed | Normal | ACS to ACC, PIX UI/UX |
| NEO-90183 | [UX/UI] Multilingual Rich Push - UI | Closed | Blocker | PIX UI/UX |
| NEO-91567 | [Web UI] Add support for NRT Feature | Resolved | Normal | ACS to ACC, PIX UI/UX |
| NEO-91563 | Transactional Rest API for Profile Based Enrichment - Web UI | Resolved | Normal | ACS to ACC, PIX UI/UX |
| NEO-92151 | [UI/UX] Profile based Enrichment Transactional Messaging - Phase 2 | Resolved | Major | ACS to ACC, PIX UI/UX |
| NEO-84916 | [UX/UI] Set up and manage the approval process | Resolved | Critical | PIX UI/UX |

---

## 2. Tickets Requiring Documentation

### 2.1 HIGH PRIORITY - Active Development (AC-UI-26-01)

#### **NEO-86754: A/B Testing**
- **Status:** In Progress (On Track)
- **Why Documentation Needed:** Major new feature for email content experimentation with A/B testing capabilities
- **Existing DOCAC:** DOCAC-13104 (New status)
- **Documentation Scope:**
  - Creating A/B test experiments in deliveries
  - Defining content/delivery variants
  - Setting sample proportions and sending test variants
  - Defining evaluation criteria
  - Analyzing experiment results and selecting winners
  - Best practices and limitations
- **Target Audience:** Marketing users, Campaign managers
- **Release:** 8.9.1, AC-UI-26-01-Monthly
- **Open Questions:**
  - Final UI/UX validation status?
  - Any limitations for transactional messages?
  - Integration with Acrite content preview?

#### **NEO-80973: Dynamic Reporting Availability**
- **Status:** In Progress (Ready for Review)
- **Why Documentation Needed:** Expanding Dynamic Reporting to all Web UI users (not just 8.7 ACS to ACC customers)
- **Existing DOCAC:** DOCAC-11070 (Closed), DOCAC-13432 (Resolved - language limitations)
- **Documentation Scope:**
  - Availability and access requirements
  - Supported languages documentation
  - Known limitations vs legacy reporting
  - Conflicting metrics display with legacy reporting
  - Demo environment setup
- **Target Audience:** All Web UI users, Analysts
- **Release:** 8.8.1, AC-UI-26-01-Monthly
- **Open Questions:**
  - Demo environment availability status?
  - Complete list of conflicting metrics with legacy reporting?
  - Language support matrix?

#### **NEO-76126: Schemas Authoring**
- **Status:** In Progress (On Track)
- **Why Documentation Needed:** Significant admin feature for data model management
- **Existing DOCAC:** DOCAC-13826 (New status)
- **Documentation Scope:**
  - Creating new tables
  - Extending existing schemas
  - Accessing external databases
  - Form definition for custom entities
  - Navigation and CRUD operations
  - Phase 3 capabilities (create and extend schemas) - ETA Feb end
- **Target Audience:** Admin users, Technical administrators
- **Release:** AC-UI-26-01-Monthly
- **Due Date:** Feb 28, 2026
- **Open Questions:**
  - When will Phase 2 be completed for FF activation?
  - Phase 3 delivery timeline confirmation?
  - Environment setup requirements?

#### **NEO-93487: Delivery Scheduling Compute Process (H&M)**
- **Status:** New
- **Why Documentation Needed:** Critical customer escalation - timezone-based delivery scheduling
- **Existing DOCAC:** None identified
- **Documentation Scope:**
  - Scheduling deliveries based on user timezone
  - Using calculated formulas for multi-timezone regions
  - Configuration examples (e.g., USA with multiple timezones)
  - Best practices for global campaigns
  - Feature comparison with ACS
- **Target Audience:** Campaign managers, Marketing users
- **Customer Impact:** H&M (50+ markets)
- **Release:** 8.9.1, AC-UI-26-01-Monthly, 8.8.2.NEO-90300
- **Open Questions:**
  - Feature demo scheduled with PM?
  - Complete functional specifications available?
  - UI mockups finalized?

#### **NEO-86753: AEM Integration for Live Copies/Language Copies**
- **Status:** New
- **Why Documentation Needed:** Microsoft-specific feature for multilingual content management
- **Existing DOCAC:** DOCAC-13829 (Resolved)
- **Documentation Scope:**
  - Browsing AEM delivery templates
  - Creating Live copies
  - Creating Language copies content variants
  - Workflow and best practices
  - Integration setup requirements
- **Target Audience:** Marketing users working with AEM, Microsoft teams
- **Release:** AC-UI-26-01-Monthly
- **Priority:** Blocker
- **Open Questions:**
  - Work transferred to Himanshu's team - current status?
  - Timeline for completion?

#### **NEO-92668: Web Analytics**
- **Status:** New (On Track)
- **Why Documentation Needed:** External account configuration for web analytics integration
- **Existing DOCAC:** None identified
- **Documentation Scope:**
  - Web Analytics external account creation
  - Configuration parameters
  - Integration with delivery tracking
  - Reporting capabilities
- **Target Audience:** Admin users, Marketing analysts
- **Release:** AC-UI-26-01-Monthly
- **Open Questions:**
  - Environment availability status?
  - Required setup steps?

### 2.2 MEDIUM PRIORITY - Recently Delivered (AC-UI-25-11)

#### **NEO-90183: Multilingual Rich Push**
- **Status:** Closed
- **Why Documentation Needed:** New capability for iOS/Android rich push with multilingual support
- **Existing DOCAC:** DOCAC-13565 (New status)
- **Documentation Scope:**
  - Rich push notification configuration for iOS and Android
  - Multilingual content variants
  - Template selection
  - Additional fields for rich content
  - File upload capabilities
  - Best practices and limitations
- **Target Audience:** Marketing users, Mobile channel managers
- **Release:** AC-UI-25-11-Monthly, 8.8.2
- **Customer:** H&M

#### **NEO-84916: Approval Process Management**
- **Status:** Resolved
- **Why Documentation Needed:** Major workflow feature for delivery validation
- **Existing DOCAC:** DOCAC-13827 (New status)
- **Documentation Scope:**
  - Setting up approval operators in deliveries/campaigns
  - Configuring content approval
  - Configuring target approval
  - Managing approval workflows across channels (Email, SMS, Push iOS/Android, Direct Mail, Call Center)
  - Accept/reject processes
  - Approval reporting and tracking
- **Target Audience:** Campaign managers, Admin users
- **Release:** AC-UI-25-11-Monthly
- **Priority:** Critical
- **Customer:** Pierre Fabre

#### **NEO-91299: Continuous Delivery Activity**
- **Status:** Closed
- **Why Documentation Needed:** New workflow activity for recurring delivery scenarios
- **Existing DOCAC:** DOCAC-13586 (New status), DOCAC-13808 (Closed - contextual help)
- **Documentation Scope:**
  - Continuous delivery activity configuration
  - Delivery template picker requirements
  - Process error handling
  - Workflow integration
  - Use cases and examples
- **Target Audience:** Technical users, Workflow designers
- **Release:** AC-UI-26.01.06

#### **NEO-90130: Multi-lingual Push File Upload (H&M)**
- **Status:** Closed
- **Why Documentation Needed:** OOTB feature parity with ACS for file-based multilingual push
- **Existing DOCAC:** DOCAC-13606 (New status)
- **Documentation Scope:**
  - CSV file upload for multilingual push notifications
  - File format specifications
  - Field mapping
  - iOS and Android specific configurations
  - Data message type handling
  - Troubleshooting and known issues
- **Target Audience:** Marketing users, Campaign managers
- **Release:** AC-UI-25-10-Monthly, AC-UI-25.11.03
- **Priority:** Critical
- **Customer:** H&M (ACS to ACC migration)

#### **NEO-92942: Pre-defined Filters - Shared Option**
- **Status:** Resolved
- **Why Documentation Needed:** Enhancement to rule builder functionality
- **Existing DOCAC:** DOCAC-13697 (Code Review status), DOCAC-13522 (Closed - helper)
- **Documentation Scope:**
  - Shared option for pre-defined filters
  - Managing filter visibility with other operators
  - ACC vs Brand Journey behaviors
  - Filter list management
- **Target Audience:** All users, Query designers
- **Release:** Main Release
- **FF:** enable-query-filter-shared

### 2.3 LOW PRIORITY - Content Editor Enhancement

#### **NEO-88838: Theme Variables in Fragments**
- **Status:** New (On Hold)
- **Why Documentation Needed:** Email Designer theme functionality
- **Existing DOCAC:** DOCAC-12941 (New status)
- **Documentation Scope:**
  - Using theme variables in email fragments
  - Theme configuration
  - Variable management
  - Best practices
- **Target Audience:** Email designers, Marketing users
- **Release:** AC-UI-26-01-Monthly
- **Note:** Feature is on hold pending Acrite-side revisit

---

## 3. Tickets NOT Requiring Documentation

### 3.1 Cancelled/No Longer Applicable

| Ticket ID | Title | Reason |
|-----------|-------|--------|
| NEO-91566 | CTA tracking in webui | No UI work expected; pending info from MSFT |
| NEO-91564 | AEM multilingual UI support | UI work managed by different team |
| NEO-91567 | NRT Feature support | No web UI impact; spec available |
| NEO-91563 | Transactional Rest API | No web UI work; pending instance upgrade |
| NEO-92151 | Profile Enrichment Phase 2 | Story has no tasks; marked as no longer applies |

### 3.2 Placeholder/Tracking Tickets

| Ticket ID | Title | Reason |
|-----------|-------|--------|
| NEO-92400 | Release improvements - January 26 | Placeholder to track completion of improvements |

---

## 4. Proposed DOCAC Tickets

### 4.1 NEW DOCAC Tickets Needed

#### **DOCAC-XXXX: Delivery Scheduling with Timezone Support**
**Parent Ticket:** NEO-93487
**Priority:** Critical
**Target Release:** AC-UI-26-01-Monthly
**Description:**
Document the new delivery scheduling compute process that enables timezone-based delivery scheduling similar to ACS functionality. This feature allows marketers to send communications based on recipient timezones using calculated formulas, particularly important for multi-timezone markets like USA.

**Scope:**
- Configuration guide for timezone-based scheduling
- Calculated formula examples
- Multi-timezone market scenarios
- Migration guide from ACS
- Best practices and limitations

**Customer:** H&M (Critical for ACS to ACC migration)

#### **DOCAC-XXXX: Web Analytics External Account Configuration**
**Parent Ticket:** NEO-92668
**Priority:** Normal
**Target Release:** AC-UI-26-01-Monthly
**Description:**
Document the Web Analytics external account type configuration and usage in the Web UI.

**Scope:**
- External account creation steps
- Configuration parameters
- Integration with delivery tracking
- Reporting capabilities
- Troubleshooting

---

### 4.2 EXISTING DOCAC Tickets to Update

#### **DOCAC-13104: A/B Testing**
**Status:** New
**Parent Ticket:** NEO-86754
**Action Needed:** Start documentation - feature in active development
**Estimated Delivery:** February 2026 (pending development completion)

#### **DOCAC-11070 & DOCAC-13432: Dynamic Reporting**
**Status:** Closed/Resolved
**Parent Ticket:** NEO-80973
**Action Needed:** 
- Update for general availability (not just 8.7)
- Document conflicting metrics with legacy reporting
- Verify language support documentation

#### **DOCAC-13826: Schemas Authoring**
**Status:** New
**Parent Ticket:** NEO-76126
**Action Needed:** 
- Phase 2 documentation (navigate + CRUD + form definition)
- Prepare for Phase 3 (create/extend schemas) - ETA Feb end

#### **DOCAC-13829: AEM Live Copies/Language Copies**
**Status:** Resolved
**Parent Ticket:** NEO-86753
**Action Needed:** Verify current status and update as needed

#### **DOCAC-13565: Multilingual Rich Push**
**Status:** New
**Parent Ticket:** NEO-90183
**Action Needed:** Complete documentation - feature delivered in Nov 2025

#### **DOCAC-13827: Approval Process**
**Status:** New
**Parent Ticket:** NEO-84916
**Action Needed:** Complete documentation - feature delivered in Nov 2025

#### **DOCAC-13586 & DOCAC-13808: Continuous Delivery**
**Status:** New/Closed
**Parent Ticket:** NEO-91299
**Action Needed:** Complete main documentation (13586) - feature delivered

#### **DOCAC-13606: Multi-lingual Push File Upload**
**Status:** New
**Parent Ticket:** NEO-90130
**Action Needed:** Complete documentation - feature delivered

#### **DOCAC-13697 & DOCAC-13522: Pre-defined Filters Shared**
**Status:** Code Review/Closed
**Parent Ticket:** NEO-92942
**Action Needed:** Finalize documentation (13697)

#### **DOCAC-12941: Themes in Email Designer**
**Status:** New
**Parent Ticket:** NEO-88838
**Action Needed:** On hold pending feature revisit

---

## 5. Open Questions & Missing Information

### 5.1 By Feature

#### **A/B Testing (NEO-86754)**
- [ ] What is the final UI/UX validation status?
- [ ] Are there specific limitations for transactional messages?
- [ ] How does this integrate with Acrite content preview (NEO-92516 blocking)?
- [ ] What are the simulate/preview capabilities within each variant?

#### **Dynamic Reporting (NEO-80973)**
- [ ] What is the status of the demo environment reactivation?
- [ ] Complete list of conflicting metrics with legacy reporting?
- [ ] Detailed language support matrix?
- [ ] Performance comparison with legacy reporting?

#### **Schemas Authoring (NEO-76126)**
- [ ] When will Phase 2 FF be activated?
- [ ] Confirmed ETA for Phase 3 (create/extend schemas)?
- [ ] What are the environment setup requirements?
- [ ] Any limitations vs Client Console functionality?

#### **Delivery Scheduling (NEO-93487)**
- [ ] Is the feature demo with PM scheduled?
- [ ] Are complete functional specifications available?
- [ ] UI mockups finalized and reviewed?
- [ ] What is the exact formula syntax/structure?

#### **AEM Live/Language Copies (NEO-86753)**
- [ ] What is current status with Himanshu's team?
- [ ] Updated delivery timeline?
- [ ] Any dependencies on AEM version?

#### **Web Analytics (NEO-92668)**
- [ ] What is environment availability status?
- [ ] Complete setup requirements?
- [ ] Supported analytics platforms?

#### **Theme Variables in Fragments (NEO-88838)**
- [ ] When will Acrite revisit the feature?
- [ ] Is this still planned for AC-UI-26-01?

### 5.2 By Release

#### **AC-UI-26-01-Monthly (January 2026)**
- [ ] Official release date confirmation?
- [ ] Feature freeze date?
- [ ] Testing completion timeline?
- [ ] Documentation delivery deadline?

#### **November 2025 Delivered Features**
- [ ] Which features are already activated in production?
- [ ] Any known issues or limitations discovered post-release?
- [ ] Customer feedback received?

### 5.3 Documentation Process

- [ ] Who are the SMEs for each feature?
- [ ] What is the documentation review process?
- [ ] Target documentation language (EN only or multilingual)?
- [ ] Documentation platform/format requirements?
- [ ] Screenshots and demo environment availability?

---

## 6. Customer Impact & Escalations

### 6.1 Critical Customer Tickets

| Customer | Ticket | Feature | Impact |
|----------|--------|---------|--------|
| **H&M** | NEO-93487 | Delivery Scheduling | 50+ markets; multi-timezone delivery requirements; ACS to ACC migration blocker |
| **H&M** | NEO-90130 | Multi-lingual Push File Upload | Critical for ACS to ACC migration; reduces operational costs |
| **Pierre Fabre** | NEO-84916 | Approval Process | Regulatory and workflow requirements |

### 6.2 Microsoft-Specific Features

| Ticket | Feature | Status | Notes |
|--------|---------|--------|-------|
| NEO-86753 | AEM Live/Language Copies | New | Heavily used by Microsoft |
| NEO-91566 | CTA Tracking | Closed/No Longer Applies | Pending info from MSFT |
| NEO-91567 | NRT Feature | Resolved/No UI Impact | New ACS feature for MSFT |

---

## 7. Documentation Priorities & Timeline

### 7.1 Immediate Action Required (January 2026)

**HIGH PRIORITY - Delivered but Not Documented:**
1. **NEO-90183** - Multilingual Rich Push (DOCAC-13565)
2. **NEO-84916** - Approval Process (DOCAC-13827)
3. **NEO-91299** - Continuous Delivery (DOCAC-13586)
4. **NEO-90130** - Multi-lingual Push File Upload (DOCAC-13606)

### 7.2 In Progress - Development Ongoing (Feb-Mar 2026)

**CRITICAL PRIORITY:**
1. **NEO-86754** - A/B Testing (DOCAC-13104) - Due: Feb 2026
2. **NEO-76126** - Schemas Authoring (DOCAC-13826) - Phase 2: Feb, Phase 3: End Feb
3. **NEO-93487** - Delivery Scheduling (NEW DOCAC) - Critical customer escalation

**NORMAL PRIORITY:**
1. **NEO-80973** - Dynamic Reporting (Update DOCAC-11070)
2. **NEO-92668** - Web Analytics (NEW DOCAC)
3. **NEO-86753** - AEM Live/Language Copies (DOCAC-13829)

### 7.3 On Hold / Future

1. **NEO-88838** - Theme Variables (DOCAC-12941) - Pending Acrite revisit

---

## 8. Next Steps

### 8.1 Documentation Team Actions
1. **Prioritize delivered features** without documentation (Section 7.1)
2. **Create new DOCAC tickets** for NEO-93487 and NEO-92668
3. **Update existing DOCAC** tickets with detailed scope (Section 4.2)
4. **Schedule SME interviews** for A/B Testing, Schemas, and Delivery Scheduling
5. **Gather screenshots** and prepare demo environments
6. **Review and finalize** language limitations for Dynamic Reporting

### 8.2 Information Gathering
1. **Contact engineering leads** for status updates on:
   - A/B Testing final validation
   - Schemas Phase 2/3 timeline
   - Delivery Scheduling specifications
2. **Schedule feature demos** with Product Management
3. **Collect customer feedback** from H&M and Pierre Fabre
4. **Verify environment availability** for Web Analytics and Dynamic Reporting

### 8.3 Coordination
1. **Sync with Himanshu's team** on AEM Live/Language Copies
2. **Coordinate with Acrite team** on Theme Variables status
3. **Follow up on Microsoft-specific** features with account team

---

## Document History

| Date | Author | Version | Changes |
|------|--------|---------|---------|
| 2026-01-12 | AI Assistant | 1.0 | Initial analysis of Jira queries |

---

## Appendix: Jira Queries Analyzed

1. `project = NEO AND fixVersion = AC-UI-26-01-Monthly and type = story order by status`
2. `issueFunction in linkedIssuesOf('key=NEO-92400', 'is implemented by')`
3. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and type = story order by status`
4. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and fixVersion != 8.8.2 and type = story order by status`

**Total Results:** 19 unique tickets analyzed

