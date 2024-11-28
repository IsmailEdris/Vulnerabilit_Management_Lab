# Vulnerability Management Lab with Nessus
**Description goes here**

## Tools and Technologies used
- VMWare for the Windows VM
- Nessus as the vulnerability scanner

## Step 1: Downloaded and Set up Nessus Essentials
> Nessus Was used as the vulnerability scanner in this lab
![in](insert first pic)

## Step 2: Set up Windows 10 VM
> The Windows 10 VM was the client used to run vulnerability scans on
- Set up Windows 10 VM with 4 GB of RAM, 4 CPUs, and 50 GB storage.
![win](insert second photo)

## Step 3: Ensured connectivity with the VM 
> VM's Network Settings
![thrid](3rd pic)
- Any attempt to "ping" the VM was timing out because of firewall protections
![before](add 4thpic)
- Turned off firewall settings to ensure the VM was reachable.
> It is not recommended to do this in a normal working environment. This was solely done for the purpose of this lab.
![insert 5th pic](5th)

- VM was successfully "pinged" after the firewall was turned off.
![work](6th pic)

## Step 4: First scan; ran a basic scan on Nessus
> The "basic scan" performs a simple vulnerability scan of the target.
- AFter the basic scan was completed the following vulnerabilities were found:
- **31 info** level
- **2 medium** level vulnerabilities.
![basic](insert 7th pic)

## Step 5: Configured the VM for credentialed scans
- Enabled "Remote Registry" allowing Nessus to connect to the VM's registry remotely for a credentialed scan.

![insert](insert 8th pic)

- Changed the UAC (User Account Control) to "never notify me"

![fa}(9th pic)

- Added a DWORD Key to the Windows Registry to further disable user account control for the remote account that will be used to connect to the VM.

![dor](insert10th pic)

## Step 6: Second scan; ran a credentialed scan on Nessus

> The credentialed vulnerability scan took much longer to complete, however, it showed much better results.
- After the credentialed vulnerability scan was completed the following vulnerabilities were found:
-  **34 critical** level vulnerabilities
-  **129 high** level vulnerabilities
-  **20 medium** level vulnerabilities
-  **1 low** level vulnerability
-  **182 info** level vulnerabilities.

This demonstrates the importance of doing credentialed scans on critical resources in an organization. With a basic scan 0 critical/high vulnerabilities were found, however, with a credentialed scan 163 total critical/high level vulnerabilities were found. 

![easy](insert 11th pic)




## Step 7: Installed a legacy version of Firefox
> This was done to create and inspect more vulnerabilities, and to gain more experience inspecting and fixing vulnerabilities.

- After the scan was completed the following vulnerabilities were found:
- **125 critical**
- **210 high** level vulnerabilities
- **37 medium** level vulnerabilities
- **1 low** level vulnerability
- **183 info** level vulnerabilities
![insert](12th pic)

## Step 8: Remediated the vulnerabilities

After inspecting the vulnerability scans, I viewed the solutions for them and made some remediations. The remediated vulnerability scans are as follows:





## Comparing the different vulnerability scans

| Basic Scan          | Credentialed Scan            | Crednetialed Scan with Firefox            | Remediated Scan          |
|---------------------|--------------------------------|--------------------------------|---------------------|
| ![Image1](path/to/image1.png) | ![Image2](path/to/image2.png) | ![Image3](path/to/image3.png) | ![Image4](path/to/image4.png) |
| Description 1       | Description 2       | Description 3       | Description 4       |






  




  
