
# Nmap Scan Overview

*Nmap (Network Mapper) is an open-source tool used for network discovery and security auditing. It is widely used by network administrators and security professionals to discover hosts and services on a computer network, as well as to perform various types of security scans to assess vulnerabilities.*


# Installation
1. Update Your System: Ensure your system is up-to-date to avoid installation issues.
```yml
sudo apt update && sudo apt upgrade -y
```

2. Install Nmap: Nmap can be easily installed via the default Ubuntu package repository.

```yml
sudo apt install nmap -y
```

3. Verify Installation: After installation, check if Nmap is successfully installed by running:

```yml
nmap --version
```
*You should see the installed version of Nmap.*


<br>
<br>

# Nmap Scan Types
  *Here is a detailed breakdown of common Nmap scans and how to use them:*

1. Basic Host Discovery (Ping Scan)
The simplest scan is used to determine which hosts are up and reachable on a network.

```yml
nmap -sn <target>
```
  - sn: Ping scan (no port scan, just check if the host is up).
  - <target>: The IP address or hostname of the target (e.g., 192.168.1.1, example.com, or a range like 192.168.1.0/24).


### Example in my case:

```yml
nmap -sn 192.168.1.0/24
```
  - This checks all hosts in the 192.168.1.0/24 range to see if they are up.

2. TCP Connect Scan (Full Scan)
A full port scan to identify open ports on a host. It establishes a full connection to each port.

```yml
nmap -sT <target>
```
  - sT: TCP connect scan (attempts to complete the three-way handshake with each port).
  - <target>: The target IP or range of IPs.

### Example in my case:

```yml
nmap -sT 192.168.1.1
```
  - This scans all 65535 ports on the target 192.168.1.1.

3. SYN Scan (Stealth Scan)
The SYN scan is the most popular and stealthiest scan. It sends a SYN packet and waits for a response.

```yml
nmap -sS <target>
```
  - sS: SYN scan (half-open scan).
  - <target>: Target IP or range.


### Example in my case:
```yml
nmap -sS 192.168.1.1
```
  - This will perform a stealth scan on all TCP ports of 192.168.1.1.

4. Service Version Detection
  - This allows you to detect the version of services running on open ports.

```yml
nmap -sV <target>
```
  - sV: Enables version detection.
  - <target>: Target IP or range.


### Example in my case:
```yml
nmap -sV 192.168.1.1
```
 - This will scan open ports and attempt to detect the service name and version running on each open port.

5. Operating System Detection
Nmap can attempt to determine the operating system of the target host.


```yml
nmap -O <target>
```
  - O: Enables operating system detection.
  - <target>: Target IP or range.


### Example in my case:
```yml
nmap -O 192.168.1.1
```
  - This will attempt to determine the operating system of the target.

6. Aggressive Scan
The aggressive scan combines several scan techniques into one. It performs host discovery, port scanning, service version detection, OS detection, and traceroute.

```yml
nmap -A <target>
```
  - -A: Aggressive scan (includes OS detection, version detection, script scanning, and traceroute).
  - <target>: Target IP or range.

### Example in my case:
```yml
nmap -A 192.168.1.1
```
  - This performs a comprehensive scan on the target 192.168.1.1.

7. Scan Specific Ports
You can specify which ports to scan rather than the default 1000 most common ports.

```yml
nmap -p <port1>,<port2>,<port3> <target>
```
  - -p <port1>,<port2>,<port3>: Specifies a comma-separated list of ports.
  - <target>: Target IP or range.

### Example in my case:
```yml
nmap -p 22,80,443 192.168.1.1
```
  - This will scan ports 22 (SSH), 80 (HTTP), and 443 (HTTPS) on the target.

8. Scan a Range of IPs
To scan a range of IP addresses, you can use either a subnet range or a specific set of IPs.

```ymml
nmap <start-ip>-<end-ip>
```
  - <start-ip>-<end-ip>: Defines a range of IPs to scan.

### Example in my case:
```yml
nmap 192.168.1.1-50
```
  This will scan IPs from 192.168.1.1 to 192.168.1.50.

9. Scan Using a Script (Nmap Scripting Engine)
Nmap has a powerful scripting engine (NSE) to perform more complex scans like vulnerability detection, web application security checks, and more.

```yml
nmap --script <script-name> <target>
```
 - --script <script-name>: Runs a specific Nmap script.
  - <target>: Target IP or range.

### Example in my case:
```yml
nmap --script=http-vuln-cve2014-3704.nse 192.168.1.1
```
  - This runs a specific Nmap script to check for a known vulnerability on the target.

10. Save Nmap Scan Results to a File
  - You can save the results of an Nmap scan to a file for later analysis. Nmap supports several output formats, including plain text, XML, and grepable formats.

```yml
nmap -oN <output-file.txt> <target>
```
  - -oN <output-file.txt>: Saves the output to a plain-text file.
  - <target>: Target IP or range.


### Example in my case:

```yml
nmap -oN scan_results.txt 192.168.1.1
```
  - This saves the output of the scan to scan_results.txt.

For XML output:

```ymml
nmap -oX <output-file.xml> <target>
```

- For grepable format:

```yml
nmap -oG <output-file.gnmap> <target>
```
<br>
<br>

## Conclusion
Nmap is a versatile and powerful tool for network exploration and security scanning. By utilizing various scan types, it allows you to discover hosts, identify open ports, detect services, and even fingerprint operating systems. This flexibility makes Nmap an essential tool for both network administrators and security professionals.













<br>
<br>
<br>
<br>



**👨‍💻 𝓒𝓻𝓪𝓯𝓽𝓮𝓭 𝓫𝔂**: [Suraj Kumar Choudhary](https://github.com/Surajkumar4-source) | 📩 **𝓕𝓮𝓮𝓵 𝓯𝓻𝓮𝓮 𝓽𝓸 𝓓𝓜 𝓯𝓸𝓻 𝓪𝓷𝔂 𝓱𝓮𝓵𝓹**: [csuraj982@gmail.com](mailto:csuraj982@gmail.com)





<br>
