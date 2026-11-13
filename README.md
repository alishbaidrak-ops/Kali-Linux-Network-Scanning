Kali Linux Network Scanning
1. Introduction
This project demonstrates basic network reconnaissance, DNS enumeration, web information gathering, and network host discovery using Kali Linux and Zenmap.
The practical was performed using different Kali Linux commands followed by Zenmap/Nmap scanning on the local network.
 2. Objectives
- To gather basic information about a target domain.
- To identify web technologies used by a website.
- To check HTTP response headers.
- To collect WHOIS information.
- To perform DNS enumeration.
- To identify a Web Application Firewall.
- To identify the local IPv4 address.
- To perform host discovery using Zenmap.
- To identify live hosts and their MAC addresses.
- To view the discovered network through Zenmap topology.
 3. Tools Used
- Kali Linux
- WhatWeb
- NSLookup
- cURL
- WHOIS
- DNSRecon
- WAFW00F
- Zenmap / Nmap
- Windows Command Prompt
4. Kali Linux Commands
 4.1 WhatWeb
bash
whatweb --open-timeout=60 --read-timeout=60 networkwalks.com
Purpose:
Used to identify technologies and components associated with the target website.
Observed results:
- Apache
- WordPress
- Bootstrap
- jQuery
- Google Tag Manager
- Other web technologies
 4.2 NSLookup
bash
nslookup networkwalks.com
Purpose: 
Used to perform DNS resolution for the target domain.
Observed result:
The command attempted DNS communication through `8.8.8.8`, but the output showed timeout messages and finally:
text
no servers could be reached
4.3 cURL
bash
curl -I https://networkwalks.com
Purpose: 
Used to retrieve the HTTP response headers of the target website.
Observed results:
text
HTTP/1.1 200 OK
Server: Apache
Content-Type: text/html; charset=UTF-8
The response also displayed WordPress-related information and HTTP headers.
4.4 WHOIS
bash
whois networkwalks.com
Purpose: 
Used to obtain domain registration information.

Information observed:
- Domain name
- Registrar
- Domain creation/update information
- Domain status
- Name servers
- WHOIS database information
 4.5 DNSRecon
bash
dnsrecon -d networkwalks.com
Purpose:
Used for DNS enumeration.
Observed record types:
- SOA
- NS
- MX
- A
- TXT
- SRV

The enumeration completed with:
text
8 Records Found
4.6 WAFW00F
bash
wafw00f networkwalks.com
Purpose: 
Used to identify the Web Application Firewall protecting the website.
Observed result:
text
ModSecurity (SpiderLabs) WAF
 5. Finding the Local IPv4 Address

Windows Command Prompt was used with:
cmd
ipconfig
The IPv4 address used for the local network scan was:
text
The network used for the scan was:
text
6. Zenmap Host Scan

Zenmap was used to perform host discovery using Nmap.

Single Host Scan

The target host was scanned using a Ping Scan.
bash
nmap 

Result:
text
Host is up.

This confirmed that the scanned host was active.
 7. Local Network Scan
The local `/24` network was scanned using:
bash
nmap 

The scan covered 256 IP addresses.

The result showed:
text
256 IP addresses (5 hosts up)

Therefore, five live hosts were identified.
zenmap Topology

Zenmap's Topology feature was used to visualize the discovered hosts in the network.

The topology view provided a graphical representation of the hosts discovered during the network scan.
11. Results
The practical demonstrated different network reconnaissance and discovery techniques
Kali Linux commands were used to gather information about the target website, including web technologies, HTTP headers, domain registration details, DNS records, and WAF information.
Zenmap was then used to discover active hosts on the network. The `/24` network scan identified five live hosts along with their corresponding MAC addresses.

12. Conclusion

This practical provided hands-on experience with Kali Linux reconnaissance tools and Zenmap network scanning.

The exercise demonstrated how different tools can be used to gather information about websites and discover active devices on a network.

All scanning activities should only be performed on systems and networks for which proper authorization has been provided.

13. Screenshots
Screenshots of the commands, outputs, Zenmap scans, and topology will be added to the repository as supporting evidence.

Kali Linux
- WhatWeb
- NSLookup
- cURL
- WHOIS
- DNSRecon
- WAFW00F

Zenmap
- Local IP configuration
- Single-host scan
- Network scan
- Live hosts
- MAC addresses
- Topology
