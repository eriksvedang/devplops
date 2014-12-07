### The good programs
* Adium
* Alfred
* AppViz 2
* Colloquy
* Dropbox
* Dropfix
* Flux
* GitHub
* iOrdning
* LightTable
* Pixelmator
* Postgres ("for Mac", standalone)
* Reason
* Steam
* Sublime Text
* The Unarchiver
* Transmission
* Type Tool
* Unity
* Versions
* VLC



### Set path for programs started from GUI

Create file in ~/Library/LaunchAgents/my.startup.plist

------------------------------------------
#!/bin/bash

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
  <key>Label</key>
  <string>my.startup</string>
  <key>ProgramArguments</key>
  <array>
    <string>sh</string>
    <string>-c</string>
    <string>launchctl setenv PATH /Users/erik/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/bin:/Applications/ghc-7.8.3.app/Contents/bin/:/Users/erik/.cabal/bin/</string>
  </array>
  <key>RunAtLoad</key>
  <true/>
</dict>
</plist>

------------------------------------------

###