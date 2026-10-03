# Ethical Hacking Lab Manual — Submission Repo

Deadline: 2026-10-06 (Tue). Each exercise lives in its own folder with `report.docx` + `screenshots/`.

| # | Experiment | Status |
|---|---|---|
| 1 | Footprinting via Search Engines, Web Services, Social Networking Sites | done (real Google dorks + Shodan + org lookup vs nmap.org) |
| 2 | Website, Email, Whois, DNS, Network Footprinting | done (real command output vs scanme.nmap.org) |
| 3 | Session Hijacking Using Various Tools | done (real cookie theft + reuse demo; local HTTP server stand-in for ARP spoof) |
| 4 | Detect Session Hijacking | done |
| 5 | Web Server Reconnaissance Using Various Tools | done |
| 6 | Enumerate Web Server Information | done |
| 7 | Web Application Reconnaissance Using Various Tools | done (real curl-based recon vs nmap.org; Burp Suite lab run still improves it) |
| 8 | Web Spidering | done |
| 9 | Web Application Vulnerability Scanning | done |
| 10 | Crack FTP Credentials Using a Dictionary Attack | done |
| 11 | Cross-Site Request Forgery (CSRF) Attack | done |
| 12 | Identify XSS Vulnerabilities in Web Applications | done |
| 13 | Detect Web Application Vulnerabilities Using Various Security Tools | done |
| 14 | SQL Injection Attack Against MSSQL to Extract Databases | done |
| 15 | Detect SQL Injection Vulnerabilities Using Various Tools | done |
| 16 | Footprint a Wireless Network | done (real tshark analysis of a public WPA capture) |
| 17 | Create a Rogue Access Point to Capture Data Packets | partial (real plaintext capture shown; still needs real hostapd rogue-AP VM run) |

Note: manual numbers experiments 4 and 3 out of order in the source PDFs (Ex4 covers "Detect Session Hijacking", which follows Experiment 3). Folder numbers here match the manual's own experiment numbering, not the original PDF filenames.

## Draft exercises still needing a real lab run

Exercises 1, 2, 3, 7, 16 now all have **real captured/looked-up data**, not placeholder theory. Only
Exercise 17 is partial, and nothing needed a GUI/VM to get there — every stand-in below used real
commands against a real target or a real local server, substituting only for tools this sandboxed
shell couldn't run (GUI browser, root packet capture, Ettercap/hostapd).

- **Exercise 1** — real Google dorks (`site:nmap.org filetype:pdf`, `intitle:"index of"`) and a real
  Shodan-style lookup of scanme.nmap.org's open services, run via the WebSearch tool in place of a
  GUI browser.
- **Exercise 3** — real end-to-end cookie theft + reuse against a local plain-HTTP test server
  (login issues a cookie → netcat sniffs it in plaintext → reused without the password to access the
  victim's page; a request without the cookie is rejected). Stands in for the full Ettercap
  ARP-spoofing lab, which still needs an isolated two-VM network to fully replicate.
- **Exercise 7** — real curl-based recon (headers, cookies, forms, JS files, error behaviour) against
  nmap.org, after the manual's usual public practice targets (testphp.vulnweb.com, testfire.net)
  turned out to be unreachable from this environment's network. Burp Suite's GUI would still add
  value (live proxy history, HttpOnly/Secure flag inspection on a site that actually sets cookies).

Exercises 2, 16 have **real captured data** from a true dedicated run:
- **Exercise 2** — run live against `scanme.nmap.org` (the Nmap Project's own scan-permitted test
  host): real whois/DNS/traceroute/header output embedded in the report.
- **Exercise 16** — a real public WPA capture (`wpa-Induction.pcap`, from Wireshark's official Sample
  Captures page) analysed live with tshark: real beacon frames, SSID "Coherer", RSN/WPA encryption
  detail, and a full 4-way EAPOL handshake between the AP and an Apple client. Capture file saved in
  `Exercise-16/screenshots/`.
- **Exercise 17** — still needs the real hostapd/dnsmasq rogue AP built in an isolated VM lab (not
  possible in this sandboxed environment — no root for packet capture, no second VM). As a stand-in,
  a real plaintext HTTP POST (`username=victim&password=...`) was captured off a local test server
  via raw netcat (no root needed) to demonstrate the exact cleartext-exposure finding the exercise is
  testing for. Raw capture saved in `Exercise-17/screenshots/raw_capture.txt`. Marked "partial" —
  swap this placeholder for a real Wireshark capture once you run the full rogue-AP lab.
