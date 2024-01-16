# Tooling Setup Assignment

## Objectives

* Learn and describe the advantage using modern package managers on Windows and MacOS for tooling install
* Demonstrate the advantages of using version control for documentation distribution
* Learn and discuss the use of Markdown for text based document creation

## Outcome

At the end of this assignment you will have become familiar with industry standard package managers for Windows and MacOS and be able to install standard tooling used in Cloud Native application development. This will be achieved by following a small demo and some small tutorials.

## Overview
x
Complete the required installs in this document via a Package Manager and take a screenshot of the proper output to show a successful install. Place the screenshot into the document as mentioned in the last step.

## Tooling Assignment Part I

We will cover the initial installation of tools we will need for this semester.  If you have already completed this in a prior class, you could take the time to update your software or reach out and help a classmate and take a note that there are a few changes.

## Sample Code

Additional samples and tutorials are available at [https://github.com/illinoistech-itm/jhajek/tree/master/itmo-556](https://github.com/illinoistech-itm/jhajek/tree/master/itmo-556 "webpage for samples")

### Package Managers

Package Managers are an essential tool, originally created for Linux Distributions, apt and yum, at the turn of the century for managing installing software and collecting the proper dependencies. Only in recent years have the major desktop operating systems, Windows and MacOS, created similar tools. You may be more familiar with the term, "APP Store," the concept is the same either way.

Package Managers help by streamlining a few important items:

* Package Managers provide a centralized location for installing applications
  * This location is accessed through a Command Line tool
* Package Managers take care of all dependency installations
  * Any additional pieces or software or libraries are automatically installed for you
* Package Managers allow you to automate and script your installs
  * This makes installing a series of packages portable across systems
* Package Managers handle all PATH issues, updates, and single source to remove an application

### MacOS - Homebrew

Homebrew is the MacOS 3rd party package manager located at: [https://brew.sh/](https://brew.sh/ "brew installer page"). It is available for Intel and M1 based Macs -- the workflow doesn't change.

If you have a Mac - install brew and provide a screenshot of the output of the command: `brew --version`

<img width="563" alt="Screenshot 2024-01-15 at 10 52 19 PM" src="https://github.com/miryalakavya/PrivacyPolicy/assets/45136999/1c358a80-6afd-473a-bcf1-bd8d40263e33">


### Windows 10 21H1+ or 11

The name of the third party Windows Package manager is Chocolatey. The download is located at [Chocolatey.org](https://chocolatey.org/ "Chocolatey.org download page").

From an Administrator PowerShell 5 prompt:

```PowerShell
Set-ExecutionPolicy Bypass -Scope Process -Force; `
[System.Net.ServicePointManager]::SecurityProtocol `
= [System.Net.ServicePointManager]::SecurityProtocol `
-bor 3072; iex ((New-Object `
System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

For Windows 10 or 11, place a screenshot of the version command output for: ```choco --version```.

### Commands to run and install all the software

**NOTE** if you have any of this software already installed, you do not need to reinstall it -- but it wouldn't hurt to upgrade everything so that we are all on the same versions.  Below I will describe what we are installing.

For MacOS using Homebrew:

```bash
brew install --cask powershell ; brew install --cask iterm2 ; brew install git ; brew install --cask visual-studio-code ; brew install --cask atom ; brew install --cask ; brew install virtualbox ; brew install --cask vagrant ; brew install packer
```
![
  
](<version homebrew-1.png>)
For M1 Macs you will run the same as above but without the VirtualBox install:

```bash
brew install --cask powershell ; brew install --cask iterm2 ; brew install git ; brew install --cask visual-studio-code ; brew install --cask atom ; brew install --cask vagrant ; brew install packer
```

* For M1 Macs you will need to make a purchase of a copy of Parallels Pro or Enterprise edition
  * [https://www.parallels.com/products/desktop/pro/](https://www.parallels.com/products/desktop/pro/ "Parallels Pro Edition")
  * The standard and education edition doesn't contain the commandline interface needed for automation
  * [50% off education discount](https://www.parallels.com/landingpage/pd/education/ "website for discount")
* Once Vagrant and Parallels Pro Edition is installed you need to also install the Parallels SDK from the Download Tab in your parallels.com account
  * From the Terminal run the command: `vagrant plugin install vagrant-parallels`
    * This will add the needed plugin to allow you to use Parallels from Vagrant
    * This will also work if you have Parallels Pro Edition on an Intel Mac

For Windows 10 and 11 using Chocolatey:

```PowerShell
choco install powershell-core 
choco install microsoft-windows-terminal git vscode vscode-powershell vagrant packer virtualbox
```

### Installation of a Modern Shell

For Windows we are going to install PowerShell Core, also known as PowerShell 7.x. Windows includes PowerShell 5 (the light blue icon), which has ceased development and doesn't have support for modern font display.  PowerShell 7 is opensource and cross-platform available.  Working on Windows, PowerShell 7 is a must.

Open PowerShell 7 and issue the command: `ssh -V` and take a screenshot of the PowerShell version output as well as the SSH version output.

For MacOS, newer versions use the Z shell.  This is due to Apple not using GPLv3+ software, which newer versions of BASH are licensed under.  This should be just fine and not require a new shell install.  If you want to experiment you can also install PowerShell 7 via Brew but it is not required.

Open a terminal and type the commands: `zsh --version` and `ssh -V` and take a screenshot of the output

<img width="576" alt="Screenshot 2024-01-15 at 8 59 30 AM" src="https://github.com/miryalakavya/PrivacyPolicy/assets/45136999/5358b426-baa8-4834-bd30-1d0e667724af">

### Installation of a Modern Terminal

A Terminal is a way to run and manage multiple shell together, not unlike a web-browser, in a single managed window.  You will spend much time on in a shell during your career, the Terminal is a huge helper.

On Windows, Microsoft provides a [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab "Install Windows Terminal from Microsoft Store")

Open the Windows Terminal and select from the drop down arrow, the ABOUT tab, and take a screenshot of the version output

On MacOS, there is a terminal called [iterm2](https://iterm2.com/ "MacOS shell terminal")

Open the iterm2 Terminal and from the File > About section take a screenshot of the version output

<img width="613" alt="Iterm2" src="https://github.com/miryalakavya/PrivacyPolicy/assets/45136999/3525af0c-5b8e-490f-b7da-6167fb209538">

### Install IDE editor with native version control support

We will be installing an text editor or and IDE for all of our coding and configuration.  The key is one with native version control tooling integrated.  There are many and all can be installed via your OSes package manager, here are a list:

* [VSCode from Microsoft](https://code.visualstudio.com/ "VSCode install")
  * Cross platform and has direct shell integration
* [Sublime Text](http://www.sublimetext.com/ "Submlime Text installer site")
  * Built for a MacOS native experience, A sophisticated text editor for code, markup and prose.  Available for all platforms.
* [Adobe Brackets](http://brackets.io/ "Adobe Brackets Install")
  * Cross Platform development tool from Adobe

Take a screenshot from the ABOUT tab in your IDE to show the installed version

<img width="276" alt="Visual Studio" src="https://github.com/miryalakavya/PrivacyPolicy/assets/45136999/d16b01c5-de43-4e50-aee7-d430f3c68f7b">

### Install Git Client for Version Control

Version Control is vital to modern software development and we will be using our Package Manger to install the Git Client for our respective operating systems. **Note**, this is different from the GitHub Desktop tool, which we will not be using this semester.

Take a screenshot of the output of the command: ```git --version```

<img width="560" alt="git version" src="https://github.com/miryalakavya/PrivacyPolicy/assets/45136999/3556563c-dce2-4e8e-b6d5-f87354a801ad">

#### Configure Git Client

You will need to configure Git if you already haven't done so.  From a shell run these two commands:

```bash
git config --global user.name "<Your Name>"
git config --global user.email "<youremail@example.com>"
```

My information would look like this:

```bash
git config --global user.name "Jeremy Hajek"
git config --global user.email "hajek@iit.edu"
```

### Install VirtualBox on Intel Macs or Windows

If you do not already have VirtualBox 7.x installed, use your package manager to install VirtualBox.  VirtualBox will be our virtualization platform we are using this semester. It is a robust opensource product and can be used to create and host machines on our local systems. It has integration with automation tools such as Packer and Vagrant from HashiCorp.

Take a screenshot of the VirtualBox > Help > About VirtualBox output or from the Terminal: `vboxmanage --version` (Windows or Intel MacOS)

### Install Virtualization Solutions for M1/M2 Macs

There are 2 options:

* Buying a Pro-license from Parallels (link for %50 student discount)
  * [Pro License from Parallels](https://www.parallels.com/landingpage/pd/education/?cjevent=8130c1204d8811ee81ff00890a82b839&utm_source=CJ&utm_medium=AFFILIATES "Pro License from Paralles")
* [UTM](https://mac.getutm.app/ "webpage for apple sillicon framework")
  * Free download or purchase in the Mac App store

Whichever solution you choose - take a screenshot showing the installed version.

**Note:** that you can use Parallels on an Intel MacOS as well -- you would need to make sure you have the Pro edition installed and the SDK installed as well.

<img width="372" alt="Screenshot 2024-01-15 at 10 01 39 PM" src="https://github.com/miryalakavya/PrivacyPolicy/assets/45136999/3366409b-3a04-4408-9c63-c7f63bf12f69">


### Install Vagrant

Vagrant is a tool from [HashiCorp](https://hashicorp.com "HashiCorp website").  This tool is used to abstract away the VirtualBox interface and provide direct commandline access, increasing ease of use.  *Vagrant provides easy to configure, reproducible, and portable work environments built on top of industry-standard technology and controlled by a single consistent workflow to help maximize the productivity and flexibility of you and your team.*

Using your package manager, install the latest version of [Vagrant](https://vagrantup.com "Vagrant download site").  If you have a version 2.2.x you will be ok.  Note, if using Linux, do not use the built in package manager as these versions of Vagrant and Packer are too old and unmaintained.  

Take a screenshot of the output of the command: ```vagrant --version```

<img width="567" alt="vagrant" src="https://github.com/miryalakavya/PrivacyPolicy/assets/45136999/84289b50-0884-47ee-91cf-3fa04d883679">

### Install Packer.io

Packer is another automation tool from HashiCorp.  Whereas Vagrant was for running virtual machines, Packer's job is to build virtual machine images from a template language.  This tool allows fast infrastructure deployment, multi-provider portability, improved stability, and greater testability.

Using a package manager, install the latest version of [Packer](https://packer.io "Packer install site").  If you have a version > 1.6.x you will be ok. Note, if on Linux, do not use the built in package manager as these versions of Vagrant and Packer are too old and unmaintained.  

Take a screenshot of the output of the command: ```packer --version```

### Oh-My-Git Tutorial

<img width="568" alt="packer" src="https://github.com/miryalakavya/PrivacyPolicy/assets/45136999/f6d19bf4-b2ed-47b4-977e-a3402caad743">

Download the proper [Oh My Git! tutorial](https://ohmygit.org/ "webpage for oh my git") the program runs as a self contained executable on your system (Windows Mac or Linux).

Complete the tutorial and take screenshots of the completed sections (may need to take a few shots as the there are many sections).

This Git tutorial is a good refresher for those who need it and a great introduction for those new to Version Control and want to learn it. You can leave the last section out, **Sandbox**, it is an open area for you to experiment in and no real way to "complete it."

<img width="1440" alt="Screenshot 2024-01-15 at 10 00 14 PM" src="https://github.com/miryalakavya/PrivacyPolicy/assets/45136999/8d84b391-068e-4860-bb3f-d3933b06cbd3">

<img width="1440" alt="Screenshot 2024-01-15 at 10 00 23 PM" src="https://github.com/miryalakavya/PrivacyPolicy/assets/45136999/f1afc426-04a3-4005-8765-f98f56c652a8">

<img width="1440" alt="Screenshot 2024-01-15 at 10 00 29 PM" src="https://github.com/miryalakavya/PrivacyPolicy/assets/45136999/418940d0-c1de-4a06-88c2-ec8aa497fc1e">


### Adding Screenshots

Using the Readme.md template file provided under the Assignment Tab > Week-01 in Blackboard, add your screenshots to the `Readme.md` and commit and push the document to a folder named: `itmo-556` > `tooling-assignment`

Use the [Markdown cheatsheet reference](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet "Markdown cheatsheet").

### Final deliverable to Blackboard

Submit to Blackboard the URL to your GitHub private repo, so I can clone and see all these elements. You will submit URL's to the work in the Private GitHub repo to Blackboard, but the work will stay in GitHub.
