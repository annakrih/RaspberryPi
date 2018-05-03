
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

### Initial setup of each RP
There is quite a lot of setup needef or each machine. In this section we will discuss what needs to be done on each and every RP machine to set it up. In short it is the following: 

- [ ] Get an operating system to the SD memory card - We used Rasbian
- [ ] Change the keyboard layout of the OS
- [ ] Change the name of the RP
- [ ] Connect each RP to internet so that we can...
- [ ] ... dowload docker to each RP

##### Get an operating system to the SD memory card
There are various [OS that can be setup on a Raspberry Pi](https://www.raspberrypi.org/downloads/), we chose to use Rasbian. Rasbian is a version of the [Debian](https://en.wikipedia.org/wiki/Debian) which is a Unix-like operating system. We also choose to use the version of Rasbian without a desktop, that is Rasbian Stretch Lite. 

The steps to get the OS to the SD cards are the following: 
* Download [Ether](https://etcher.io/) 
* Download the [Raspbian Stretch Lite image](https://www.raspberrypi.org/downloads/raspbian/)
* Unzip the Rasbian Strech Lite image. 
* Open Ether and insert an SD card to your own computer
* In Ether, choose the .img image file for the OS, the SD card, and then click **Flash!**

##### Change the keyboard layout of the OS Þarf að fara yfir og laga!!
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
##### Change the name of the RP
##### Connect each RP to internet
##### Dowload docker to each RP




## Discussion 



