# **🍎🌈💠 New macOS (Intel) Setup**

### This guide is based on my own experience, but also draws on other guides. It is primarily oriented towards those doing code-related stuff and applicable to those doing Web-based development.

## Steo 0: Change the computer name ❓❓❓

```bash
# To change the computer name on a Mac via the terminal (the command line), use the scutil command. There are three different names you may want to update for consistency

sudo scutil --set ComputerName "New-Computer-Name"
sudo scutil --set LocalHostName "New-Local-Name"
sudo scutil --set HostName "New-Host-Name"

# Important Follow-up Commands
dscacheutil -flushcache
sudo reboot

# Verification
scutil --get ComputerName
scutil --get LocalHostName
scutil --get HostName

```

## Step 1: Run software update ✅✅✅

Make sure everything is up to date. Essential Terminal Commands for macOS 15+ Updates:

- List all available updates:

```bash
softwareupdate -l
```

- LInstall all available updates:

```bash
sudo softwareupdate -i -a
```

- Install only recommended updates:

```bash
sudo softwareupdate -i -r
```

- Install updates and restart automatically:

```bash
sudo softwareupdate -i -a -R
```

## Step 2. Install Xcode and/or "Command Line Tools" 🟠🟠🟠

> NOTE: homebrew now automatically installs command line tools, so you can skip this step.

"Command Line Tools" can be downloaded separate from Xcode at
https://developer.apple.com/downloads/ — It is way smaller than installing the
whole Xcode but might not work for all cases tho — or you can run `xcode-select --install`

## Step 3. Install Homebrew 🍺

http://brew.sh/

This is the first thing I normally do. As I've said before, [haters gonna hate](https://applehelpwriter.com/2018/03/21/how-homebrew-invites-users-to-get-pwned/), but this is the quickest, easiest way to get a commonly-referenced package manager on the Mac.

To install **Homebrew**, run this command:

```bash
# install homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

To make sure it's all working correctly, execute:

```bash
brew doctor
```

Finally, just to make sure everything's up-to-date:

```bash
brew update
```

### Step 4. Install softwares ❇️❇️❇️

```sh
# essential
brew install git
brew install wget
brew install mise
brew install nano
brew install jandedobbeleer/oh-my-posh/oh-my-posh
brew install fastfetch
brew install lla

# dev
brew install --cask font-maple-mono-nf
brew install --cask ghostty
brew install --cask visual-studio-code
brew install --cask sublime-text
brew install --cask xcodes

# media
brew install --cask iina
brew install --cask vlc

# browsers
brew install --cask librewolf
brew install --cask google-chrome

# others
brew install --cask puremac

```

## Step 5: Mole Cleaner Tool ☢️☢️☢️

```bash
# Optional args: -s latest for main branch code, -s 1.17.0 for specific version
curl -fsSL https://raw.githubusercontent.com/tw93/mole/main/install.sh | bash

mo                           # Interactive menu
mo clean                     # Deep cleanup + already-uninstalled app leftovers
mo uninstall                 # Remove installed apps + their leftovers
mo optimize                  # Refresh caches & services
mo analyze                   # Visual disk explorer
mo status                    # Live system health dashboard
mo purge                     # Clean project build artifacts
mo installer                 # Find and remove installer files
mo update                    # Update Mole
mo --help                    # Show help
mo --version                 # Show installed version
```

## Step 6: Terminal profile via oh-my-posh (~/.zshrc) 🎉🎉🎉

It is also included in this repo

```bash
#------- Customized oh-my-posh themes
#eval "$(oh-my-posh init zsh --config ~/.omp/atomic.omp.json)"
#eval "$(oh-my-posh init zsh --config ~/.omp/atomicBit.omp.json)"
#eval "$(oh-my-posh init zsh --config ~/.omp/chips.omp.json)"
#eval "$(oh-my-posh init zsh --config ~/.omp/cloud-native-azure.omp.json)"
#eval "$(oh-my-posh init zsh --config ~/.omp/huvix.omp.json)"
#eval "$(oh-my-posh init zsh --config ~/.omp/negligible.omp.json)"
#eval "$(oh-my-posh init zsh --config ~/.omp/ys.omp.json)"
```

## Step 7: Others Miscellaneous

```bash
# Let's just brute-force creating the .nanorc and include all syntax highlighters:
echo include "/usr/local/share/nano/\*.nanorc" >> ~/.nanorc
```
