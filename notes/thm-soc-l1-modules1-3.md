# THM SOC Level 1: First 3 Modules Write-up

**Path**: SOC Level 1 → Modules 1-3  
**Completed**: March 29, 2026

## Module 1: Blue Team Introduction

**Key Concepts**:
```
SOC Role: Monitor, detect, respond to threats 24/7
Tier 1 Analyst: Alert triage, false positive filtering
Daily Tasks: SIEM review, phishing analysis, IOC hunting
```

**Workflow**:
```
Alert → Validate → Investigate → Escalate/Document
```

**Answer**: `SOC analysts triage alerts and escalate to Tier 2`

## Module 2: Cyber Defence Frameworks

**MITRE ATT&CK Coverage**:
```
Recon → Initial Access → Execution → Persistence
Privilege Escalation → Defense Evasion → Lateral Movement
Collection → Exfiltration → Impact
```

**Kill Chain Stages**:
```
1. Reconnaissance
2. Weaponization  
3. Delivery → Phishing, exploits
4. Exploitation → RCE
5. Installation → Backdoor
6. C2 → Beaconing
7. Actions on Objectives
```

**Answer**: `Phishing emails map to Initial Access (T1566)`

## Module 3: Phishing Analysis

**Phishing Types**:
```
Spear Phishing → Targeted individuals
Whaling → Executives
Business Email Compromise → Payment redirects
```

**Investigation Steps**:
```
1. Headers → DKIM/SPF/DMARC check
2. URL analysis → VirusTotal, URLScan
3. Attachment → Office macros, PE analysis
4. Sender domain → WHOIS lookup
```

**Red Flags**:
```
- Mismatched domains (google-security.com)
- URL shorteners (bit.ly)
- Macro-enabled docs (.xlsm)
- Poor grammar/urgency
```

**Practical**:
```
Email Headers: DKIM fail → Suspicious
Attachment: SHA256 → Known malware
Callback Domain: DGA generated
→ Verdict: MALICIOUS
```

**Flag**: `THM{PH1SH1NG_1S_3V3RYWH3R3}`

## Key Tools Learned
```
WHOIS → Domain registration
VirusTotal → File/URL reputation
DKIM Analyzer → Email auth
```