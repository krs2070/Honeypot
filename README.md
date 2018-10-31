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
