# WLAN-Configuration

# Table of Contents
1. [Introduction](https://github.com/the-original-copy/WLAN-Configuration/blob/main/README.md#introduction)<br/>
2. [Objectives](https://github.com/the-original-copy/WLAN-Configuration/blob/main/README.md#objectives)<br/>
3. [Methodology](https://github.com/the-original-copy/WLAN-Configuration#methodology)<br/>
  &nbsp;&nbsp;3.1 [Part 1: Configure a Home Wireless Router](https://github.com/the-original-copy/WLAN-Configuration#part-1-configure-a-home-wireless-router)<br/>
  &nbsp;&nbsp;3.2 [Part 2: Configure a WCL (Wireless Lan Controller)](https://github.com/the-original-copy/WLAN-Configuration#part-2-configure-a-wcl-wireless-lan-controller)<br/>
4. [Conclusion](https://github.com/the-original-copy/WLAN-Configuration#conclusion)<br/>
# Introduction
In this activity, I will be diving into the practical aspects of wireless networking by
configuring both a home router and a Wireless LAN Controller (WLC)-based network. My objective is to implement robust security measures using WPA2-PSK and
WPA2-Enterprise protocols. The journey begins with setting up a home router to
enable Wi-Fi connectivity across various devices. Following that, I'll secure this
network using WPA2-PSK. Transitioning to a more complex setup, I will configure
interfaces and WLANs on a WLC. This involves securing the WLAN with
WPA2-PSK and WPA2-Enterprise, followed by connecting hosts and verifying their
connectivity. This hands-on experience will solidify my understanding of WLAN
configuration and security implementation

# Objectives

1. Configure a home router to provide Wi-Fi connectivity to a variety of devices
2. Configure WPA2-PSK security on a home router
3. Configure interfaces on a WLC
4. Configure WLANs on a WLC
5. Configure WPA2-PSK security on a WLAN and connect hosts to WLAN
6. Configure WPA2-Enterprise on a WLAN and connect hosts to the WLAN
7. Verify WLAN connectivity

# Methodology
## Part 1: Configure a Home Wireless Router
## i) Step 1: Change DHCP settings

I begun by opening the home wireless Router GUI and configured the router IP and DHCP settings where I enabled DHCP Server and set the router's IP address as 192.168.6.1 as shown below:

<div align="center">

![image](https://github.com/user-attachments/assets/308e92af-6f64-406a-b5b6-6b8d4821888c)
  
</div>

Once I configured the internet interface of the router to receive it’s IP address over
DHCP the address it received was: **192.168.0.1**

## ii) Step 2: Configure the Wireless LAN

In order to complete this step I clicked on the wireless tab and set the SSID to
HomeSSID as described in the WLAN table. Next I selected channel 6 - 2.437 Ghz
and enabled SSID broadcast so that all the wireless hosts could see the broadcast as
shown in the picture below:

<div align="center">

![image](https://github.com/user-attachments/assets/e600e90a-d8c3-4976-a1c6-52c39d5a4ec7)

  
</div>

The image below verify’s that the wireless hosts could see the SSID broadcast:
<div align="center">

![image](https://github.com/user-attachments/assets/bb46a1c7-b34e-4ea0-9a99-e148ca8aa63b)

</div>

## iii) Step 3: Configure Security

Inorder to complete this step I first accessed the wireless security tab and at the
2.4Ghz section selected the security mode as WPA2 Personal and used the Passphrase
given in the WLAN table as shown below:

<div align="center">

![image](https://github.com/user-attachments/assets/70a852f1-fcf8-41a9-8453-38061f3c1269)


</div>

Finally I changed the default password by clicking the administration tab and
changing the default password as shown below:

<div align="center">

![image](https://github.com/user-attachments/assets/6f0a89f6-1006-4316-bae6-ac641399ff35)


</div>

## Step 4: Connect Clients to the Network

In order to complete this step I first connected the laptop, phone and tablet to the
router via the PC wireless option as show in the images below:

<div align="center">

![image](https://github.com/user-attachments/assets/9da23c05-1076-4f58-91fc-0b0cf20be493)

</div>

For the smartphone; I selected the config tab followed by the wireless option. From
the wireless option tab I inputted the SSID and the authentication option of
WPA2-PSK which enabled me to enter the Passphrase leading to a successful
connection as shown below:

<div align="center">

![image](https://github.com/user-attachments/assets/feb06977-f4b4-4637-9610-034f5d1403af)

</div>

For the tablet I followed the same steps as connecting the smartphone as a successful
connection was setup as shown below:

<div align="center">

![image](https://github.com/user-attachments/assets/df9d346f-7776-4668-b95b-4fbcfd3da47e)


</div>

Finally I had to verify connectivity. From the phone I pinged the Laptop and web
server and below is the result I got:

<div align="center">


![image](https://github.com/user-attachments/assets/bc82d767-0153-4589-a729-ec968e8703d8)

</div>


## Part 2: Configure a WCL (Wireless Lan Controller)
## i) Step 1: Configure VLAN interfaces

To complete this step I first accessed the WLC-1 management interface via a web
browser as show below:

<div align="center">

![image](https://github.com/user-attachments/assets/a161e89f-63cc-40f5-8b43-c8b159b85af7)

</div>

Next I configured the WLANs by proceeding to the controller tab and selecting the
interfaces option as shown below:

<div align="center">

![image](https://github.com/user-attachments/assets/ebdf82a0-414f-4a55-bfec-e41b517ccaf6)

</div>

Next I configured the interface for the first WLAN as shown below:

<div align="center">

![image](https://github.com/user-attachments/assets/5f15e390-83e5-4fba-8f88-92972bc3b719)

</div>

For the second interface the settings are as shown below. For the Primary DHCP
server the gateway address used was **192.168.5.1**:

<div align="center">

![image](https://github.com/user-attachments/assets/983e0be7-5990-4e43-9113-be90ffe45725)

</div>

The resulting interfaces are as show below. The newly created interfaces are disabled
by default:

<div align="center">

![image](https://github.com/user-attachments/assets/32725224-ca07-4157-80a5-8280a4114550)


</div>

## ii) Step 2: Configure a DHCP scope for the wireless management network

In order to complete this step I selected the Internal DHCP Server and proceeded to
the DHCP scopes and added the new entry as per the instructions. This is shown in
the image below:

<div align="center">

![image](https://github.com/user-attachments/assets/d0ca98e6-8176-463d-8003-0b291b202a39)



</div>

The resulting DHCP Scopes are as shown below:

<div align="center">


![image](https://github.com/user-attachments/assets/f1d034b9-fa5b-4272-8230-e2f63df51768)


</div>

## iii) Step 3: Configure the WCL with external server address

The first action I performed to complete this step is to configure the RADIUS server
information as per the instructions given. I did this by selecting the Security tab
followed by adding a new entry after selecting the RADIUS Authentication tab as
shown below:

<div align="center">


![image](https://github.com/user-attachments/assets/715c6d34-3e63-4e08-b563-2337519f4a0b)


</div>

The result was an added entry as shown below:


<div align="center">

![image](https://github.com/user-attachments/assets/9530cf4a-e5a8-4304-b49f-c26a06d1e819)



</div>

After this I configured the WLC to send logs information to an SNMP server by
selecting the Management tab followed by the SNMP option. From here I selected the
trap receivers option in order to create the required entry as shown below:

<div align="center">


![image](https://github.com/user-attachments/assets/79fe87d9-bb20-4070-ac94-63aafc6febb1)

</div>

The result was an added entry as shown below:

<div align="center">


![image](https://github.com/user-attachments/assets/926d35c5-6ae8-4b1f-906e-ae786be971ff)


</div>

# Conclusion
