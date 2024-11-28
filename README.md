# Vulnerability Management Lab with Nessus
This lab demonstrates a systematic approach to vulnerability management, encompassing detection, analysis, remediation, and validation. It underscores the importance of proactive security measures and provides hands-on experience with industry-standard tools and methodologies.

## Tools and Technologies used
- VMWare for the Windows VM
- Nessus as the vulnerability scanner

## Step 1: Downloaded and Set up Nessus Essentials
> Nessus Was used as the vulnerability scanner in this lab
![in](https://i.imgur.com/NKKVAMf.png)

## Step 2: Set up Windows 10 VM
> The Windows 10 VM was the client used to run vulnerability scans on
- Set up Windows 10 VM with 4 GB of RAM, 4 CPUs, and 50 GB storage.
![win](https://i.imgur.com/ivCTdOE.png)

## Step 3: Ensured connectivity with the VM 
> VM's Network Settings
![thrid](https://i.imgur.com/vMk95wC.png)
- Any attempt to "ping" the VM was timing out because of firewall protections
![before](https://i.imgur.com/yJVhSsi.png)
- Turned off firewall settings to ensure the VM was reachable.
> It is not recommended to do this in a normal working environment. This was solely done for the purpose of this lab.
![insert 5th pic](https://i.imgur.com/XpFkHTa.png)

- VM was successfully "pinged" after the firewall was turned off.
![work](https://i.imgur.com/cIFmDZu.png)

## Step 4: First scan; ran a basic scan on Nessus
> The "basic scan" performs a simple vulnerability scan of the target.
- AFter the basic scan was completed the following vulnerabilities were found:
- **31 info** level
- **2 medium** level vulnerabilities.
![basic](https://i.imgur.com/PmduP37.png)

## Step 5: Configured the VM for credentialed scans
- Enabled "Remote Registry" allowing Nessus to connect to the VM's registry remotely for a credentialed scan.

![insert](https://i.imgur.com/LGNZ3uD.png)

- Changed the UAC (User Account Control) to "never notify me"

![fa](https://i.imgur.com/yKUpKL2.png)

- Added a DWORD Key to the Windows Registry to further disable user account control for the remote account that will be used to connect to the VM.

![dor](https://i.imgur.com/luyjeQp.png)

## Step 6: Second scan; ran a credentialed scan on Nessus

> The credentialed vulnerability scan took much longer to complete, however, it showed much better results.
- After the credentialed vulnerability scan was completed the following vulnerabilities were found:
-  **34 critical** level vulnerabilities
-  **129 high** level vulnerabilities
-  **20 medium** level vulnerabilities
-  **1 low** level vulnerability
-  **182 info** level vulnerabilities.

![easy](https://i.imgur.com/yx1VYMv.png)

This demonstrates the importance of doing credentialed scans on critical resources in an organization. With a basic scan 0 critical/high vulnerabilities were found, however, with a credentialed scan 163 total critical/high level vulnerabilities were found. 






## Step 7: Installed a legacy version of Firefox
> This was done to create and inspect more vulnerabilities, and to gain more experience inspecting and fixing vulnerabilities.

- After the scan was completed the following vulnerabilities were found:
- **125 critical** level vulnarbilites 
- **210 high** level vulnerabilities
- **37 medium** level vulnerabilities
- **1 low** level vulnerability
- **183 info** level vulnerabilities

> As shown below, a lot of vulnerabilities come with legacy versions of applications which demonstrates the importance of staying on top of updates and patches. 
![insert](https://i.imgur.com/e7hgFda.png)

## Step 8: Remediated the vulnerabilities

After inspecting the vulnerability scans, I viewed the solutions for them, I made the following remidaitions:
- Deleted the legacy version of Firefox
- Checked for updates and installed Windows updates on the VM
- Upgraded Microsoft Edge to the latest version

![solutions](https://i.imgur.com/KgcWaGF.png)

The remediated vulnerability scan results are as follows:
- **1 critical level vulnerability**
- **13 high-level vulnerabilities**
- **7 medium-level vulnerabilities**
- **1 low-level vulnerability**
- **180 info level vulnerabilities**

![forget](https://i.imgur.com/OTsxoJx.png)





## Comparing the different vulnerability scans

| Basic Scan          | Credentialed Scan            | Crednetialed Scan with Firefox            | Remediated Scan          |
|---------------------|--------------------------------|--------------------------------|---------------------|
| ![Image1](https://i.imgur.com/PmduP37.png) | ![Image2](https://i.imgur.com/yx1VYMv.png) | ![Image3](https://i.imgur.com/e7hgFda.png) | ![Image4](https://i.imgur.com/OTsxoJx.png) |
| The basic scan was the quickest and didn't dive deep into the system. It showed a limited amount of info-level vulnerabilities with 0 critical/high-level vulnerabilities. This demonstrates how unreliable basic scans are.      | The credentialed scan took much longer to complete and showed much more vulnerabilities compared to the basic scan. This demonstrates its superiority over a basic scan | The third vulnerability scan was done after a legacy version of Firefox was installed. It showed an enormous amount of vulnerabilities on the Windows VM compared to the credentialed scan which demonstrates the importance of upgrading legacy systems and applications.    | The fourth and final scan was done after some remediations were made to the VM. The remediations were made based on the solutions by Nessus. The scan was a credentialed scan and showcased much fewer vulnerabilities than the other two credentialed scans demonstrating that vulnerability management is an essential part of having cybersecurity.       |






  




  
