# Project 9 - Honeypot

## Honeypot(s) deployed

- For this project I deployed the following honeypots,
	- Dionaea over HTTP
		- As mentioned in the assignment, Dionaea over HTTP is a honeypot that is used to trap malware samples. "Dionaea supports ipv6 and tls and uses libemu to detect shellcodes" ([Reference Link](https://github.com/threatstream/mhn/wiki/Dionaea-Sensor)).
	- p0f
		- p0f is a honeypot that "identifies incidental TCP/IP communications using purely passive traffic fingerprinting mechanisms" ([Reference Link](https://github.com/threatstream/mhn/wiki/p0f-Sensor)).
	- Snort
		- Snort is a honeypot that is "capable of real-time traffic analysis and packet logging" ([Reference Link](https://github.com/threatstream/mhn/wiki/Snort-Sensor)).  
	
- To create the MHN Admin VM and deploy the honeypots, I used Google Cloud. I was able to follow the provided instructions properly, however, I did encounter a few issues during the set-up process. More information about these issues is provided below under the Issues Encountered section.
	
- Provided below is a GIF that demonstrates that honeypots that were deployed and the corresponding attack reports.
	- GIF: ![]() 

## Summary of data collected
- To collect a good amount of data, I deployed the above mentioned 3 honeypots and allowed them to run for a few hours.
- As mentioned in Milestone 5 of the assignment instructions, I also attacked the Dionaea over HTTP honeypot. I attacked the honeypot from my Kali VM using the nmap command as mentioned in the instructions for Milestone 5. After attacking the Dionaea over HTTP honeypot, I was able to see the IP address of the Kali VM in the Attack Report of the honeypot.
- According the assignment instructions, Dionaea over HTTP is a honeypot used to trap malware samples. Unfortunately, the honeypot that I deployed was unable to capture any malware samples.
- The image below, captured from the MHN Admin console, shows the overall attack stats.  
![](https://i.imgur.com/aRLGxep.jpg)
- Provided below is the overall summary of the data collected.
	- Total number of attacks captured: 4293 attacks
	- Of all the attacks captured,
		- Dionaea over HTTP honeypot captured the highest number of attacks with 3438 captured attacks.
		- p0f honeypot captured 487 attacks
		- Snort honeypot captured 368 attacks.
	- Attacker IP with most attacks: 98.249.5.34 (This is the IP of the Kali VM that I used to attack the Dionaea over HTTP honeypot. This indicates that when I used the nmap command to attack the honeypot, a total of 2848 attacks were triggered). Provided below is the list of top 5 attacker IPs.
		- IP 98.249.5.34 attacked 2848 times.
		- IP 209.141.35.236 attacked 118 times.
		- IP 46.166.142.138 attacked 110 times.
		- IP 209.141.56.95 attacked 74 times.
		- IP 62.210.141.119 attacked 67 times.
	- After analyzing the data more, I realized that the attacks came from a lot of different countries, but the country with the highest number of attacks was USA.
	- Overall, the 5 most attacked ports were 8088, 5060, 22, 23, and 8080. The 8088 port was the most attacked port. 
		- Port 8088 was attacked 709 times.
		- Port 5060 was attacked 205 times.
		- Port 22 was attacked 61 times.
		- Port 23 was attacked 43 times.
		- Port 8080 was attacked 19 times.

- Provided below is the summary specific to Dionaea over HTTP honeypot.
	- Provided below is the image of an Attack Report page for the Dionaea over HTTP honeypot
	![](https://i.imgur.com/fmVKbya.jpg)
	- Total number of attacks captured: 3438 attacks
	- Based on the data gathered, a majority of the captured attacks use the pcap protocol. SipSession, httpd, and smbd are among the few other protocols used.
	- Unfortunately no malware samples were captured by this honeypot.

- Provided below is the summary specific to p0f honeypot.
	- Provided below is the image of an Attack Report page for the p0f honeypot
	![](https://i.imgur.com/ffXZFRD.jpg)
	- Total number of attacks captured: 487 attacks
	- Based on the data gathered, all the captured attacks use the pcap protocol.

- Provided below is the summary specific to Snort honeypot.



## Unresolved Questions

## Json export of the data collected
- I have included a json export of the data collected from my honeypots in this repository. To make it easier to find it, provided below is the link to the document  
https://github.com/krs2070/Honeypot/blob/master/session.json

## Issues Encountered
- Provided below is the list of issues that I encountered while completing the assignment
	
	- While installing the MHN Admin Application, the assignment instructions tell us to clone the https://github.com/RedolentSun/mhn.git repository. However, after cloning the repo, when I ran the install.sh, the install process failed due to a missing repository fatal error. After discussing this issue with a TA, I was able to fix it by cloning the https://github.com/threatstream/mhn.git repository instead of https://github.com/RedolentSun/mhn.git.
	
	- On the first attempt, I wasn't able to load and view the MHN admin console in the browser. I had to update the MHN Admin VM's firewalls to HTTP and HTTPS traffic to be able to view the MHN admin console in the browser. The assignment instructions does not mention anything about this.
	
	- I also tried deploying the Conpot and Cowrie honeypots, however, I was not able to do due to issues that I faced with running the deploy.sh script on the google cloud VM.

## Resources

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## License

    Copyright [2018] [Kevin Shah]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
