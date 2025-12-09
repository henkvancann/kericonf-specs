## Introduction KERISuite Conference Operations Handbook
### Purpose of This Handbook  
Provide a complete operational guide for planning and executing the KERISuite conference.

### Scope  
Covers the entire lifecycle:  
- Concept → Planning → Program → Execution → Afterwork  
- Includes privacy, logistics, sponsorships, communication, technical tooling.

### Roles and Responsibilities  
- Conference Lead  
- Track Leads  
- Program Coordinator  
- Sponsorship Coordinator  
- Communications & Privacy Officer  
- Website & Tooling Lead  
- Logistics Lead  
- Volunteer Coordinator  
- On-site Staff & Volunteers

---

## From Idea to Go/No-Go  
### Early Idea & Constraints  
#### Chicken-and-Egg Problem  
Sponsor → speakers → visitors.  
But if you only have a date and venue (no speakers or visitors yet), what can you do?

The KERICONF uses the concept of **[[ref: Tracks]]** and **[[ref: Lines]]** that connect directly to the conference’s objectives.  
This enables presenting a compelling **[[ref: Program]]** early on, even without confirmed speakers or sponsors.

This helps attract interest and overcome temporary lack of commitments.

> **Important:**  
> Until there is solid commitment from individuals or organizations, **privacy must always be considered.**

### Concept Definition  
(Create tracks, initial themes, high-level goals.)

### Feasibility Check  
Budget, attendance expectations, sponsor viability, resource availability.

### Go/No-Go Decision  
Document assumptions, risks, and confirmation.

---

## Core Framework  
### Tracks and Lines  
Framework for building a program skeleton without confirmed speakers.

### Early Program Skeleton  
Enables publishing an attractive outline early in the process.

---

## Program Development  
### Single Source of Truth (SSOT)

::: todo Really Important  
Please edit program content in merge letters, emails, PDFs, and on the website **always in the single source of truth**,  
and not (only) in the expression at hand.  
:::

#### SSOT Location  
> Google Sheet (2026 version):  
> https://docs.google.com/spreadsheets/d/1bET8KvpFACJFyAIv6g0c6RSvCOg2midnu4gwI5oOOLg/edit  

> **Tab: “Talks”**

### Mail Merge Workflow  
1. Edit content in the Google Sheet  
2. Export the correct view as CSV  
3. Refresh the CSV in the Word merge document  
4. Finalize output and validate fields  
5. Iterate until correct  

### Program Publication Pipeline  
(Connected later with privacy rules in Section 5.)

---

## Privacy & Data Handling  
### General Privacy Principles  
As ideas evolve about **[[ref: Topics]]** and potential **[[ref: Speakers]]**, care must be taken when publishing online.

### Placeholders & Obfuscation  
Before mutual agreement exists (sponsorship, talk, support, attendance):  
- Use placeholders  
- Keep all information obfuscated  

::: info  
“A Dutch airline starting with a ‘K’…” is **not** good obfuscation.  
:::

### Google Sheets & PII 
We use Google Sheets and rely on their privacy statement:  
- https://support.google.com/docs/answer/10381817  
- https://workspace.google.com/terms/09242021/dpa_terms/  
- ChatGPT analysis 2025: https://chatgpt.com/share/692b081e-a584-800a-9941-73436b1df607

We intentionally **do not store sensitive data** in Google Sheets.

**Insensitive (allowed) data:**  
- email  
- names  

### Publishing From Google Sheets to kericonf.com  
We use views and automated scripts to publish program data to the website.

The scripts:  
- Preserve privacy  
- Only reveal PII when a status level is sufficiently high (Appointed / Received / Confirmed)

#### Example Script
```text
=MAP(Talks!K3:K39, Talks!G3:G39, Talks!S3:S39,
 LAMBDA(y, x, z,
  IF(
   OR(z="APPOINTED", z="RECEIVED", z="CONFIRMED"),
   IF(
    y="","",
    REGEXREPLACE(
      y,
      "\{([^}]+)\}",
      LAMBDA(key,
        IF(
          x="",
          "",
          REGEXEXTRACT(x, key & "=(.*)")
        )
      )(REGEXEXTRACT(y,"\{([^}]+)\}"))
    )
   ),
   y
  )
 ))
```
What is does, is it only replaces a variable with the actual [[ref: pii]] when the status of a Talk has a sufficient level. ### GitHub 

 - **Issues** - Source: https://github.com/blockchainbird/kericonf-specs/issues/
 - **Pull Requests** - Source: https://github.com/blockchainbird/kericonf-specs/pull/
 - **Repo** - Source: https://github.com/blockchainbird/kericonf-specs/
- **Render**: https://blockchainbird.github.io/kericonf-specs/index.html
  
### Obfuscation & Placeholders  
Procedure for pre-confirmation representation.

### Publication Rules  
Conditions for publishing names, bios, affiliations.

### Compliance  
- Google Workspace privacy  
- Internal KERI/Suite data policy

## Sponsorships  
### Sponsorship Model  
Types of packages, benefits, exposure rules.

### Outreach Workflow  
Templates, timelines, approval flows.

### Contracting & Commitments  
Storage, SSOT integration, publication permissions.

## Speaker Management  
### Invitation Process  
Draft invite → outreach → follow-up → confirmation.

### Speaker Data Requirements  
Bio, title, abstract, picture (optional), affiliation.

### Logistics for Speakers  
Travel arrangements (if applicable), hotel suggestions, reimbursements.

### Publication Rules  
What can be published and when.

## Communications  
### Internal Communications  
Slack, email, GitHub workflow.

### External Communications  
Website, newsletters, social media.

### Style & Tone Guidelines  
Voice, terminology, expectations.

## Technical Infrastructure  
### GitHub Repositories  
Issues, PR workflow, documentation standards.

### Website  
Data pipeline, publishing scripts, staging vs production.

### Registration & Ticketing Tools  
Setup, reporting, privacy considerations.

## Logistics  
### Venue Planning  
- Rooms, capacities, seating layouts  
- AV equipment, recording, live streaming  
- Accessibility requirements  
- Emergency procedures  

### Schedule & Room Allocation  
Link SSOT → website → printed schedules → signage.

### Signage & Wayfinding  
Directional posters, room labels, registration signage.

### Volunteer Roles  
Registration desk, room hosts, speaker support, Q&A helpers.

## Catering  
### Catering Strategy  
- Coffee/tea service  
- Lunch setup  
- Snacks and breaks  
- Balanced dietary choices  

### Dietary Requirements  
Collecting and communicating requirements to caterers.

### Vendor Coordination  
Deadlines, delivery windows, on-site contact.

### On-site Food Logistics  
Buffet layout, waste management, refill schedule.

## Transport  
### Transport for Participants  
- Local public transport information  
- Taxi availability  
- Shuttle options (if provided)  

### Speaker / VIP Transport  
- Airport pickup (if applicable)  
- Reimbursement policy  
- Travel schedule synchronization  

### Accessibility Transport  
Wheelchair-accessible transport options.

## Hotels  
### Recommended Hotels  
List based on:  
- Distance to venue  
- Price category  
- Breakfast availability  
- Cancellation policy  

### Speaker & VIP Booking  
Block reservations, deadlines, confirmation handling.

### Accommodation Information Page  
Ensure hotels are listed on the website with:  
- Maps  
- Estimated walking times  
- Public transport lines  

## Conference Execution  
### Day-by-Day Timeline  
- Setup  
- Opening  
- Sessions  
- Breaks  
- Closing  
- Cleanup  

### Issue Handling  
Escalation procedure, role assignments.

### Safety & Security  
First-aid, emergency contacts, evacuation plan.

## Afterwork / Post-Event  
### Wrap-up Deliverables  
- Publish slides (if permitted)  
- Thank-you emails  
- Social media recap  

### Evaluation  
- Attendee feedback  
- Internal debrief  
- Sponsor follow-up  

### Financial Close  
Invoices, reimbursements, final budget.

### Archiving  
Store SSOT, contracts, receipts, decisions, slides.

### Kickoff for Next Year  
Review improvements and update tracks/lines.

## Appendices  
### Templates  
Invitations, sponsor decks, privacy statements, volunteer briefings.

### Tools Index  
Google Sheets, GitHub, website scripts, registration system, communication channels.

### Glossary  
Tracks, Lines, PII, SSOT, statuses, roles.
