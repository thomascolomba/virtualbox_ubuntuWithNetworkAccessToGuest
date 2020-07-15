# virtualbox_ubuntuWithNetworkAccessToGuest

How to have ubuntu running within virtualbox with network access between the host and the ubuntu guest.<br/>
<br/>

prerequisites :<br/>
- download and install virtualbox 5.2 (available here for instance : https://www.virtualbox.org/wiki/Download_Old_Builds_5_2)<br/>
- download the iso image of ubuntu 16.04 (available here for instance : https://releases.ubuntu.com/16.04/)<br/>
<br/>
The 3 main steps are :<br/>
- configure a virtualbox host-guest network<br/>
- create a new virtual machine with ubuntu<br/>
- configure the new ubuntu virtual machine for host-guest network<br/>
<br/>
<br/>

1.1)In virtualbox, click "Global Tools"<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step1-1.png?raw=true)<br/><br/>
1.2)Click "Create"<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step1-2.png?raw=true)<br/><br/>
1.3)Check the "Enable" checkbox<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step1-3.png?raw=true)<br/><br/>
1.4)Click "Machine Tools"<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step1-4.png?raw=true)<br/><br/>
<br/>
2.1)Click "New"<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step2-1.png?raw=true)<br/><br/>
2.2)Choose a name for your virtual machine, set Type to Linux and Version to Ubuntu, then click [Next]<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step2-2.png?raw=true)<br/><br/>
2.3)Choose a memory size for the virtual machine, then click [Next]<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step2-3.png?raw=true)<br/><br/>
2.4)Choose how to handle a hard disk, then click [Next]<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step2-4.png?raw=true)<br/><br/>
2.5)Choose the type of disk file type, then click [Next]<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step2-5.png?raw=true)<br/><br/>
2.6)Choose a hard disk memory allocation strategy, then click [Next]<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step2-6.png?raw=true)<br/><br/>
2.7)Choose a name for the virtual hard disk, then click [Create]<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step2-7.png?raw=true)<br/><br/>
2.8)Click "Start"<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step2-8.png?raw=true)<br/><br/>
2.9)Select the iso image of ubuntu 16.04, then click [Start]<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step2-9.png?raw=true)<br/><br/>
2.10.1)Go through the ubuntu installation process, no screenshot of this installation is provided in this tutorial.<br/>
No image provided here, you may install ubuntu as it fits you best.<br/>
2.10.2)At the end of the installation of ubuntu click [Restart Now]<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step2-10.png?raw=true)<br/><br/>
2.11)When ubuntu has restarted, shutdown the virtual machine<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step2-11.png?raw=true)<br/><br/>
<br/>
3.1)Right-click your newly created virtual machine, then select "Settings..."<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step3-1.png?raw=true)<br/><br/>
3.2)In the left panel, click the "Network" entry.<br/>
Then, in the main panel :<br/>
&nbsp;&nbsp;-click the tab "Adapter 2"<br/>
&nbsp;&nbsp;-check the "Enable Network Adapter" checkbox<br/>
&nbsp;&nbsp;-set "Attached to" to Host-only Adapter<br/>
&nbsp;&nbsp;-click the "Advanced" label<br/>
&nbsp;&nbsp;-set "Promiscuous Mode" to Allow VMs<br/>
Finally click [OK]<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step3-2.png?raw=true)<br/><br/>
3.3)Click "Start"<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step3-3.png?raw=true)<br/><br/>
3.4)When the ubuntu virtual machine is started, open a terminal and execute the "ifconfig" command. One of the entries will show the ip of ubuntu through virtualbox (it begins with "192.168"). Remember that ip address.<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step3-4.png?raw=true)<br/><br/>

<br/>
4) From outside virtualbox, open a new terminal and try to ping the ubuntu virtual machine with the ip address you remembered from the previous step (in my case I executed "ping 192.168.41.3").<br/>
If the ping command show that it receives packets then you have successfully configured virtualbox and your virtual machine.<br/>
![alt text](https://github.com/thomascolomba/virtualbox_ubuntuWithNetworkAccessToGuest/blob/master/step4-1.png?raw=true)<br/><br/>
