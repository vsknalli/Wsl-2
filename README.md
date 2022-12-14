## WSL commands:      
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart   
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart    
wsl --set-default-version 2   
wsl --install -d Ubuntu-20.04    
```    


## Ubuntu GUI commands:    

### For Cinnamon GUI:     
```
sudo apt update && sudo apt -y upgrade
sudo apt-get purge xrdp
sudo apt install -y xrdp
sudo apt install -y cinnamon

sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak
sudo sed -i 's/3389/3390/g' /etc/xrdp/xrdp.ini
sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini
sudo sed -i 's/xserverbpp=24/#xserverbpp=24\nxserverbpp=128/g' /etc/xrdp/xrdp.ini
echo cinnamon > ~/.xsession
sudo nano /etc/xrdp/startwm.sh    
```     
Comment these lines to:
#test -x /etc/X11/Xsession && exec /etc/X11/Xsession        
#exec /bin/sh /etc/X11/Xsession       

Add the following lines:   
#cinnamon    
cinnamon  

### For XFCE4 GUI:     
```
sudo apt update && sudo apt -y upgrade
sudo apt-get purge xrdp
sudo apt install -y xrdp
sudo apt install -y xfce4
sudo apt install -y xfce4-goodies

sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak
sudo sed -i 's/3389/3390/g' /etc/xrdp/xrdp.ini
sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini
sudo sed -i 's/xserverbpp=24/#xserverbpp=24\nxserverbpp=128/g' /etc/xrdp/xrdp.ini
echo xfce4-session > ~/.xsession
sudo nano /etc/xrdp/startwm.sh    
```     
Comment these lines to:
#test -x /etc/X11/Xsession && exec /etc/X11/Xsession        
#exec /bin/sh /etc/X11/Xsession       

Add the following lines:   
#xfce       
startxfce4    

     
## Start XRDP using:         
```     
sudo /etc/init.d/xrdp start
```     
    
## Now in Windows, use Remote Desktop Connection
Set computer link to: localhost:3390   
Login using your Ubuntu username and password      

## Good links:
Microsoft GUI announcement: https://devblogs.microsoft.com/commandline/the-windows-subsystem-for-linux-build-2020-summary/      
Ubuntu WSL2 GUI Install:     
https://dev.to/darksmile92/linux-on-windows-wsl-with-desktop-environment-via-rdp-522g    
WSL 2 install: https://docs.microsoft.com/en-us/windows/wsl/install-win10    
Docker for WSL2: https://docs.docker.com/docker-for-windows/wsl/    
What is WSL? https://docs.microsoft.com/en-us/windows/wsl/about    
WSL documentation: https://docs.microsoft.com/en-us/windows/wsl/    
WSL 2 Announcement: https://devblogs.microsoft.com/commandline/announcing-wsl-2/    
