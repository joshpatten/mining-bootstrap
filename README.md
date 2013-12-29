Overview
=========================

This script is intended to take an Ubuntu Linux distribution and install all necessary components for Scrypt coin mining with AMD GPUs.

Rather than reading some how-to guide on setting everything up I've taken the liberty of doing all the hard work for you!

System Requirements
-------------------
The following are the system requirements for this script:

+ Ubuntu/Kubuntu/Xubuntu version 13.04 or later
+ 64 bit (are you really still running a 32 bit CPU and OS?)
+ AMD GPU capable of mining

What It Does
------------
This script performs the following:

+ Installs AMD Catalyst drivers (provided by Ubuntu fglrx-updates)
+ Installs AMD APP SDK (for openCL support)
+ Creates BFGMiner repository
+ Installs BFGMiner
+ Installs Apache+PHP
+ Installs miner.php miner monitoring web page
+ Creates Sample Configuration files
+ Creates Miner Scripts
+ Creates Desktop Shortcuts to Miner Scripts

How do I use it?
----------------

To use it, open up a terminal window (Terminal is located under Accessories) and run the following commands:

    wget https://raw.github.com/joshpatten/mining-bootstrap/master/mining-bootstrap
    chmod +x mining-bootstrap
    ./mining-bootstrap

You will be prompted once to enter your password for permission to install the components. If you do not enter your password the installation will fail.

Once you've entered your password the script will begin working. This will take some time as there are a lot of files to download and install.

It's finished, now what?
------------------------

+ Reboot. Seriously, you have to reboot otherwise your drivers and openCL SDK aren't going to load.
+ Modify the mining configuration files to suit your needs. The files are located in your home folder under the Mining/configs folder. (As much as I would have liked to leave my own mining pool credentials in there to soak up some shares from those who didn't quite understand what they were doing, I didn't, for better or worse.)

What Else?
----------
Send me some coin(s)! You can send me whatever you like to to following addresses:

    Bitcoin:   12tok8QAH6ZAY8H7YDHDNE87E1XjDFY7Uj
    Litecoin:  LasEiSR9NTi4vaApDQT7xKQhxCP2CXWxpB
    Dogecoin:  DJjuynL3Fm9XH9EZPajsqJPW3dxPKQEhsN
    Goldcoin:  EArdUoBrRmKbfiiMzMgRbiUkARFnxGCDRa
    Noirbits:  EDNHNGjLKXiBf7HGc3ye3ZY3ZTFabdhRVK
    Worldcoin: WYS8RzwuAhkvKpRg2riYboNFZTUjkrGgqc
    
### AMD APP SDK Manual Download
For those of you who are skeptical about the script downloading from an IP address instead of AMD's website there is a technical reason for this I couldn't overcome in a decent amount of time, and GitHub has a filesize limit of 100MB so I chose to host the site on one of my VPS servers. Rest assured that the MD5 hash of the AMD download server file and the file on my VPS server are identical, but if you still wish to manually download this file here's how:

* Download the 64 bit linux SDK from [AMD's website](http://developer.amd.com/tools-and-sdks/heterogeneous-computing/amd-accelerated-parallel-processing-app-sdk/downloads/)
* Place the file in ~/mine-working (create the folder mine-working in your home folder)

Once you've done this the script will check and verify the MD5 hash of the file against the MD5 hash posted by AMD. If your file download is not corrupt they will match and the file will not be redownloaded, instead using your downloaded copy.
