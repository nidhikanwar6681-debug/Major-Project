# Major-Project
Bug Bounty Reconnaissance Assignment (Revolut)

1️⃣ Identify the Company’s Main Domain
🎯 Objective

Find the official primary domain of Revolut.

🔍 Steps

Open Google

Search:

Revolut official website

Open the homepage / About / Contact page

Ignore:

Marketing links

Country-specific domains

✅ Result

Main Domain:

revolut.com

2️⃣ Locate Bug Bounty / Vulnerability Disclosure Program
🎯 Objective

Find where Revolut accepts security vulnerability reports.

🔍 Steps

Google search:

Revolut bug bounty
Revolut vulnerability disclosure

✅ Findings

Revolut hosts its bug bounty on HackerOne.

📌 Example Link (mention in report)
https://hackerone.com/revolut


3️⃣ Identify Bug Bounty Scope (In-Scope & Out-of-Scope)
🎯 Objective

Understand what assets are allowed to be tested.

🔍 Steps

Open the HackerOne program page

Scroll to Scope / In-Scope / Out-of-Scope

✅ Example Scope (Explain, don’t exploit)

In-Scope:

*.revolut.com

Out-of-Scope:

DoS attacks

Social engineering

Physical attacks

Third-party services


4️⃣ Ping the Main Domain
🎯 Objective

Check ICMP reachability and IP address.

🧪 Command (Linux / Kali)
ping revolut.com

✅ Possible Outcomes

Replies received → Ping allowed

Request timed out → ICMP blocked (common for banks)

📝 Example Observation
PING revolut.com (X.X.X.X)
Request timed out


5️⃣ Technology Stack Identification (Main Domain)
🎯 Objective

Identify technologies used on revolut.com.

🧰 Tool

Wappalyzer (Browser Extension)

🔍 Steps

Open https://revolut.com

Click Wappalyzer icon

Record findings

📊 Example Technologies
Category	Technology
Web Server	Nginx
Framework	React
Language	JavaScript
CDN	Cloudflare
Analytics	Google Analytics

6️⃣ Find ASN Number & IP Ranges
🎯 Objective

Identify Revolut’s network ownership.

🧪 Commands
dig revolut.com
whois <IP_ADDRESS>


OR

whois -h whois.cymru.com " -v <IP_ADDRESS>"

✅ Information Collected

ASN Number

Organization name

Netblocks (IP ranges)


7️⃣ Subdomain Enumeration
🎯 Objective

Find subdomains related to Revolut.

🧰 Tool (Kali Linux)

amass

🧪 Command
amass enum -d revolut.com

📁 Output

Save results:

amass enum -d revolut.com -o revolut_subdomains.txt

8️⃣ Technology Stack on Subdomains
🎯 Objective

Compare technologies across subdomains.

🔍 Steps

Select any 5 subdomains

Open them in browser

Use Wappalyzer

📊 Example Comparison Table
Subdomain	Tech Stack
app.revolut.com	React, APIs
help.revolut.com	Zendesk
blog.revolut.com	WordPress
developer.revolut.com	Static site


9️⃣ Hidden Files & Directories (Main Domain Only)
⚠️ Rule Reminder

✔ Main domain only
❌ No subdomains

🧰 Tool

dirb

🧪 Command
dirb https://revolut.com
