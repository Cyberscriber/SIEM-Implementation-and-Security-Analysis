<h1>SIEM Implementation and Security Analysis </h1>


<h2>Description</h2>
Project consists of utilization of complex SPL queries, and development of statistical reports for threat identification and mitigation, including response to a DOS attack and monitoring for brute force attacks


<h2>Languages and Utilities Used</h2>

- <b>SPL</b> 


<h2>Environments Used </h2>

- <b>Splunk 

<h2>Program walk-through:</h2>
SIEM (system information and event management) is used by organizations to solve the challenge of monitoring and identifying security incidents.  Organizations detect attacks against their information security assets with a concept called continuous monitoring, or more specifically, information security continuous monitoring (ISCM).
<br />
ISCM is the processes and technologies used to detect information security risks associated with an organization's operational environment in real time.  Organizations consider the following factors when determining security risk priorities: Compliance, Financial impact, Reputational impact and Likelihood of attack.
<br />
Logs are the most common organizational method for monitoring.  A log is a record of an event occurring within a device or a network. here are four main log types used by information security professionals: Operating system logs,Application logs, Networking device logs, and Security device logs.  Log aggregation is the identification and collection of logs from multiple computing sources.  Log parsing is the process of converting the single string of data into fields of structured data.  If we separate the values, we can categorize each field and rearrange them to match a uniform structure, a process known as log normalization. Log correlation identifies security events by using correlation rules.  Correlation rules are the logic used to identify security events.  One of the greatest strengths of SIEM tools is their ability to automate the aggregation, parsing, and normalization process.
<br />

As the SOC manager at OMP, you are asked to analyze the company's vulnerability scanning logs in order to determine the vulnerabilities of OMP's technical assets. 

- To accomplish this, you must design SPL searches to run against the vulnerability scanning log file `nessus.txt`.

- These searches can be used to quickly look up existing vulnerabilities on your operating systems or devices.
<br />
<br />
<p align="center">
Using SPL, design searches to display the following data from the `nessus` logs:
<br />
Display results where OS contains "Linux".
<img src="https://imgur.com/zNyWrpZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />   
Display results by destionation IP
<img src="https://imgur.com/b4CgUo0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Display results by destination IP
**Hint:** Use wildcards in your searches.
<p align="center">
Splunk for Fictional Company Vandalay Inc.
Command: source="server_speedtest (1).csv" host="server_speedtest" sourcetype="server_speedtest.csv" | eval ratio = ( DOWNLOAD_MEGABITS / UPLOAD_MEGABITS )to show the ratio between upload to download speeds
<br />
<img src="https://imgur.com/4QfcZpB.png" height="80%" width="80%" alt="SIEM Steps"/>
<br />
<br />
Command: source="server_speedtest (1).csv" host="server_speedtest" sourcetype="server_speedtest.csv" | eval ratio = ( DOWNLOAD_MEGABITS / UPLOAD_MEGABITS ) | table _time IP_ADDRESS DOWNLOAD_MEGABITS UPLOAD_MEGABITS ratio to display relevant fields
<br />
<img src="https://imgur.com/XRdja7w.png" height="80%" width="80%" alt="SIEM Steps"/>
<br />
<br />
The results were then saved as a report.  Based on the report, created the approximate date and time of the attack was on the 23rd at 14:30 <br />
<img src="https://imgur.com/CVkY9Z4.png" height="80%" width="80%" alt="SIEM Steps"/>
<br />
<br />
It took about 9 hours for systems to recover, from 14:30 to 23:30.
<br/>
<img src="https://imgur.com/MLU2eDb.png" height="80%" width="80%" alt="SIEM Steps"/>
<br />
<br />
Are We Vulnerable?
Command: source="nessus_logs.csv" host="nessus_logs" sourcetype="nessus_logs.csv" dest_ip="10.11.36.23" severity="critical" | top severity to find the count of critical vulnerabilities using the Nessus data
<br/>
<img src="https://imgur.com/p9fomJn.png" height="80%" width="80%" alt="SIEM Steps"/>
<br />
<br />
Used those results to run a report of Critical Vulnerabilities for IP address
<br />
<img src="https://imgur.com/mNvsvdc.png" height="80%" width="80%" alt="SIEM Steps"/>
<br />
An alert was set up to monitor every day to see if this server has any critical vulnerabilities. If a vulnerability exists, an alert will be emailed to soc@vandalay.com.<br />
<br />
<img src="https://imgur.com/vGm4zjO.png" height="80%" width="80%" alt="SIEM Steps"/>
<br />
<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
