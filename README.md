# Ethical Hacking Lab Manual — Submission Repo

Deadline: 2026-10-06 (Tue). Each exercise lives in its own folder with `report.docx` + `screenshots/`.

| # | Experiment | Status |
|---|---|---|
| 1 | Footprinting via Search Engines, Web Services, Social Networking Sites | draft (needs your browser screenshots) |
| 2 | Website, Email, Whois, DNS, Network Footprinting | done (real command output vs scanme.nmap.org) |
| 3 | Session Hijacking Using Various Tools | draft (needs isolated VM lab run) |
| 4 | Detect Session Hijacking | done |
| 5 | Web Server Reconnaissance Using Various Tools | done |
| 6 | Enumerate Web Server Information | done |
| 7 | Web Application Reconnaissance Using Various Tools | draft (needs Burp Suite + DVWA/Juice Shop lab run) |
| 8 | Web Spidering | done |
| 9 | Web Application Vulnerability Scanning | done |
| 10 | Crack FTP Credentials Using a Dictionary Attack | done |
| 11 | Cross-Site Request Forgery (CSRF) Attack | done |
| 12 | Identify XSS Vulnerabilities in Web Applications | done |
| 13 | Detect Web Application Vulnerabilities Using Various Security Tools | done |
| 14 | SQL Injection Attack Against MSSQL to Extract Databases | done |
| 15 | Detect SQL Injection Vulnerabilities Using Various Tools | done |
| 16 | Footprint a Wireless Network | draft (needs sample pcap + Wireshark/aircrack-ng lab run) |
| 17 | Create a Rogue Access Point to Capture Data Packets | draft (needs isolated VM lab run) |

Note: manual numbers experiments 4 and 3 out of order in the source PDFs (Ex4 covers "Detect Session Hijacking", which follows Experiment 3). Folder numbers here match the manual's own experiment numbering, not the original PDF filenames.

## Draft exercises still needing a real lab run

Exercises 1, 3, 7, 16, 17 have complete theory/procedure/viva write-ups in `report.docx`, written
directly from the lab manual, but **do not yet have real screenshots** — they need a live run in a
VM lab (or, for Exercise 1, just a browser) before submission:

- **Exercise 1** — redo the Google dork / Shodan searches in a real browser and screenshot the results.
- **Exercise 3, 17** — active attacks (ARP spoofing, rogue AP). Must run only inside an isolated
  VM lab (attacker + victim on a private host-only network), never on a real/shared network.
- **Exercise 7** — needs Burp Suite + a running DVWA/Juice Shop target.
- **Exercise 16** — needs a sample wireless `.pcap` plus Wireshark/aircrack-ng.

Exercise 2 was run live against `scanme.nmap.org` (the Nmap Project's own scan-permitted test host),
so its `report.docx` has real whois/DNS/traceroute output already — no further action needed there.
