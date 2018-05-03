
# Raspberry Pi Cluster
<img src="/RUlogo.png" align="right" width="250"/>  

*A fully fledged miniature cloud datacenter that supports running microservices and serverless applications using a Raspberry cluster.*

3 week course  
Spring 2018 

**Students**:  
Anna Kristín Halldórsdóttir (annah14@ru.is)  
Ásgeir Örn Nordquist (asgeiro14@ru.is)  
Birna Vala Eyjólfsdóttir (birna14@ru.is)   
& Sandra N. Sigurðardóttir (sandra14@ru.is)  

**Supervisor**:  
Mohammad Hamdaqa

## Introduction 


## Method 

### 1.  Initial setup of each RP
There is quite a lot of setup needef or each machine. In this section we will discuss what needs to be done on each and every RP machine to set it up. In short it is the following: 

- [ ] Get an operating system to the SD memory card - We used Rasbian
- [ ] Change the keyboard layout of the OS
- [ ] Change the name of the RP
- [ ] Connect each RP to internet so that we can...
- [ ] ... dowload docker to each RP
- [ ] ... and make swarm

#### &nbsp;&nbsp;&nbsp;&nbsp; 1.1  Get an operating system to the SD memory card
There are various [OS that can be setup on a Raspberry Pi](https://www.raspberrypi.org/downloads/), we chose to use Rasbian. Rasbian is a version of the [Debian](https://en.wikipedia.org/wiki/Debian) which is a Unix-like operating system. We also choose to use the version of Rasbian without a desktop, that is Rasbian Stretch Lite. 

The steps to get the OS to the SD cards are the following: 
* Download [Ether](https://etcher.io/) 
* Download the [Raspbian Stretch Lite image](https://www.raspberrypi.org/downloads/raspbian/)
* Unzip the Rasbian Strech Lite image. 
* Open Ether and insert an SD card to your own computer
* In Ether, choose the .img image file for the OS, the SD card, and then click **Flash!**


#### &nbsp;&nbsp;&nbsp;&nbsp; 1.2  Change the keyboard layout of the OS Þarf að fara yfir og laga!!
The keyboard language was changed by following these steps:
1. Run the command ``` sudo raspi-config ```
2. Navigate to option number 4. Localisation Options
3. Keyboard Layout (?)
4. Pick the keyboard layout that is already selected
5. Pick other
6. Pick Icelandic
7. Select ok to everything untill first page pops up again
8. Navigate down to the finish button, go to lowest and then press right arrow to select lowest options 

The reason for changing the keyboard was to make working on the Raspberry Pi's easier, we were working with an Icelandic keyboard so it became necisarry for us to change it. To change the keyboard back the same steps can be made but by selecting the desired keyboard language

#### &nbsp;&nbsp;&nbsp;&nbsp; 1.3  Change the name of the RP
The names of the RP's were changed with the following steps:
1. Set up and run the RP that you want to change the name of
2. Run the command ``` sudo nano /etc/hosts ```
3. There you change the name to what you want it to be, in our case it was RPC-MASTER, RPC-NODE1, etc.
4. Run command ``` sudo nano /etc/hostname ```, and repeat step 3.
5. Reboot 

#### &nbsp;&nbsp;&nbsp;&nbsp; 1.4  Connect each RP to internet
To be able to instal Docker to the RP (which is the next step), we must first connect it to the internet. To do this we were not able to use the university's network, since we couldn't find information on how to sign into a network with username and password. This section describes how to connect an internet with WPA2 security protocol with a network name and password. We connected the RP to hotspots on our phones, but a basic router would also work. 

1. Run the command:
``` 
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf 
```
2. A file opens. Be careful not to change what is in in already, but add beneath it the following
```
network={
  ssid="Network Name"
	psk="Password"
}
```
    Where the `Network Name` and `Password` are the same as what you would use if you were connecting to the network normally. 
3. Run the commands:
``` 
wpa_cli -i wlan0 reconfigure
ifconfig wlan0
``` 


*If more infomation is needed, we used [this](https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md 
) information*

#### &nbsp;&nbsp;&nbsp;&nbsp; 1.5  Dowload docker to each RP
To download Docker the RP's need to have access to the internet, then the following commands need to be run:

``` curl -sSL https://get.docker.com | sh ```

``` sudo usermod -a -G docker &USER ```

``` sudo reboot ``` or ``` reboot ```

Repeat on all RP's.

##### Make a docker swarm
On the node or RP that should be the master or leader run the following command:

``` docker swarm init ```

Then a message should appear that tells you what the token to add other RP's, or you can at any time run the command:

``` docker swarm join-token worker ```

A message with the token should appear, this token is needed to join the other nodes or RP's to the swarm, as well as the IP address of the master. The IP address can be optained by running:

``` hostname -I ```

To join the other RP's to the swarm the following command needs to be run on each of them, TOKEN stands for the token optained from the master and IP-ADDRESS is the IP address of the master:

``` docker swarm join --token TOKEN IP-ADDRESS:2377 ```

2377 is the port and should be the same in most cases.

Promoting a node to be a manager is a good security mesure, if the master RP goes offline the manager becomes the new master. To promote a node to manager you need run the following command on the master,(NAMEOFNODE should be the name of the node that should be promoted, e.g., RPC-NODE1, RPC-NODE2, etc):

``` docker node promote NAMEOFNODE ``` 



## Discussion 



