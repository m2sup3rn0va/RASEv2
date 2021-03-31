![](screenshots/RASEv2.png)

> **Owner** : 🧛🏻‍♂️ - Mr. Sup3rN0va | 01-April-2021

> **Tags** : #i0S (📲), #android (📱), #pentesting (👨🏼‍💻), #tools (⚒), #cheatsheet (📜)

---

<h2><b>TABLE OF CONTENTS</b></h2>

- [**RASEv2**](#rasev2)
- [**Features**](#features)
- [**Pre-requisites**](#pre-requisites)
  - [**WINDOWS HOST**](#windows-host)
    - [**Install Python**](#install-python)
    - [**Install Android Studio**](#install-android-studio)
  - [**LINUX HOST**](#linux-host)
- [**Usage**](#usage)
  - [**Usage - Windows**](#usage---windows)
  - [**Usage - Linux**](#usage---linux)
- [**BIG SHOUT**](#big-shout)

---

## **RASEv2**

---

- Stands for **"Root Android Studio Emulators - v2"**
- This is a toolkit to auto-install emulator and then root it

---

☝️ <a href="#">Back to top</a> ☝️

---

## **Features**

- **Intuitive system tray GUI**
- **One-click download, android system images and building emulator**
- **One-click rooting**
- **Auto-Install PowerShell/Bash scripts for post-installation process**
- **Option to re-install burpsuite certificate**
- **Supports rooting from Android-v6 and above**
- **Supports both Windows and Linux(Ubuntu) platforms**
- **Colorfull installation console logs**
- **Powershell/Bash scripts have argument based auto-completion feature**

---

☝️ <a href="#">Back to top</a> ☝️

---

## **Pre-requisites**

---

### **WINDOWS HOST**

---

- Download latest **Android Studio** and **Python** from Internet
- **Windows Terminal** and **GWSL** can be downloaded from Microsoft Store free of cost. It will prompt you to sign-in but you can close the window
- Once all the above are downloaded, open downloaded **'Windows Terminal'** and copy-paste

    `pip3.exe install -U pip rich pyqt5 pyqt5-tools wget --user --no-warn-script-location`

- Please run the above command twice because first run will not download all the pip dependencies
- Once done, run this

    `Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope CurrentUser`

---

☝️ <a href="#">Back to top</a> ☝️

---

#### **Install Python**

---

- Run the python installer and you will see this

  ![](screenshots/windows/Python-Install.png)

- `Uncheck "Install Launcher for all users"` and `Check "Add Python 3.9 to PATH"` and then click `Install Now`
- This will not prompt you for `UAC`

---

☝️ <a href="#">Back to top</a> ☝️

---

#### **Install Android Studio**

---

- Double-click the installer and you will get the `UAC` prompt. Click `Yes`
- Hit Next > Next > Next > Install
- Once the installation is over, click `Next` you will see

  ![](screenshots/Windows/AndroidStudio-1.png)

- Click `Finish`
- After this, it will prompt you again, click `Do Not Import Settings` and `Don't Send` and then Next > Next > Next > Finish
- Then you will see

  ![](screenshots/windows/AndroidStudio-2.png)

- Make sure that you have `HAXM` installed, else emulators will not boot (See the image above). Click `Finish`
- After that you will see this

  ![](screenshots/windows/AndroidStudio-3.png)

- Click on `SDK Manager` and follow the screenshots below

  ![](screenshots/windows/AndroidStudio-4.png)

  ![](screenshots/windows/AndroidStudio-5.png)

  Make sure that none of the softwares of `Android 11.0` are selected from first image and from second image check all highlighted and then click `OK` and again `OK`

- Then you will get this

  ![](screenshots/windows/AndroidStudio-6.png)

  This will remove and install all the packages. Once done, click `Finish`

- Then you will get this

  ![](screenshots/windows/AndroidStudio-3.png)
- Open `SDK Manager` and it should look like below screenshots

  ![](screenshots/windows/AndroidStudio-7.png)

  ![](screenshots/windows/AndroidStudio-8.png)

- Close `Android Studio`
- Also because we will be creating our AVD's from the script, so we need to delete the AVD created at the time of `Android Studio` installation
- Check below screenshot for that

  ![](screenshots/windows/Delete-DefaultAVD.png)

---

☝️ <a href="#">Back to top</a> ☝️

---

### **LINUX HOST**

---

- Download the latest **Android Studio** from Internet
- Download the **RASEv2-Linux.tar.gz**
- Extract it and you will see

  ![](screenshots/linux/rasev2-linux.png)

- **RASEv2** has `install_pre-requisites` script which will auto-install all the dependencies and also set **Android Studio** for installation
- Run it and enjoy the rainbow 🌈:wink:

  ![](screenshots/linux/install_prereq-1.png)

  ![](screenshots/linux/install_prereq-2.png)

  ![](screenshots/linux/install_prereq-3.png)

  ![](screenshots/linux/install_prereq-4.png)

  ![](screenshots/linux/install_prereq-5.png)

- After this as per above screenshot run `$HOME/.android-studio/bin/studio.sh` and the installation steps are similar to how we install **Android Studio** in Windows starting from **bullet point - 5**
- In Linux, default AVD is created in `$HOME/.android/avd`. You can delete it as we did in windows and we will be creating AVD's via script

---

☝️ <a href="#">Back to top</a> ☝️

---

## **Usage**

---

- From here the steps are same for both Linux and Windows
- Run `python RASEv2.py`
- This will pop a notification and a system tray application starts

  ![](screenshots/rase-1.png)

- Right-click the system tray icon and you will have your options

  ![](screenshots/rase-2.png)

- Click on `Build-AVD` and it will prompt you to check `AVD Path` and `Android SDK Path`. If you have done default **Android Studio** installation like mentioned above, then we are good else you need to go to your `RASEv2` and inside `configs\config.json`, you will get default paths which you need to update

  ![](screenshots/rase-3.png)

- Hit `OK` and you will have your `Build-AVD`

  ![](screenshots/rase-4.png)

- Right now it has four android versions support
  - `API23x86_v6.0_GoogleAPIs`
  - `API25x86_v7.1.1_GoogleAPIs`
  - `API27x86_v8.1_GoogleAPIs`
  - `API28x86_v9.0_GoogleAPIs`

- This is because my thought process was more focussed towards pentesting, so this will suffice the requirement but the support can be extended till the latest `Android Versions` though `Not-Tested`
- Paths as I mentioned earlier can be changed from `config.json`. So, we just have to give `AVD Name` and select the version and the tool will auto-download the system image for that version and build the emulator
- This looks like

  ![](screenshots/rase-5.png)

- It will prompt you to close the emulator multiple times so that the script can adjust the look and feel of the emulator
- Once done, you will have a auto-configured emulator ready to get rooted

  ![](screenshots/rase-6.png)

- For rooting the emulator, close the window and click on `Root-AVD` from system tray icon
- This will bring you rooting window

  ![](screenshots/rase-7.png)

- Here the `AVD Name` is a drop-down menu which will automatically gets populated based on the AVDs created. Select which AVD you want to root and click `Root Emulator`

  ![](screenshots/rase-8.png)

  > **NOTE** : Most important point here is to add burpsuite certificate in 'toinstall' folder, else the script will fail

- Once you are done, you can quit the app from system tray

---

☝️ <a href="#">Back to top</a> ☝️

---

### **Usage - Windows**

---

- As per above screenshot, you need to restart the terminal and open `POWERSHELL` and run `RASEv2`
- This will look like

  ![](screenshots/windows/rase-9.png)

- Best part about all the above scripts are that they will be auto-loaded when you start powershell and also they have argument based autocomplete feature which means you don't have to type the command at all because `TABBING` will complete your command, even the emulator names

---

☝️ <a href="#">Back to top</a> ☝️

---

### **Usage - Linux**

---

- It's same for linux as well but I guess it looks much better in linux
- Restart the terminal and run `RASEv2`

  ![](screenshots/linux/rase-9.png)

---

☝️ <a href="#">Back to top</a> ☝️

---

## **BIG SHOUT**

---

- GUI Inspiration : [Wanderson - Youtube](https://www.youtube.com/user/VFXtestingWMP)
- The designs will not be possible without his tutorials 👍

---

☝️ <a href="#">Back to top</a> ☝️

---
