# Threat-Intelligence
Leveraging OSINT for Business Risk Profiling and Threat Assessment

A passive Cyber Threat Intelligence (CTI) assessment of ZEIT (zeit.de) focused on understanding its public digital footprint, exposed infrastructure, potential phishing and impersonation risks, and data-leakage indicators. The project used multiple OSINT and threat-intelligence sources to correlate publicly available information and develop actionable defensive recommendations. 

(**Table of Contents**)
•	Project Overview 
•	Network Topology 
•	Tools and Technologies 
•	Configuration Steps 
•	Results and Findings 
•	Author 

(**Project Overview**)
This project conducted a passive OSINT investigation of ZEIT / ZEIT Verlagsgruppe, with the primary focus on zeit.de.
The main objectives were to:
•	Profile the organisation's publicly discoverable digital footprint 
•	Identify publicly exposed domains, subdomains, hosts, IP addresses, and infrastructure 
•	Investigate potential phishing and brand impersonation activity 
•	Identify data-leakage indicators associated with organisational email addresses 
•	Validate the reputation of discovered domains, hosts, and IP addresses 
•	Correlate intelligence from multiple OSINT and threat-intelligence sources 
•	Assess potential business risks from publicly available information 
•	Develop defensive recommendations for security and SOC teams 
The assessment was explicitly limited to passive intelligence collection. It did not include vulnerability exploitation, password attacks, active penetration testing, unauthorised access, malware deployment, credential validation, social engineering, or internal network testing. 

(**Network Topology**)
This project did not implement a traditional internal network topology because the assessment focused on external digital-footprint and OSINT analysis rather than network penetration testing.
The assessed digital environment included:
•	Primary domain: zeit.de 
•	Subdomains: 15 subdomains identified through Sublist3r 
•	IP infrastructure: 51 IP addresses identified during passive collection 
•	Hosts: 1,540 hosts identified during broad passive collection 
•	ASNs: 10 ASNs identified through theHarvester 
•	URLs: 30 interesting URLs identified through theHarvester 
•	Public-facing services: Websites, applications, newsletters, multimedia services, subscription platforms, and related subsidiary platforms 
•	Organisation ecosystem: ZEIT Verlagsgruppe subsidiaries and associated digital platforms 

The investigation also examined ZEIT-related infrastructure through services including Shodan, VirusTotal, AbuseIPDB, URLScan, PhishTank, WHOIS, and web archives. 
Tools and Technologies
•	Kali Linux: OSINT investigation environment 
•	Google Dorks: Search-engine reconnaissance and discovery of indexed information 
•	theHarvester : Passive infrastructure and email discovery 
•	Sublist3r: Subdomain enumeration 
•	Shodan: Internet-facing infrastructure discovery 
•	VirusTotal : Domain and host reputation validation 
•	AbuseIPDB: IP reputation and abuse-report checking 
•	Wayback Machine: Historical web infrastructure and asset discovery 
•	Have I Been Pwned : Public breach exposure validation 
•	MITRE ATT&CK Framework: Threat-actor and technique analysis 
•	MXToolbox :Supporting domain and infrastructure analysis 
•	URLScan: URL and web validation 
•	PhishTank: Phishing validation 
•	WHOIS:  Domain metadata collection 
•	OSINT Framework:  Supporting OSINT resource 
•	Exploit-DB Google Hacking Database: Supporting search reconnaissance resource 

(**Configuration Steps**)
1.	Defined the intelligence requirements and established ZEIT / zeit.de as the primary investigation scope. 
2.	Conducted passive search-engine reconnaissance to identify publicly indexed login pages, security-related documents, PDFs, spreadsheets, references, and other relevant information. 
3.	Used theHarvester to identify publicly observable infrastructure and email information, including: 
10 ASNs 
30 interesting URLs 
51 IP addresses 
1,540 hosts 
4.	Used Sublist3r for passive subdomain enumeration, identifying 15 subdomains. 
5.	Queried Shodan using org:"Zeit" to identify publicly visible infrastructure associated with the organisation. 
6.	Investigated potential phishing and impersonation activity using the search query intitle:"zeit" inurl:login -site:zeit.de. 
7.	Searched for potential data-leakage indicators using queries such as filetype:pdf "zeit" "security", site: pastebin.com "zeit.de", and intext:"zeit" filetype:xls OR filetype:csv. 
8.	Validated discovered domains and hosts using VirusTotal, including zeit.de, abo.zeit.de, and consent-cdn.zeit.de. 
9.	Checked identified IP infrastructure against AbuseIPDB and other reputation sources. 
10.	Used URLScan and PhishTank to validate potential malicious URLs or phishing indicators. 
11.	Used WHOIS and the Wayback Machine to investigate domain metadata and historical ZEIT web infrastructure. 
12.	Used Have I Been Pwned to validate breach exposure associated with publicly identified organisational email addresses. 
13.	Correlated indicators across multiple independent sources rather than treating any single OSINT database as authoritative. 
14.	Assessed findings according to their confidence, likelihood, potential business impact, and recommended defensive action. 
Results and Findings
The assessment identified a large and publicly discoverable ZEIT digital footprint but did not establish evidence of an active compromise.
Key Findings
•	No confirmed phishing domain was identified. The query intitle:"zeit" inurl:login -site:zeit.de returned no results in the investigation. 
•	No confirmed malicious ZEIT-related domain or IP address was identified. 
•	zeit.de received 0/92 detections in the recorded VirusTotal investigation. 
•	abo.zeit.de and consent-cdn.zeit.de received 0/91 detections in the recorded VirusTotal results. 
•	IP address 151.101.1.55 had no negative AbuseIPDB result reported and was assessed as low concern. 
•	diezeit@zeit.de was reported in 14 breaches, with the investigation identifying a more recent exposure in April 2026. 
•	digitalabo@zeit.de was reported in one breach, dated February 2020. 
•	The exposed information associated with diezeit@zeit.de reportedly included email addresses, names, job titles, telephone numbers, and physical addresses. 
•	The investigation identified 1,540 hosts, demonstrating the importance of maintaining an accurate external attack-surface inventory.


(**Risk Assessment**)
The highest-confidence security concern was historical breach exposure of organisational email addresses, rather than malicious infrastructure.
•	Infrastructure reputation: Low concern 
•	Confirmed impersonation: Not identified 
•	Data-exposure concern: Significant 
•	Social-engineering risk: Moderate 
•	Evidence of active compromise: Not established 
Potential risks associated with exposed organisational information include spear-phishing, business email compromise attempts, password-spraying campaigns, social engineering, identity impersonation, and fraudulent subscription or customer-service communications. 

(**Recommendations**)
•	Continuously monitor for look-alike domains, typosquatting, fake ZEIT login pages, fake subscription pages, and fraudulent social-media accounts. 
•	Treat identified breached email addresses as exposed intelligence. 
•	Confirm whether exposed accounts remain active and ensure historical passwords are no longer used. 
•	Enforce strong authentication and phishing-resistant MFA where feasible. 
•	Monitor authentication logs for anomalous activity and potential credential reuse. 
•	Maintain an authoritative inventory of domains, subdomains, IP ranges, cloud services, SaaS applications, third-party services, and subsidiary infrastructure. 
•	Monitor indicators through SIEM, EDR, DNS monitoring, email security controls, threat-intelligence platforms, and brand-monitoring services. 
•	Strengthen email security through SPF, DKIM, and DMARC. 
•	Repeat the CTI assessment periodically to maintain continuous visibility into changes to the external attack surface. 

(**Author**)
Name: Olajumoke Olaniyan
Role: Cyber Threat Intelligence Analyst
Organisation: ZEIT (zeit.de)
Submission Date: August 14, 2026


