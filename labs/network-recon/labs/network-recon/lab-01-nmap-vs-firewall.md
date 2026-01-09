Lab 1: Nmap With and Without Firewall

## Objective
To observe how Windows Firewall affects network reconnaissance using Nmap from a Kali Linux attacker VM.

---

## Enviroment
- attacker: Kali Linux
- Victim: Windows VM
- Network: Host only (192.168.56.0/24)

---

## Without firewall:
when running nmap against a computer without a firewall the Nmap completed almost instantly and returned a large amount of host and service information.
![Nmap scan with firewall disabled](screenshots/nmap-firewall-off-win10-scan-results.png)
---

## With firewall:
with the firewall up the nmap appeared to stall during the initial probaing this continued for approximately 3 minutes when the nmap finally finished only a small amount of information was recived compared to the amount recived without the firewall.
![Nmap scan with firewall enabled](screenshots/nmap-firewall-on-win10-filtered-ports.png)
---

## Conclusion:
having the firewall up may not stop all the information for being obtained but it does limit the amount and slow down would be attackers. This demonstrates how stateful firewalls reduce attacker visibility by silently dropping packets, increasing scan time and limiting reconnaissance accuracy.

---

## Commands Used
code used: nmap -sS -sV -O 192.168.56.103

## Next Steps
- Run scan with `-Pn` to compare firewall behavior
- Review Windows Firewall logs during scan
- Test timing templates (-T4 vs default)
