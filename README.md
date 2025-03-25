<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this project, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create a virtual machine (VM) in Windows 10 and one in Linux (Ubuntu)
- Remote Desktop into Windows VM and download Wireshark
- Open Wireshark and PowerShell as Admin
- Observe ICMP traffic
- Configuring a Firewall (Network Security Group)
- Observe SSH traffic

<h2>Actions and Observations</h2>

<h4>1. Virtual machines post creation.</h4>  

![image](https://github.com/user-attachments/assets/62aefcc0-132f-4cf4-aeda-0649cc3b3c48)

![image](https://github.com/user-attachments/assets/0a422f05-f364-41c3-baa0-02658e233d3b)

<br>
<br>

<h4>2. Remote Desktop into Windows VM and install Wireshark</h4>

![image](https://github.com/user-attachments/assets/b9793e80-f932-4b02-866b-609a00fa67f1)

![image](https://github.com/user-attachments/assets/9f1ed518-b69b-4079-bb7c-363ca3212bda)
https://www.wireshark.org/download.html

<br>
<br>

<h4>3. Open Wireshark and PowerShell.</h4>

![image](https://github.com/user-attachments/assets/f0e1b859-71b5-431c-bbc2-aae637ee445f)


<br>
<br>

<h4>4. Observe ICMP traffic</h4>

Filter icmp protocol in wireshark -> ping the private IP address of the Ubuntu VM in PowerShell

![image](https://github.com/user-attachments/assets/40b6f5f4-28fe-48cd-b57d-8aab656bfcb6) 

![image](https://github.com/user-attachments/assets/43bbf66c-d79f-4771-8047-e151a0c46443)

<br>
<br>

<h4>5. Configuring a Firewall (Network Security Group)</h4>

Initiate non-stop ping from windows VM to Ubuntu in PowerShell

![image](https://github.com/user-attachments/assets/1498dcd5-d8c6-4167-8ec6-7228c0fe51ef)

<br>

Add inbound security rule to deny ICMP traffic
![image](https://github.com/user-attachments/assets/faa82324-460d-481f-9d50-92e7caa170a5)

Once denied, all requests will time out.

![image](https://github.com/user-attachments/assets/5667e010-0486-45b7-9abf-79ca682332bc) 

<br>

If you allow ICMP traffic (or delete the security rule), replies will resume. 

![image](https://github.com/user-attachments/assets/cb35776f-11d1-42e9-ab7e-de893ec59b3a)

![image](https://github.com/user-attachments/assets/a7d8df4b-3991-40b2-8e54-b769cb4eea36)

<br>
<br>

<h4>6. Observe SSH traffic</h4>









