MacOS-Tips
==========

Change Default Settings for The Guest User Account
--------------------------------------------------

### Features (so far)

* Set mouse tracking speed personal preference
* Disable playing feedback when volume is changed
* Install Safari extensions (e.g., AdBlock, ClickToFlash, etc.)
* Disable Safari stopping plug–ins to save power
* Disable Safari auto filling user names, passwords and credit cards
* Enable Safari asking websites not to track me

### How–to

* Enable Guest User in System Preferences > Users & Groups
* Open Terminal

```bash
sudo bash
cd /System/Library/User\ Template
cp -a English.lproj English.lproj.orig
```

* Login as the Guest User and do whatever changes you would like to do
* Switch back to the original user, *without* logging off the Guest User

```bash
rm -r English.lproj/Library/*
cp -a /Users/Guest/Library/* English.lproj/Library/
rm -r English.lproj/Library/Keychains/*
```

* Switch back to the Guest User
* Logoff the Guest User
* Done ;-)

### If something goes wrong:

```bash
sudo bash
cd /System/Library/User\ Template
rm -r English.lproj
mv English.lproj.orig English.lproj
```
