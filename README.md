# 🛡️ Case #001 – Windows Event Log Investigation

## Executive Summary

This repository documents a Windows Event Log investigation performed to identify and analyze authentication-related events using Windows Event Viewer.

The investigation focused on reviewing Security logs, filtering relevant Event IDs, examining event properties, and documenting findings following a structured SOC investigation methodology.

---

## Scenario

A Windows workstation exhibited unusual behavior.

The objective was to examine Windows Security Event Logs to determine whether suspicious authentication activity had occurred and document the investigation process.

---

## Environment

- Windows Operating System
- Windows Event Viewer
- Windows Security Logs

---

## Tools Used

- Windows Event Viewer
- Windows Security Logs
- GitHub

---

# Investigation

## Step 1 — Open Event Viewer

The investigation began by launching Windows Event Viewer and navigating to the Windows Security log, which records authentication and security-related events.

### Evidence

![Event Viewer Overview](screenshots/01-event-viewer-overview.png)

---

## Step 2 — Review Security Logs

The Security log was examined to identify recorded authentication events and obtain an overview of available security activity before filtering specific Event IDs.

### Evidence

![Security Log](screenshots/02-security-log.png)

---

## Step 3 — Filter Event ID 4625

The Security log was filtered using Event ID **4625**, which represents failed logon attempts.

Filtering allows investigators to quickly identify unsuccessful authentication events that may indicate password guessing, unauthorized access attempts, or user authentication failures.

### Evidence

![Filter Event ID 4625](screenshots/03-filter-eventid-4625.png)

---

## Step 4 — Review Event ID 4624

The investigation continued by reviewing Event ID **4624**, which represents successful logon events.

Successful authentication events help investigators understand user activity, verify legitimate logins, and establish an authentication timeline during an investigation.

### Evidence

![Event ID 4624](screenshots/04-eventid-4624-result.png)

---

## Step 5 — Inspect Event Properties

The General tab of the selected event was reviewed to collect important metadata including:

- Event ID
- Log Name
- Source
- Logged Time
- Task Category
- Keywords

These properties provide valuable context when validating authentication activity.

### Evidence

![Event Properties](screenshots/05-eventid-4624-properties.png)

---

## Step 6 — Analyze Event Details

The Details tab was examined to inspect structured event information including:

- Subject User SID
- Account Name
- Domain Information
- Logon ID
- Target User Information

Reviewing these details enables investigators to correlate authentication events and better understand user activity.

### Evidence

![Event Details](screenshots/06-eventid-4624-details.png)

---

# Findings

The investigation successfully identified Windows authentication events by reviewing Security logs and examining Event IDs related to user logon activity.

The collected event information provided sufficient evidence to understand authentication behavior and demonstrated how Windows Event Logs support incident investigations.

No indicators of malicious activity were confirmed during this investigation.

---

# Risk Assessment

| Category | Assessment |
|----------|------------|
| Likelihood | Low |
| Impact | Low |
| Overall Risk | Low |

The reviewed authentication events appeared consistent with normal Windows activity.

No evidence of unauthorized access or malicious behavior was identified during the investigation.

---

# Analyst's Conclusion

The investigation demonstrated the effectiveness of Windows Event Viewer for reviewing authentication activity and collecting forensic evidence.

By filtering Security logs, reviewing authentication events, and examining detailed event properties, investigators can efficiently validate user activity and support incident response procedures.

---

# Recommendations

- Monitor Windows Security logs regularly.
- Review authentication-related Event IDs during security investigations.
- Correlate multiple events instead of relying on a single log entry.
- Preserve relevant logs before performing remediation activities.
- Document investigation findings using a structured methodology.

---

# Lessons Learned

- Windows Event Logs provide valuable forensic evidence during investigations.
- Event filtering significantly improves investigation efficiency.
- Authentication events help establish user activity timelines.
- Structured documentation improves investigation quality and reproducibility.

---

# Skills Demonstrated

- Windows Event Log Analysis
- Security Log Investigation
- Authentication Event Analysis
- Event Correlation
- Evidence Collection
- Incident Documentation
- Windows Event Viewer
- SOC Investigation Methodology
