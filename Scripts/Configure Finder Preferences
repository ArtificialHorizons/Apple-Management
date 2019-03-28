#!/bin/bash

#Finds current username and defines a variable
currentuser=`stat -f "%Su" /dev/console`

#Substituting as user stored in variable to modify plist
#su "$currentuser" -c "<command to run>"

#Add Movies, Music, Pictures, <username>, to Finder Favorites sidebar.

su "$currentuser" -c "sfltool add-item com.apple.LSSharedFileList.FavoriteItems file:///Users/$currentuser && sleep 2"

su "$currentuser" -c "sfltool add-item com.apple.LSSharedFileList.FavoriteItems file:///Users/$currentuser/Movies && sleep 2"

su "$currentuser" -c "sfltool add-item com.apple.LSSharedFileList.FavoriteItems file:///Users/$currentuser/Music && sleep 2"

su "$currentuser" -c "sfltool add-item com.apple.LSSharedFileList.FavoriteItems file:///Users/$currentuser/Pictures && sleep 2"

su "$currentuser" -c "touch /Users/$currentuser/.sidebarshortcuts"

#Turns on show Hard Disks, External disks, CDs, DVDs, and iPads, and Connected Servers

su "$currentuser" -c "defaults write com.apple.finder ShowExternalHardDrivesOnDesktop -bool true;"

su "$currentuser" -c "defaults write com.apple.finder ShowHardDrivesOnDesktop -bool true;"

su "$currentuser" -c "defaults write com.apple.finder ShowMountedServersOnDesktop -bool true;"

su "$currentuser" -c "defaults write com.apple.finder ShowRemovableMediaOnDesktop -bool true;"

#Shows Status Bar

su "$currentuser" -c "defaults write com.apple.finder ShowStatusBar -bool true;"

#Shows Tab View

su "$currentuser" -c "defaults write com.apple.finder ShowTabView -bool true;"

#Shows Path Bar

su "$currentuser" -c "defaults write com.apple.finder ShowPathbar -bool true;"

#Changes Finder to List View
#Four-letter codes for the other view modes: 'icnv', 'clmv', 'Flwv'

su "$currentuser" -c "defaults write com.apple.finder FXPreferredViewStyle -string 'Nlsv'"

#New Finder windows now opens in /Users/<username>

su "$currentuser" -c "defaults write com.apple.finder NewWindowTarget -string 'PfHm'"

#Turns off re-open programs/windows after restart/login/shutdown

su "$currentuser" -c "defaults write com.apple.loginwindow.plist TALLogoutSavesState -bool false"

#Restarts cfprefsd and Finder

killAll cfprefsd
killAll Finder

echo "Finder Preferences set"

exit 0\
