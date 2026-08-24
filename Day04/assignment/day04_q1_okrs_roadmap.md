# Day 04 – Q1: OKRs, Initiatives, CUJ and Roadmap

## Strategic Intent

> Become the most reliable, zero-downtime database platform for high-growth SaaS startups within 12 months, measured by uptime percentage and recovery speed — not by product breadth.

---

# 1. OKRs

## Objective

Become the most reliable, zero-downtime database platform for high-growth SaaS startups.

| Key Result | Baseline | Target |
|---|---:|---:|
| KR1 – Improve platform uptime | 99.5% | 99.99% |
| KR2 – Reduce Mean Time to Recovery (MTTR) | 45 min | 10 min |
| KR3 – Reduce critical database incidents | 20/month | 5/month |

---

# 2. Initiatives

## KR1 – Improve platform uptime to 99.99%

- Multi-region database failover
- Automated health monitoring
- Eliminate single points of failure

## KR2 – Reduce MTTR from 45 minutes to 10 minutes

- Automated incident detection
- Automated recovery procedures
- Improve alerting and escalation

## KR3 – Reduce critical incidents from 20/month to 5/month

- Proactive database health monitoring
- Root-cause analysis for recurring incidents
- Regular failure and recovery testing

---

# 3. CUJ Walkthrough

## CUJ – Database Failure Recovery

### Screen 1 – Reliability Dashboard

The dashboard displays:

- Current uptime
- Database health
- Active incidents
- Recovery status
- MTTR

**User Action:** Monitor database platform health.

### Screen 2 – Incident Alert

The system detects a database failure and displays:

- Incident ID
- Affected database
- Severity
- Time detected
- Current status

**User Action:** Open the incident and begin recovery.

### Screen 3 – Incident Diagnosis

The platform provides:

- Root-cause information
- Affected services
- Database status
- Recommended recovery action

**User Action:** Review the problem and initiate recovery/failover.

### Screen 4 – Failover / Recovery

The system displays:

- Recovery progress
- Current database status
- Failover status
- Estimated recovery completion

**User Action:** Monitor the recovery process.

### Screen 5 – Recovery Complete

The system displays:

- Database status: Healthy
- Recovery completed
- Recovery time
- Updated uptime information

**User Action:** Confirm that the service is available.

---

# 4. Summary Roadmap

| Period | Key Result | Major Initiatives |
|---|---|---|
| Q1 | Establish reliability baseline | Monitoring, health metrics, incident tracking |
| Q2 | Improve uptime toward 99.9%+ | Multi-region failover, redundancy |
| Q3 | Reduce MTTR toward 10 min | Automated detection, recovery automation |
| Q4 | Reach 99.99% uptime and reduce critical incidents | Failure testing, optimization, proactive reliability |

## Overall Roadmap

```text
Q1
Baseline & Monitoring
        ↓
Q2
High Availability & Failover
        ↓
Q3
Recovery Automation
        ↓
Q4
Zero-Downtime Reliability
