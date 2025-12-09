# KERISuite Conference Operations Handbook  
*A specification for organising the conference from early idea to afterwork*

---

## 1. Introduction  
### 1.1 Purpose of This Handbook  
Provide a complete operational guide for planning and executing the KERISuite conference.

### 1.2 Scope  
Covers the entire lifecycle:  
- Concept → Planning → Program → Execution → Afterwork  
- Includes privacy, logistics, sponsorships, communication, technical tooling.

### 1.3 Roles and Responsibilities  
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

## 2. From Idea to Go/No-Go  
### 2.1 Early Idea & Constraints  
#### Chicken-and-Egg Problem  
Sponsor → speakers → visitors.  
But if you only have a date and venue (no speakers or visitors yet), what can you do?

The KERICONF uses the concept of **[[ref: Tracks]]** and **[[ref: Lines]]** that connect directly to the conference’s objectives.  
This enables presenting a compelling **[[ref: Program]]** early on, even without confirmed speakers or sponsors.

This helps attract interest and overcome temporary lack of commitments.

> **Important:**  
> Until there is solid commitment from individuals or organizations, **privacy must always be considered.**

### 2.2 Concept Definition  
(Create tracks, initial themes, high-level goals.)

### 2.3 Feasibility Check  
Budget, attendance expectations, sponsor viability, resource availability.

### 2.4 Go/No-Go Decision  
Document assumptions, risks, and confirmation.

---

## 3. Core Framework  
### 3.1 Tracks and Lines  
Framework for building a program skeleton without confirmed speakers.

### 3.2 Early Program Skeleton  
Enables publishing an attractive outline early in the process.

---

## 4. Program Development  
### 4.1 Single Source of Truth (SSOT)

::: todo Really Important  
Please edit program content in merge letters, emails, PDFs, and on the website **always in the single source of truth**,  
and not (only) in the expression at hand.  
:::

#### SSOT Location  
> Google Sheet (2026 version):  
> https://docs.google.com/spreadsheets/d/1bET8KvpFACJFyAIv6g0c6RSvCOg2midnu4gwI5oOOLg/edit  

> **Tab: “Talks”**

### 4.2 Mail Merge Workflow  
1. Edit content in the Google Sheet  
2. Export the correct view as CSV  
3. Refresh the CSV in the Word merge document  
4. Finalize output and validate fields  
5. Iterate until correct  

### 4.3 Program Publication Pipeline  
(Connected later with privacy rules in Section 5.)

---

## 5. Privacy & Data Handling  
### 5.1 General Privacy Principles  
As ideas evolve about **[[ref: Topics]]** and potential **[[ref: Speakers]]**, care must be taken when publishing online.

### 5.2 Placeholders & Obfuscation  
Before mutual agreement exists (sponsorship, talk, support, attendance):  
- Use placeholders  
- Keep all information obfuscated  

::: info  
“A Dutch airline starting with a ‘K’…” is **not** good obfuscation.  
:::

### 5.3 Google Sheets & PII  
We use Google Sheets and rely on their privacy statement:  
- https://support.google.com/docs/answer/10381817  
- https://workspace.google.com/terms/09242021/dpa_terms/  
- ChatGPT analysis 2025: https://chatgpt.com/share/692b081e-a584-800a-9941-73436b1df607

We intentionally **do not store sensitive data** in Google Sheets.

**Insensitive (allowed) data:**  
- email  
- names  

### 5.4 Publishing From Google Sheets to kericonf.com  
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
  
### 5.3 Obfuscation & Placeholders  
Procedure for pre-confirmation representation.

### 5.4 Publication Rules  
Conditions for publishing names, bios, affiliations.

### 5.5 Compliance  
- Google Workspace privacy  
- Internal KERI/Suite data policy

---

## 6. Sponsorships  
### 6.1 Sponsorship Model  
Types of packages, benefits, exposure rules.

### 6.2 Outreach Workflow  
Templates, timelines, approval flows.

### 6.3 Contracting & Commitments  
Storage, SSOT integration, publication permissions.

---

## 7. Speaker Management  
### 7.1 Invitation Process  
Draft invite → outreach → follow-up → confirmation.

### 7.2 Speaker Data Requirements  
Bio, title, abstract, picture (optional), affiliation.

### 7.3 Logistics for Speakers  
Travel arrangements (if applicable), hotel suggestions, reimbursements.

### 7.4 Publication Rules  
What can be published and when.

---

## 8. Communications  
### 8.1 Internal Communications  
Slack, email, GitHub workflow.

### 8.2 External Communications  
Website, newsletters, social media.

### 8.3 Style & Tone Guidelines  
Voice, terminology, expectations.

---

## 9. Technical Infrastructure  
### 9.1 GitHub Repositories  
Issues, PR workflow, documentation standards.

### 9.2 Website  
Data pipeline, publishing scripts, staging vs production.

### 9.3 Registration & Ticketing Tools  
Setup, reporting, privacy considerations.

---

## 10. Logistics  
### 10.1 Venue Planning  
- Rooms, capacities, seating layouts  
- AV equipment, recording, live streaming  
- Accessibility requirements  
- Emergency procedures  

### 10.2 Schedule & Room Allocation  
Link SSOT → website → printed schedules → signage.

### 10.3 Signage & Wayfinding  
Directional posters, room labels, registration signage.

### 10.4 Volunteer Roles  
Registration desk, room hosts, speaker support, Q&A helpers.

---

## 11. Catering  
### 11.1 Catering Strategy  
- Coffee/tea service  
- Lunch setup  
- Snacks and breaks  
- Balanced dietary choices  

### 11.2 Dietary Requirements  
Collecting and communicating requirements to caterers.

### 11.3 Vendor Coordination  
Deadlines, delivery windows, on-site contact.

### 11.4 On-site Food Logistics  
Buffet layout, waste management, refill schedule.

---

## 12. Transport  
### 12.1 Transport for Participants  
- Local public transport information  
- Taxi availability  
- Shuttle options (if provided)  

### 12.2 Speaker / VIP Transport  
- Airport pickup (if applicable)  
- Reimbursement policy  
- Travel schedule synchronization  

### 12.3 Accessibility Transport  
Wheelchair-accessible transport options.

---

## 13. Hotels  
### 13.1 Recommended Hotels  
List based on:  
- Distance to venue  
- Price category  
- Breakfast availability  
- Cancellation policy  

### 13.2 Speaker & VIP Booking  
Block reservations, deadlines, confirmation handling.

### 13.3 Accommodation Information Page  
Ensure hotels are listed on the website with:  
- Maps  
- Estimated walking times  
- Public transport lines  

---

## 14. Conference Execution  
### 14.1 Day-by-Day Timeline  
- Setup  
- Opening  
- Sessions  
- Breaks  
- Closing  
- Cleanup  

### 14.2 Issue Handling  
Escalation procedure, role assignments.

### 14.3 Safety & Security  
First-aid, emergency contacts, evacuation plan.

---

## 15. Afterwork / Post-Event  
### 15.1 Wrap-up Deliverables  
- Publish slides (if permitted)  
- Thank-you emails  
- Social media recap  

### 15.2 Evaluation  
- Attendee feedback  
- Internal debrief  
- Sponsor follow-up  

### 15.3 Financial Close  
Invoices, reimbursements, final budget.

### 15.4 Archiving  
Store SSOT, contracts, receipts, decisions, slides.

### 15.5 Kickoff for Next Year  
Review improvements and update tracks/lines.

---

## 16. Appendices  
### 16.1 Templates  
Invitations, sponsor decks, privacy statements, volunteer briefings.

### 16.2 Tools Index  
Google Sheets, GitHub, website scripts, registration system, communication channels.

### 16.3 Glossary  
Tracks, Lines, PII, SSOT, statuses, roles.
