# Introductino 
This guide will help us get our machine ready for the development and exploitation environment.
The core Tools and Methodologies used for assesing web applications and performing researches should be applied.

## Core Tools and Methodologies
Generally the following tools are required for performing White, Gray and Black box assessments.

1. Web traffic inspection: burp suite(Setting web testing guide: https://app-sec.gitbook.io/application-security/v/penetration-testing/web-testing/advanced-web-testing-workspace)
2. Scripting: Python is used to interact and perform web interactions, send/receive requests, changing headers, parameters, meta data
3. Source code analysis: IDE (Visual Code/ NeoVim), used for debugging and analysis Routes and functions
4. Compilers and runtime environment: Node.js runtime(+NPM), Java+JDK, 

## Pre-requisites
In this course we will install and deploy several web and api frameworks. 
Our machine should be one of the following: 
1. MacOs with Brew installed
2. Debian based with RPM (apt)
3. Windows with WSL or Kali running on a VM

You'd need at least 60GB of storage, at least 16G RAM, and an internet connection

### Preferred OS - Kali
It is preferred to use Kali OS, as it comes pre-built with most of the tools and all of the prerequisites.

Installing Kali:
##
1. Use ISO and install bare metal if using a dedicated computer:
2. If using a Windows host machine: install [virtualbox](https://www.virtualbox.org/wiki/Download_Old_Builds_6_0) or VMware or use Hyper-V and download and load the [KaliOS VM](https://www.kali.org/get-kali/#kali-virtual-machines)
3. Using Windows 11 - WSL 2 we can use a Linux Kernel inside Hyper-V VM(make sure to allow for nested VM) Follow [Kali documentation and commands](https://www.kali.org/docs/wsl/wsl-preparations/#quick-method)

Note: The easiest method is to install Kali in WSL2 is [Kali Linux via the Microsoft Store](https://www.kali.org/docs/wsl/wsl-preparations/#kali-in-microsoft-store)
```bash
#commands to get WSL2 Kali up to speed:

# https://www.kali.org/docs/troubleshooting/common-minimum-setup/
sudo apt update 
sudo apt full-upgrade -y
sudo apt install -y kali-win-kex

# pick your kali installation: kali-linux-default should suffice
# https://www.kali.org/docs/installation/installation-sizes/

sudo apt install -y kali-linux-large
```

to start kali Win-Kex:
```bash
# From windows
wsl -d kali-linux kex --win -s

# Inside Kali WSL:
kex --win -s
```


## Additional Tools
We would require the following:
1. package manager
2. node + npm (opt for nvm to control versions)
#### MacOS
If using Mac ensure [homebrew](https://brew.sh/) is installed:
```bash
# Install brew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Check version to verify installation
npm --version
node --version
which node
# Install NVM
brew install nvm

nvm install 16
nvm use 16
```


#### Debian
kali includes most of the tools, ensure tools are installed if you're not using kali or missing any

```bash
# Check version to verify installation
npm --version
node --version
which node

# Install NVM
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
nvm install 16
nvm use 16
```

# Installation Example
```bash
# Install Nerd Font (Download from https://www.nerdfonts.com/font-downloads)
sudo cp ~/Downloads/HackNerdFont-Bold.ttf /etc/fonts/hackNerd.ttf

# Install and login gh CLI
sudo apt install gh
gh auth login

# Install NeoVim IDE
sudo apt install neovim

# Install AstroNvim configuration
git clone --depth 1 https://github.com/AstroNvim/template ~/.config/nvim
rm -rf ~/.config/nvim/.git

# Install additional AstronVim Dependencies
sudo apt-get install ripgrep
npm install tree-sitter-cli

# Install LazyGit
LAZYGIT_VERSION=$(curl -s "https://api.github.com/repos/jesseduffield/lazygit/releases/latest" | grep -Po '"tag_name": "v\K[^"]*')
curl -Lo lazygit.tar.gz "https://github.com/jesseduffield/lazygit/releases/latest/download/lazygit_${LAZYGIT_VERSION}_Linux_x86_64.tar.gz"
sudo curl -Lo lazygit.tar.gz "https://github.com/jesseduffield/lazygit/releases/latest/download/lazygit_${LAZYGIT_VERSION}_Linux_x86_64.tar.gz"
sudo tar xf lazygit.tar.gz lazygit
sudo install lazygit /usr/local/bin
lazygit --version

# Install Visual Studio Code
# Download: https://code.visualstudio.com/docs/setup/linux
cd Downloads/
sudo apt install ./code_1.93.0-1725459079_amd64.deb 

# Optionally install zsh theme
# https://github.com/romkatv/powerlevel10k

# Install zoxide to replace cd with a smarter option
sudo apt-install zoxide
sudo apt install fzf
echo "source <(fzf --zsh)" >> ~/.zshrc
echo 'eval "$(zoxide init zsh --cmd cd)"' >> ~/.zshrc


# verify javasdk
java --version

# Install FF extensions
# https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/
# https://addons.mozilla.org/en-US/firefox/addon/vimium-ff/
# https://addons.mozilla.org/en-US/firefox/addon/sponsorblock/
# https://addons.mozilla.org/en-US/firefox/addon/foxyproxy-standard/
```
