<div align="center">
  <img height="150" src="https://github.com/Fluffyzwz/thinkpad-2015-hackintosh/assets/85907829/842f78d5-d447-4012-b491-8cad1356c250"  />
</div>

<p align="center">
   <strong>OpenCore Version: </strong>0.8.0
</p>
</br>

###

<h1 align="center">hey there 👋</h1>
<li> Note: if you get a black screen on the internal display at boot, press "ctrl + shift + insert" and then any key 👋<li>

  
###

<h3 align="left">👩‍💻 Lenovo ThinkPad X1 Carbon 3rd Gen OpenCore Configuration</h3>

<h3 align="left">🛠 Welcome to my ted talk.</h3>

<details>  
<summary><strong>My ThinkPad X1C3 Hardware Specs 💻</strong></summary>
</br>

| Model              | Lenovo ThinkPad X1 Carbon 3rd Gen                                                                         |
|:-------------------|:----------------------------------------------------------------------------------------------------------|
| Processor          | Intel Core i7-5600U (2C, 4T,  2.60Hz / 3.20GHz) vPro (The best compatibility with macOS)                  |                                               
| Graphics           | Integrated Intel HD Graphics 5500                                                                         |
| Memory             | 8GB Soldered                                                                                              |
| Display            | 14" HD (2560x1440) non-touch                                                                              |
| Storage            | 512GB S.A.T.A PCIE SSD                                                             


</details>

</details>


<details>  
<summary><strong>Hardware Compatibility 🧰</strong></summary>
</br>

## What works:
- Intel HD Graphics 5500
- Brightness Control
- Keyboard & Backlit
- TrackPoint (TrackPoint / Nipple Mouse Warriors, rejoice!)
- TouchPad with Gestures
- Secure Boot
- Sleep and Wake
- Audio and Mini DisplayPort Audio
- Power Management
- USB Ports
- Mini DisplayPort
- HDMI
- Wireless and Bluetooth
- [DRM content](https://github.com/acidanthera/OpenCorePkg/releases) 

## What doesn't work:
- FingerPrint Reader

</details>

</details>

## Lenovo ThinkPad X1 Carbon 3rd Gen Hackintosh Guide

<details>  
<summary><strong>Getting Started</strong></summary>
</br>

To start you'll need the following:

You must have the following items:
- Lenovo ThinkPad X1 Carbon 3rd Gen (Obviously 😁).
- Access to a working Windows machine with Python installed.
- A pendrive with more than 4 GB (Keep in mind, during the preperation we will format the disk to create the install media).
- an Internet connection via Ethernet.
- 1-2 hours of your time.

</details>

<details>  
<summary><strong>Creating the USB Installer </strong></summary>
</br>

1. To grab legacy installers is super easy, first grab a copy of [OpenCorePkg](https://github.com/acidanthera/OpenCorePkg/releases) and head to /Utilities/macrecovery/. Next copy the folder path for the macrecovery folder. 

<img width="974" alt="file-path 0aea4278" src="https://user-images.githubusercontent.com/72415505/156628158-190cba5d-6114-4972-aa83-f1b14749e34d.png">


#
2. From here, you'll want to open up a Command Prompt and cd into the macrecovery folder that we copied earlier:

```cd Paste_Folder_Path```

<img width="917" alt="command-prompt 53392eba" src="https://user-images.githubusercontent.com/72415505/156628358-c2692037-80ac-40f9-bb3b-9a424442dafe.png">

#
3. Now run one of the following depending on what version of macOS you want(Note these scripts rely on [Python](https://www.microsoft.com/en-us/p/python-39/9p7qfqmjrfp7?activetab=pivot:overviewtab) support, please install if you haven't already):

 ```
# Monterey (12)
python macrecovery.py -b Mac-E43C1C25D4880AD6 -m 00000000000000000 download
```

This will take some time, however once you're finished you should get either BaseSystem or RecoveryImage files:

![macrecovery-after 4c24ba88](https://user-images.githubusercontent.com/72415505/156629881-3d0e18a5-79cf-465e-a054-44b39a77b47f.jpg) <img width="973" alt="basesystem-example 93778929" src="https://user-images.githubusercontent.com/72415505/156629925-77869c1f-19ee-463f-bcc7-cafb2be09866.png">

#
4. Download [Rufus](https://rufus.ie/en/), set the BOOT selection as not bootable, set File System as Large FAT32, click Start, and delete all file autorun in USB Drive partition.

![format-usb-rufus 43feba9e](https://user-images.githubusercontent.com/72415505/156631083-73e33087-d51e-42e4-a804-e93afad7c2ca.png)

#
5. Next, go to the root of this USB drive and create a folder called com.apple.recovery.boot. Then move the downloaded BaseSystem or RecoveryImage files. Please ensure you copy over both the .dmg and .chunklist files to this folder:

<img width="824" alt="com-recovery 805dc41f" src="https://user-images.githubusercontent.com/72415505/156631343-529ca3ee-9e79-4e21-bab1-7305b4ed3df9.png">

#

6. Open up and extract the EFI folder archive you downloaded earlier.


7. Copy the folder named, "EFI," to the root of your USB Drive.

8. Restart your computer.


</details>

<details>  
<summary><strong>Installing macOS</strong></summary>
</br>

1. Open the BIOS and disable all the security options. (Security Chip, Intel (R) AT Module Activation, and Computrace Module)

2. Boot via your Flash Drive.

11. Boot the macOS installer.

12. Now open Disk Utility and format your internal or external Hard Drive or SSD as APFS.

13. Follow the on-screen prompts and install macOS.

14. Your system might reboot during the installation.

15. Now after install again boot into your usb drive and then select the drive that you installed macOS on.

16. Now copy the EFI Folder to the EFI Partition and overwrite it with the one system created.

17. Now try booting macOS without the USB drive.

18. Congratulations, you've successfully hackintoshed your Lenovo ThinkPad X1 Carbon 3rd Gen.

