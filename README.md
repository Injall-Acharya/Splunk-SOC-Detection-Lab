# Splunk-SOC-Detection-Lab
Splunk-based SOC detection lab for analyzing Apache logs, creating SPL detections, dashboards, and alerts for security monitoring and threat investigation.

## Overview

A Security Operations Center (SOC) monitoring project built using Splunk Enterprise.
The project demonstrates log ingestion, SPL-based threat detection, dashboard creation,
and alert configuration using Apache web server logs.

## Objectives

- Analyze web server logs using Splunk
- Detect suspicious activities
- Create security monitoring dashboards
- Generate alerts for potential threats

## Tools Used

- Splunk Enterprise
- SPL (Search Processing Language)
- Apache Access Logs

## Implemented Detections

### 1. Top Source IP Detection

Identifies the most active client IP addresses.

SPL:

index=soc_lab
| top clientip

---

### 2. HTTP Status Analysis

Analyzes HTTP response codes.

SPL:

index=soc_lab
| stats count by status

---

### 3. Web Enumeration Detection

Detects excessive 404 responses.

SPL:

index=soc_lab status=404
| stats count by clientip
| sort -count

---

### 4. Requested URL Analysis

Identifies frequently accessed resources.

SPL:

index=soc_lab
| top uri_path


## Dashboard

Created a SOC monitoring dashboard containing:

- Top Source IPs
- HTTP Status Distribution
- 404 Error Detection
- Most Requested URLs
- HTTP Methods

## Skills Demonstrated

- SIEM Operations
- Splunk
- SPL Query Writing
- Log Analysis
- Security Monitoring
- Threat Detection
