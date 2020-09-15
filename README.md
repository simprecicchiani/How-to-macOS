<img align="right" src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/22/MacOS_logo_%282017%29.svg/1024px-MacOS_logo_%282017%29.svg.png" alt="T460s macOS" width="100">

# How to macOS

Should you find an error or improve anything please consider opening an issue or pull request.  
If you find my work useful, please consider donating via PayPal.
It would mean a lot to me.  
[![donate](https://img.shields.io/badge/-buy%20me%20a%20coffee-orange)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=Y5BE5HYACDERG&source=url)

A collection of useful command that are rarely used (maybe once a year or for fresh OS installations) and so, hardly remembered.

This is not a beginners guide. These commands want to help medium/high experienced users that need more control over basic system settings.

⌘+F anything you need!


### Reset Launchpad Layout
```
defaults write com.apple.dock ResetLaunchPad -bool true; killall Dock
```
### Delete all .DS_Store files on your computer
If you want to set defaul view in fider, this will be applied to new visited directories only. By deleting all .DS_Store files, every directory history will be deleted as well.
```
sudo find / -name .DS_Store -delete; killall Finder
```
### Mount Root Partition with Read and Write permissions
```
sudo mount -uw /
```
### Install Homebrew package manager
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```
### Install updated Bash and set as default shell for Terminal ![Homebrew](/assets/brew.png)
```
brew update && brew install bash && sudo chsh -s /usr/local/bin/bash $(whoami)
```
### Speed-up dock's animation
```
defaults write com.apple.dock autohide-delay -float 0; defaults write com.apple.dock autohide-time-modifier -float 0.5; killall Dock
```
### Jump through page sections by clicking on the scrollbar
```
defaults write -globalDomain AppleScrollerPagingBehavior -bool true
```
### Show all filename extensions
```
defaults write NSGlobalDomain AppleShowAllExtensions -bool true
```
### Hide warning before changing a file's extension
```
defaults write com.apple.finder FXEnableExtensionChangeWarning -bool false
```
### Allow quitting Finder via ⌘ + Q
Enable closing finder unless is the only app running. Once closed the desktop icons will not be visible
```
defaults write com.apple.finder QuitMenuItem -bool true
```
### Delete Time Machine snapshots
List all snapshots
```
tmutil listlocalsnapshots /
```
delete snapshot 
```
sudo tmutil deletelocalsnapshots "insert-date-here"
```
