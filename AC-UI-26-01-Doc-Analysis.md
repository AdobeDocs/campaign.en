# AC-UI-26-01 Documentation Analysis

## Next Release Content

This document analyzes product JIRAs for the AC-UI-26-01 and AC-UI-25-11 monthly releases to plan documentation actions.

### JIRA Filters

1. **[AC-UI-26-01-Monthly Stories](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-26-01-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - Main release stories
2. **[NEO-92400 Improvements](https://jira.corp.adobe.com/issues/?jql=issueFunction%20in%20linkedIssuesOf(%27key%3DNEO-92400%27%2C%20%27is%20implemented%20by%27))** - Release improvements linked issues
3. **[AC-UI-25-11-Monthly Stories](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - Previous release carryover
4. **[AC-UI-25-11 Excluding 8.8.2](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20fixVersion%20!%3D%208.8.2%20and%20type%20%3D%20story%20order%20by%20status)** - Filtered previous release

---

## 🟢 Create DOCAC

### [NEO-91565](https://jira.corp.adobe.com/browse/NEO-91565) - Add support for personalisation fields (Advanced AEM Integration)
**Status:** Resolved  
**Doc Required:** Yes  
**Existing DOCAC:** None  
**Action:** Create DOCAC

**Scope:**
- Document support for personalization fields in Advanced AEM Integration
- UI workflow and configuration steps
- AEM multilingual integration capabilities

**Feature Description:**
Support for adding personalization fields in deliveries using Advanced AEM Integration, enabling dynamic content insertion from Campaign data into AEM-authored email templates.

**Context:** ACS to ACC parity, MSFT-specific requirement

**References:** [AEM multilingual wiki](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=2988189953)

---

### [NEO-93487](https://jira.corp.adobe.com/browse/NEO-93487) - Delivery scheduling compute process (ACS parity)
**Status:** New  
**Doc Required:** Yes  
**Existing DOCAC:** None  
**Action:** Create DOCAC

**Scope:**
- Document delivery scheduling compute process for push notifications
- Timezone-based scheduling formulas
- File upload for multi-timezone targeting

**Feature Description:**
Enable OOTB file-based delivery scheduling with computed send times based on recipient timezone, allowing single delivery targeting across multiple timezones with optimized send times per region.

**Context:** Customer-driven (H&M), ACS to ACC parity requirement

**References:** [ACS documentation](https://experienceleague.adobe.com/en/docs/campaign-standard/using/testing-and-sending/scheduling-messages/computing-the-sending-date)

---

## 🔄 Update DOCAC

### [NEO-80973](https://jira.corp.adobe.com/browse/NEO-80973) - Dynamic Reporting availability for all web UI users
**Status:** In Progress  
**Doc Required:** Yes  
**Existing DOCAC:** [DOCAC-11070](https://jira.corp.adobe.com/browse/DOCAC-11070) (Closed), [DOCAC-13432](https://jira.corp.adobe.com/browse/DOCAC-13432) (Resolved)  
**Action:** Review DOCAC

**Scope:**
- Update availability information (now for all Web UI users, not just 8.7)
- Document language limitations
- Clarify conflictual metrics display with legacy reporting

**Feature Description:**
Dynamic Reporting is now available for all Campaign Web UI users (previously limited to 8.7 ACS to ACC customers), providing advanced analytics and custom reporting capabilities with ACS-style interface.

**Context:** Feature expansion, backend build dependency (8.8.1)

**References:** [Wiki - Reports comparison](https://wiki.corp.adobe.com/display/~kumarvishal/Reports+-+Client+console+vs+WebUI)

---

### [NEO-86754](https://jira.corp.adobe.com/browse/NEO-86754) - A/B Testing
**Status:** In Progress  
**Doc Required:** Yes  
**Existing DOCAC:** [DOCAC-13104](https://jira.corp.adobe.com/browse/DOCAC-13104) (New)  
**Action:** Update DOCAC

**Scope:**
- Complete A/B testing workflow documentation
- Content experimentation setup and variant configuration
- Sample proportion definition and winner selection criteria
- Statistics collection and evaluation

**Feature Description:**
Content experimentation and A/B testing for email deliveries, enabling marketers to test different content variants, define sample sizes, collect performance statistics, and automatically send the winning variant to remaining recipients.

**Context:** Europa project, Microsoft requirement, feature flag enabled

**References:** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=3017705719), [Figma mocks](https://www.figma.com/design/4EfXEaA6OIV0D8rauuXSWX/A-B-Testing)

---

### [NEO-76126](https://jira.corp.adobe.com/browse/NEO-76126) - Schemas authoring (create new table, extend schemas, access external DB)
**Status:** In Progress  
**Doc Required:** Yes  
**Existing DOCAC:** [DOCAC-13826](https://jira.corp.adobe.com/browse/DOCAC-13826) (New)  
**Action:** Update DOCAC

**Scope:**
- Document schema authoring workflow (3 options only: create table, extend schema, access external DB)
- Form definition for custom entities
- Navigate and CRUD operations on custom schemas
- Phase 2 and Phase 3 capabilities

**Feature Description:**
Schema authoring capabilities in Web UI allowing administrators to create new database tables, extend existing schemas with custom fields, and connect to external databases - essential for data model customization.

**Context:** Microsoft requirement, Europa project, phased delivery (Phase 2 active, Phase 3 Feb end)

**References:** [PRD](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=AC+Web+UI+-+Schemas+PRD), [Figma](https://www.figma.com/design/lZkJso2HvXPbNjG0TmQTrC/Schemas)

---

### [NEO-92668](https://jira.corp.adobe.com/browse/NEO-92668) - Web Analytics
**Status:** New  
**Doc Required:** Yes  
**Existing DOCAC:** None  
**Action:** Create DOCAC

**Scope:**
- Web Analytics external account configuration
- Integration setup and authentication
- Analytics data usage in campaigns

**Feature Description:**
Web Analytics integration enabling connection to web analytics platforms for tracking and reporting on campaign performance and website visitor behavior.

**Context:** Customer request (P2E-RSC), pending environment availability

**References:** None provided

---

### [NEO-86753](https://jira.corp.adobe.com/browse/NEO-86753) - AEM integration for Live copies/Language copies
**Status:** New  
**Doc Required:** Yes  
**Existing DOCAC:** [DOCAC-13829](https://jira.corp.adobe.com/browse/DOCAC-13829) (Resolved)  
**Action:** Review DOCAC

**Scope:**
- Browse AEM delivery templates
- Create Live copies and Language copies with one click
- Multilingual content variant creation workflow

**Feature Description:**
Streamlined AEM integration allowing one-click creation of Live copies and Language copies from AEM delivery templates, simplifying multilingual campaign creation for AEM users.

**Context:** Microsoft requirement, work transferred to Himanshu's team

**References:** [ACS documentation](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-experience-manager/creating-multilingual-email-aem.html)

---

### [NEO-88838](https://jira.corp.adobe.com/browse/NEO-88838) - Content Editor: Use theme variables in fragment
**Status:** New  
**Doc Required:** Yes  
**Existing DOCAC:** [DOCAC-12941](https://jira.corp.adobe.com/browse/DOCAC-12941) (New)  
**Action:** Update DOCAC

**Scope:**
- Theme variables in email designer (Beta)
- Using themes in fragments
- Acrite feature activation

**Feature Description:**
Support for using theme variables within content fragments, enabling consistent branding and design system application across email components with centralized theme management.

**Context:** On hold, Acrite feature to be revisited

**References:** [ATU-5460](https://jira.corp.adobe.com/browse/ATU-5460)

---

## ➕ Create DOCAC (Improvements)

### [NEO-92942](https://jira.corp.adobe.com/browse/NEO-92942) - Pre-defined filters - Shared option
**Status:** Resolved  
**Doc Required:** Yes  
**Existing DOCAC:** [DOCAC-13697](https://jira.corp.adobe.com/browse/DOCAC-13697) (Code Review), [DOCAC-13522](https://jira.corp.adobe.com/browse/DOCAC-13522) (Closed - Helper)  
**Action:** Review DOCAC

**Scope:**
- Shared option for pre-defined filters
- Filter visibility with other operators (ACC vs Brand Journey behavior)
- User management of shared filters

**Feature Description:**
Pre-defined filters can now be marked as "shared" to make them visible to other operators, with different behavior for ACC (default) and Brand Journey (user-specific filtering).

**Context:** Rule builder enhancement, feature flag: enable-query-filter-shared

**References:** Related to [NEO-88441](https://jira.corp.adobe.com/browse/NEO-88441)

---

### [NEO-91299](https://jira.corp.adobe.com/browse/NEO-91299) - Continuous delivery activity
**Status:** Closed  
**Doc Required:** Yes  
**Existing DOCAC:** [DOCAC-13586](https://jira.corp.adobe.com/browse/DOCAC-13586) (New), [DOCAC-13808](https://jira.corp.adobe.com/browse/DOCAC-13808) (Closed - contextual help)  
**Action:** Update DOCAC

**Scope:**
- Continuous delivery workflow activity
- Delivery template picker configuration
- Automatic outbound transition generation
- Targeting options (no content access)

**Feature Description:**
Continuous delivery activity for workflows enables recurring delivery execution from templates, automatically generating outbound transitions for workflow orchestration without content modification.

**Context:** Feature flag: enable-continuous-delivery

**References:** Related epic [NEO-67972](https://jira.corp.adobe.com/browse/NEO-67972)

---

### [NEO-90130](https://jira.corp.adobe.com/browse/NEO-90130) - Enable OOTB File Upload for Multi-lingual Push Notifications
**Status:** Closed  
**Doc Required:** Yes  
**Existing DOCAC:** [DOCAC-13606](https://jira.corp.adobe.com/browse/DOCAC-13606) (New)  
**Action:** Update DOCAC

**Scope:**
- File upload for multilingual push notifications (iOS and Android)
- CSV format and field mapping
- Rich push support with multilingual capabilities

**Feature Description:**
OOTB file upload capability for creating multi-lingual push notification deliveries via CSV import, matching ACS functionality and enabling efficient multilingual campaign configuration.

**Context:** Customer-driven (H&M), ACS to ACC parity, critical for migration

**References:** [ACS documentation](https://experienceleague.adobe.com/en/docs/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push)

---

## ❌ Cancelled / No Longer Applies

### [NEO-91566](https://jira.corp.adobe.com/browse/NEO-91566) - Support for CTA tracking in webui
**Status:** Closed (No Longer Applies)  
**Doc Required:** No  
**Existing DOCAC:** [DOCAC-13821](https://jira.corp.adobe.com/browse/DOCAC-13821) (New)  
**Action:** Close DOCAC

**Reason:** New ACS feature to support MSFT - not started, pending info from MSFT, no UI work expected

**Context:** Microsoft-specific, CTA tracking requirement

---

### [NEO-91564](https://jira.corp.adobe.com/browse/NEO-91564) - AEM multilingual UI support
**Status:** Closed (No Longer Applies)  
**Doc Required:** No  
**Existing DOCAC:** [DOCAC-13822](https://jira.corp.adobe.com/browse/DOCAC-13822) (New)  
**Action:** Close DOCAC

**Reason:** UI work managed by Himanshu's team (different story)

**Context:** Microsoft requirement, work transferred

---

### [NEO-91567](https://jira.corp.adobe.com/browse/NEO-91567) - Add support for NRT Feature
**Status:** Resolved (No Longer Applies)  
**Doc Required:** No  
**Existing DOCAC:** [DOCAC-13824](https://jira.corp.adobe.com/browse/DOCAC-13824) (New)  
**Action:** Close DOCAC

**Reason:** New ACS specific feature for MSFT - spec available but no web UI impact

**Context:** Microsoft requirement, transactional messaging

---

### [NEO-91563](https://jira.corp.adobe.com/browse/NEO-91563) - Transactional Rest API for Profile Based Enrichment
**Status:** Resolved (No Longer Applies)  
**Doc Required:** No  
**Existing DOCAC:** [DOCAC-13825](https://jira.corp.adobe.com/browse/DOCAC-13825) (New)  
**Action:** Close DOCAC

**Reason:** No web UI work, pending upgraded instance, build upgrade mandatory for release

**Context:** REST API endpoint feature

---

### [NEO-92151](https://jira.corp.adobe.com/browse/NEO-92151) - Profile based Enrichment Transactional Messaging Phase 2
**Status:** Resolved (No Longer Applies)  
**Doc Required:** No  
**Existing DOCAC:** [DOCAC-13823](https://jira.corp.adobe.com/browse/DOCAC-13823) (New)  
**Action:** Close DOCAC

**Reason:** Story has no tasks, marked as "no longer applies"

**Context:** Microsoft requirement, Europa project

---

## 🟢 Documentation Ready (From AC-UI-25-11)

### [NEO-90183](https://jira.corp.adobe.com/browse/NEO-90183) - Multilingual Rich Push - UI
**Status:** Closed  
**Doc Required:** Yes  
**Existing DOCAC:** [DOCAC-13565](https://jira.corp.adobe.com/browse/DOCAC-13565) (New)  
**Action:** Review DOCAC

**Scope:**
- Rich push fields for multilingual deliveries
- iOS and Android platform support
- Template and content configuration

**Feature Description:**
Rich push notification support with multilingual capabilities, allowing marketers to create enhanced push notifications with images, buttons, and rich media for both iOS and Android in multiple languages.

**Context:** Customer-driven (H&M), delivered in 25-11, backend work completed

**References:** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=Rich+push+fields+in+multilingual)

---

### [NEO-84916](https://jira.corp.adobe.com/browse/NEO-84916) - Set up and manage the approval process
**Status:** Resolved  
**Doc Required:** Yes  
**Existing DOCAC:** [DOCAC-13827](https://jira.corp.adobe.com/browse/DOCAC-13827) (New)  
**Action:** Update DOCAC

**Scope:**
- Configure validation operators in delivery/campaign
- Approval workflow setup
- Content and target approval process
- Multi-channel support (email, SMS, push, direct mail, call center, custom)

**Feature Description:**
Approval process management enabling validation workflows for delivery content and targeting, with operator assignment and approval tracking across all delivery channels.

**Context:** Customer-driven (Pierre Fabre), Microsoft requirement, dev complete and in test

**References:** [Classic documentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval), [Figma mocks](https://www.figma.com/design/r2vpqXoVyI3aucKgkt8TLN/Approvals)

---

## 📊 Summary by Action

| Action | Count |
|--------|-------|
| 🟢 Create DOCAC | 3 |
| 🔄 Update DOCAC | 6 |
| ✅ Review DOCAC | 3 |
| ❌ Close DOCAC | 5 |
| **Total** | **17** |

---

## ⚠️ Open Questions

1. NEO-93487 - H&M escalation - needs urgent attention for scheduling compute process
2. NEO-92668 - Web Analytics - waiting for environment availability before documentation can be completed
3. NEO-76126 - Schemas Phase 3 - ETA Feb end, need separate documentation story
4. NEO-88838 - Theme variables - on hold pending Acrite feature revision
5. Dynamic Reporting - clarify conflictual metrics display guidance with legacy reporting

---

## 🔗 Related Epics

- NEO-85263 - ACS to ACC (EUROPA) parent epic
- NEO-67972 - Workflow improvements
- NEO-87980 - Advanced AEM Integration
- NEO-90199 - Dynamic Reporting release readiness
- NEO-63067 - Content experimentation UX/UI
- NEO-67726 - A/B testing and content experimentation
- NEO-85274 - Schema and form (Phase 2)
- NEO-87993 - Schema and form (Phase 3)
