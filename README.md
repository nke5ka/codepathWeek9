# Codepath Week 9 Honeypot

## Overview
For the Codepath assignment, I spun up an AWS VM which ran MHN.  The honeypots Dionaea, Elastic Honey, and Conpot were used, but Dionaea was the only one attacked, other than one instance of Elastic Honey being attacked.

No issues were encountered in setup, and 1407 attacks took place over the course of about 20 hours, including 1054 attacks due to me running nmap on the system. This leaves 353 genuine attacks.  Interestingly, an attack from France took place before I even got a chance to run nmap - the Internet is a wild place.

## Analytics
No samples of payloads were found, but the 129 unique attack ips provide some interesting analytics.  You can get the same results by finding the following in the repo:
* session.json - verbatim output of mongodb dump
* sessionNoSubDicts.json - cleaned up json for input into database
* ipAddr.txt - the 129 unique IP addresses used
* ipCountry.txt - the 129 unique IP addresses and their countries of origin using http://software77.net/geo-ip/multi-lookup/

Here are the countries of attack origin and corresponding frequency of countries with more than one attack
| Country       | Frequency |
|---------------|-----------|
| United States |        29 |
| China         |        16 |
| Russia        |        13 |
| Chile         |         5 |
| France        |         5 |
| Ukraine       |         5 |
| Venezuela     |         5 |
| Brazil        |         4 |
| Germany       |         4 |
| India         |         4 |
| Netherlands   |         4 |
| Taiwan        |         4 |
| Canada        |         3 |
| Indonesia     |         3 |
| Turkey        |         3 |
| Vietnam       |         3 |
| Ecuador       |         2 |
| Egypt         |         2 |
| Italy         |         2 |

With more uptime and honeypots, more research can be done on the effect of country wealth on number of cyber-attacks per capita.  In my case, Americans attacked the most - not unexpected.

Additional questions are:
* how exactly do these attackers operate (finding targets, attempts to exploit, goals, proxies, etc.)
* effect of server time since creation on number of attacks per unit time (the speed of attacks seemed to increase as time went on)
* effect of host and server on attack frequency and origin (Google v Amazon, ipv4 v ipv6, number of open ports...)
* actions to mitigate attacks (hosting sites, developers, law enforcement)