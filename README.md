<p align="center">
<img src="https://i.imgur.com/MwrkwEQ.png" alt="DNS Photo"/>
</p>

<h1>Understanding DNS</h1>

This lab explores the practical application of DNS, a foundational concept in IT that is often covered in theory across various resources. In this exercise, I will configure DNS records to understand how they function in real-world scenarios. Building on a previous lab where a client was joined to the domain ernestotest.com, I am logged in as Jane Doe (an administrator) on both the client and domain controller VMs. Administrative privileges are required for this lab to ensure proper configuration and functionality.
<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- Command Prompt

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 Pro (21H2)

<h2>DNS Configuration Steps</h2>

**A-Record Exercise**


1.) Log in to DC-1 using your domain administrator account (e.g., mydomain.com\jane_admin). Log in to Client-1 using an administrator account (e.g., mydomain\jane_admin).

<p>
<img src="https://imgur.com/LnPuk2a.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

2.) From Client-1, attempt to ping "mainframe" and observe that the attempt fails.

<p>
<img src="https://imgur.com/S1EU0zD.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

3.) Use nslookup to query "mainframe" from Client-1 and observe that the query fails due to the absence of a DNS record.

<p>
<img src="https://imgur.com/9XcmVG4.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

4.) Create a DNS A-record on DC-1 for "mainframe" and configure it to point to DC-1's private IP address.

<p>
<img src="https://imgur.com/fQGUNuf.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

<p>
<img src="https://imgur.com/mXD9IdW.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

<p>
<img src="https://imgur.com/fY9dQbD.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

5.)  Return to **Client-1** and retry pinging "mainframe." Verify that the ping is now successful.

<p>
<img src="https://imgur.com/rxrv2np.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

**Local DNS Cache Exercise**

6.) On DC-1, update the A-record for "mainframe" to point to 8.8.8.8.

<p>
<img src="https://imgur.com/PTNSfxZ.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>


7.) Return to Client-1 and ping "mainframe" again. Note that it still resolves to the old address due to cached DNS records.

<p>
<img src="https://imgur.com/mtTvcx3.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

8.) View the local DNS cache on Client-1 by running the command: "ipconfig /displaydns"
Then, flush the DNS cache by running: "ipconfig /flushdns"

<p>
<img src="https://imgur.com/Edf2Ena.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

<p>
<img src="https://imgur.com/3nOtK8c.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

<p>
<img src="https://imgur.com/hE0qMp1.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

9.) Verify that the DNS cache is now empty by running the command: "ipconfig /displaydns"

<p>
<img src="https://imgur.com/YhpMGgH.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

<p>
<img src="https://imgur.com/O7MWIgH.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

<p>
<img src="https://imgur.com/wtHy7tu.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

<p>
<img src="https://imgur.com/5h62y3M.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

10.) Attempt to ping "mainframe" again from Client-1. Observe that the new address from the updated DNS record (8.8.8.8) is now being resolved and displayed.

<p>
<img src="https://imgur.com/nkjtIjv.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

**CNAME Record Exercise**

11.) On DC-1, create a CNAME record that maps the hostname "search" to "www.google.com".

<p>
<img src="https://imgur.com/ftb5JyA.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

<p>
<img src="https://imgur.com/X7ZTJCa.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

12.) Return to Client-1 and attempt to ping "search". Observe that the CNAME record resolves "search" to "www.google.com", and the ping displays the IP address associated with www.google.com.

<p>
<img src="https://imgur.com/yYz6SSN.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

13.) On Client-1, run the following command: "nslookup search" Observe that the output shows the CNAME record pointing "search" to www.google.com. The result will also display the IP address associated with www.google.com.

<p>
<img src="https://imgur.com/ComkbuT.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>
<h2>Conclusion</h2>

*This lab provided hands-on experience with DNS configuration, including creating and updating A-records, working with local DNS cache, and configuring CNAME records. Through these exercises, I observed the practical application of DNS in resolving hostnames to IP addresses and ensuring accurate network communication. These skills are fundamental for managing and troubleshooting DNS in a business environment, laying the groundwork for advanced network management tasks.*
