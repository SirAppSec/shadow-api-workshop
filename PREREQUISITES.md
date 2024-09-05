# Introductino 
This guide will help us get our machine ready for the development and exploitation environment.
The core Tools and Methodologies used for assesing web applications and performing researches should be applied.

## Core Tools and Methodologies
Generally the following tools are required for performing White, Gray and Black box assessments.

1. Web traffic inspection: burp suite(Setting web testing guide: https://app-sec.gitbook.io/application-security/v/penetration-testing/web-testing/advanced-web-testing-workspace)
2. Scripting: Python is used to interact and perform web interactions, send/receive requests, changing headers, parameters, meta data
3. Source code analysis: IDE (Visual Code/ NeoVim), used for debugging and analysis Routes and functions
4. Compilers and runtime environment: Node.js runtime(+NPM), java+SDK, 

## Pre-requisites
In this course we will install and deploy several web and api frameworks. 
Our machine should be one of the following: 
1. MacOs with Brew installed
2. Debian based with RPM (apt)
3. Windows with WSL or Kali running on a VM

### Preferred OS
It is preferred to use Kali OS, as it comes pre-built with most of the tools and all of the prerequisites.

Installing Kali:
##
1. Use ISO and install bare metal if using a dedicated computer:
2. If using a Windows host machine: install [virtualbox](https://www.virtualbox.org/wiki/Download_Old_Builds_6_0) or VMware or use Hyper-V and download and load the [KaliOS VM](https://www.kali.org/get-kali/#kali-virtual-machines)
3. Using Windows 11 - WSL 2 we can use a Linux Kernel inside Hyper-V VM(make sure to allow for nested VM) Follow [Kali documentation and commands](https://www.kali.org/docs/wsl/wsl-preparations/#quick-method)

Note: The easiest method is to install Kali in WSL2 is [Kali Linux via the Microsoft Store](https://www.kali.org/docs/wsl/wsl-preparations/#kali-in-microsoft-store)



