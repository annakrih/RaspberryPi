
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
- [ ] Connect each RP to internet
- [ ] Dowload docker to each RP

##### Get an operating system to the SD memory card
Flasha image á SD kortin
Farið eftir þessum leiðbeiningum:
https://www.raspberrypi.org/documentation/installation/installing-images/README.md 
Ná í https://etcher.io/ til að flasha image á SD kort
Ná í Raspian Lite og unzippa, þá á maður að hafa .img file.
SD kort sett í tölvuna. Opna Etcher og velja image-ið og SD kortið og flasha það. 
Á meðan kortið er í tölvunni, gefa því nafn með því að rename SD kortin sjálf. Við notuðum nöfnin: 
RPC-MASTER, 
RPC-NODE1, RPC-NODE2, RPC-NODE3, RPC-NODE4, RPC-NODE5, RPC-NODE6, RPC-NODE7
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
#### Connect each RP to internet
#### Dowload docker to each RP




## Discussion 



