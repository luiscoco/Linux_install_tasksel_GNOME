# Linux VM install GUI Desktop XFCE

## 1. (Option1) Create in Azure a Linux Ubuntu server VM (Spot instance)


## 1. (Option2) Create in AWS a Linux Ubuntu server VM (Spot instance)

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/80872937-4e03-463a-83ae-a271343ac1ce)

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/9173ff09-b40b-45db-806c-da7044c51cec)

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/b94cd032-a596-4160-9efd-65924670666d)

Move the private key *.pem file from Download folder to .ssh folder 

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/e4327c04-dff3-498e-b417-cbd488406387)

After creating the ssh key pair we select it

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/c86479ba-8bc7-4e44-9687-9060c95c70da)

Now we set the networking options. We only have to include a new inbound rule for RDP 3389 port

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/ecb0a621-fdd9-42ce-a774-a1cea9ad2a56)

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/8097586b-0f9c-4a07-b197-2e7fb20beb46)

Now we set the VM hard disk capacity to 30 Gb because is free

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/21591d34-5ad9-4391-acf3-8f580dea4c07)

Finally we request a Spot instance for reducing the VM cost

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/c5df0234-26d7-4c98-b004-da07d1834059)

Then we create the Linux VM pressing the "Launch Instance" button

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/e2bec630-8251-429e-8c39-6fb0a46ed468)

We check the VM was created, we press in the VM id link

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/4935341d-ce34-4f2a-a831-4e0472d818c9)

See the new VM in the instances list

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/04049b83-5f7a-47ea-8fc1-464d596c9ce7)

Select the instance and press the "Connect" button

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/235890bd-9643-459f-86b2-667272d10e58)

For connecting to the Linux VM via SSH type press the "ssh client" tab and copy the command

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/99da5e9b-fb4a-469d-9de3-f5faed8b97a4)

In our case we placed the private key file *.pem in the .ssh path, then for connecting to the Linux VM we have to type the command:

```
ssh -i C:/Users/LEnriquez/.ssh/mynewxfceawskeypair.pem ubuntu@ec2-35-180-41-178.eu-west-3.compute.amazonaws.com
```

![image](https://github.com/luiscoco/Linux_install_XFCE_GUI_Desktop/assets/32194879/10c8685a-67b4-41d5-8e98-54e6ab2e743b)

You can see we enter in our Linux VM with the user "ubuntu"

## 2. Install XFCE (GUI Desktop for Ubuntu Linux VM)

https://www.xfce.org/

**IMPORTANT NOTE**: top 10 best Linux desktop environments

https://tecadmin.net/best-linux-desktop-environments/

Run this commands to install xfce in the Linux VM

```
sudo apt-get update

sudo DEBIAN_FRONTEND=noninteractive apt-get -y install xfce4

sudo apt install xfce4-session
```

## 3. Install and configure XRDP to use Remote Desktop with Ubuntu

https://learn.microsoft.com/en-us/azure/virtual-machines/linux/use-remote-desktop?tabs=azure-cli

Run this commands to install and configure xrdp in your Linux VM:

```
sudo apt-get -y install xrdp

sudo systemctl enable xrdp

sudo adduser xrdp ssl-cert

echo xfce4-session >~/.xsession

sudo service xrdp restart

sudo passwd azureuser
```

## 4. Be user you open the RDP port

For Azure Linux VM run the command:

```
az vm open-port --resource-group myResourceGroup --name myVM --port 3389
```

For AWS Linux VM open the 3389 port for RDP when configuring/creating the new Linux VM instance



## 5. Install VSCode and extensions




## 6. Install Google Chrome





## 7. Install .NET 8




## 8. Install Docker 





## 9. Install Portainer




## 10. Download and run a MongoDB docker container




## 11. Install Studio 3T for MongoDB







## 11. Install Node.js






## 12. Install Angular CLI






## 13. 




