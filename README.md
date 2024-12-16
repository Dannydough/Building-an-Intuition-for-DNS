# Building-an-Intuition-for-DNS

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


6.)

<p>
<img src="https://imgur.com/rxrv2np.png" height="80%" width="80%" alt="Configuration Steps"/>
</p>
<p>

**Local DNS Cache Exercise**
