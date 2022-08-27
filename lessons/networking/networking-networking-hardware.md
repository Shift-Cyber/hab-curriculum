# [Networking] Hardware
*Understanding components of a common home router*

![Wi-Fi Router](.rsrc/wifi-router.jpeg)

# Objectives
- Understand common components of a home router
- Learn network specific terminology
- Learn what components could be useful to solve connection requirements

# Introduction
A total of 5 billion people around the world use the internet today. Networking hardware allow different devices to talk to one another at near instantaneous speeds regardless of where they are in the world. These technologies form the physical backbone of the internet. You may be familiar with a home router that allows you access to the internet and in this lesson, you will learn what components are part of the home router.

1. [Home Router Components](#home-router-components)
2. [Switch](#switch)
3. [Router](#router)
4. [Broadband Connection](#broadband-connection)
5. [Wireless Access Point](#wireless-access-point)
6. [Firewall](#firewall)

# Lesson
## Home Router Components
Home routers typically contain following components:
* Switch (Ethernet LAN)
* Router (Ethernet WAN)
* Broadband Connection
* Wireless Access Point (Wi-Fi)
* Firewall 

![image](https://user-images.githubusercontent.com/18094862/179405675-5a1c6c1b-4f70-4b8e-89a4-982c522729c4.png)

## Switch
Switches facilitate sharing of resources on a Local Area Network (LAN). LAN includes all of the computers, printers, and servers in one location where all of the connected devices share information and usually these are all of the devices you own and trust. The highlighted section below represents a switch as a component of a home router. 

![switch](https://user-images.githubusercontent.com/18094862/187009652-a687f468-f905-4f3f-b263-9cbec72a06b1.JPG)

Ethernet cables are used to connect devices on the network. Below is the picture of an ethernet cable. 
![image](https://user-images.githubusercontent.com/18094862/179407510-eecacf84-1513-4565-a9e4-55acc99d9fc0.png)

## Router
Routers connect to an Internet Service Provider (ISP) which is part of the Wide Area Network (WAN). WAN is network that can span the entire globe. An example of the largest WAN is the internet. The way we can get access to the internet is by connecting to the ISP. The ISP has connections to other routers on the internet creating a very large web-like network with many different paths between each source and destination. The ISP charges us to provide that service. 

Just as a switch connects multiple devices to create a Local Area Network, a router connects multiple switches, and their respective networks, to form an even larger network. Home routers are different than enterprise routers used by ISPs within the internet primarily on their processing power, but conceptually they are the same.  

Depending on the ISP, various different forms broadband connections are used which is described in next section. 
![image](https://user-images.githubusercontent.com/18094862/179405602-b95cc6ef-db56-4b31-93b6-8354b759b69c.png)

## Broadband Connection
Broadband connection refers to the high-speed internet access technology which the ISP provides. The fastest broadband connection is fiber which is almost always preferable, but if that is not available then connections such as cable modem and DSL are preferred, wireless and satellite are less reliable, but in cases of rural networks they are the only ones available.  

* Cable Modem
  * Cable modem service uses coaxial cables that deliver picture sand sound to TV.
* Digital Subscriber Line (DSL)
  * DSL service uses traditional copper telephone lines.
* Fiber
  * Fiber technology uses light to carry data through transparent glass fibers
* Wireless
  * Wireless service uses radio link between home location and nearest service provider facility
* Satellite
  * Satellite service is a type of wireless broadband, but the communication is with a satellite rather than a nearby facility

## Wireless Access Point
Wireless Access Point component of the router provides Wi-Fi access to all of the devices on your local network without the need for Ethernet cables. 

Wi-Fi standard includes two frequency bands 2.4 GHz and 5 GHz. Wi-Fi frequency bands are frequency ranges within the wireless spectrum that are designated to carry Wi-Fi. 2.4 GHz frequency band includes 14 channels, but since they need to be separated to reduce interference only channels 1, 6, and 11 can be used simultaneously without any interference between each other. 5 GHz band has 42 channels where 24 channels are non-overlapping. 

The transmit power of an access point radio is proportional to its effective range. The higher the transmit power, the farther a signal can travel, and the more obstructions it can effectively penetrate.

The advantage of 2.4 GHz band is that it is available at a greater distance from the access point and it is available for a lot of devices, but it is much more congested.
The advantage of 5 GHz band is that it allows much more bandwidth with much less interference, but it is available at shorter distances and it is not compatible with many older devices. 

## Firewall 
Home routers also contain a firewall which appropriately protects devices on your LAN from devices on the internet. If you have ever played games on consoles, some of them require modification of the home router firewall in terms of allowing certain ports through or setting up port forwarding which allows devices on the internet to connect to the console on your local LAN. 

Firewalls create rules that allow or deny devices from talking to one another. 

There are two ways of accomplishing that
* Whitelisting - Everything is denied by default and only things in the rule list are allowed
* Blacklisting - Everything is allowed by default and only things in the rule list are blocked

# Check YoSelf
## Q1 - What can make Wi-Fi signal stronger for a device that is further away from the router?
- Increasing Power
- Changing to 2.4 GHz band instead of 5 GHz band 

## Q2 - What is the preferred firewall rule method (whitelist/blacklist) and why?
- Whitelist <--- because it allows minimal access to your network and only specific things are allowed based on the rules

## Q3 - Can a home router function without Ethernet LAN (switch)?
a. ```Yes```<---<br>
b. ```No```<br>

# Keep Going, Next Steps
Check out the following curated resources if you'd like to keep learning about this topic to dominate hard challenges.
1. Resource 1 - [What Is a Router](https://www.cisco.com/c/en/us/solutions/small-business/resource-center/networking/what-is-a-router.html)
2. Resource 2 - [Types of Broadband Connections](https://www.fcc.gov/general/types-broadband-connections)
3. Resource 3 - [Understanding Wireless Radio Channels](https://www.juniper.net/documentation/en_US/junos-space-apps/network-director4.0/topics/concept/wireless-radio-channel.html)
