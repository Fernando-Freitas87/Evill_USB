# EvilUSB

These are some EvilUSB Sticks...

![EvilUSB Sticks](http://i.imgur.com/wDYmoYJ.jpg)


## What is EvilUSB?

EvilUSB is a pentesting USB Device that is recognized by the target Computer as a regular USB Flash Drive. This innocent-looking Social Engineering device can be placed at anyone's desk/mailbox, and as soon as they get hold of it and plug it into their Computer, just like any average user, they would attempt to browse the USB Flash Drive and take look at the contents of the Drive. From there on, they're just a click away from getting infected.

## How does it work?

![EvilUSB Drive](https://i.gyazo.com/b9ebdf1cd99fa32d31148ce185f34760.png)

Each EvilUSB comes with the following files:
```
EvilUSB (D:)
|-- % [H]
|    |-- evil.bat || .exe [H]
+-- New folder.lnk
```
Notes:
* `%: Invisible (U+180E) Space Charcater`
* `[H]: Hidden`

With the % Folder being [H]idden, it will not be visible in Windows explorer by default. That means, the only file visible to the user will be the Shortcut `New folder.lnk`, which is linked to the malicious file, `/%/evil.bat || .exe`. `New folder.lnk` will have gotten the Icon of a Folder, hence the name of the Shortcut file. That makes the "New folder" look identical to an actual, real folder. So, as soon as the target attempts to open the "folder", he will have basically run the Shortcut file, which is linked to the malicious file, `evil.exe`/`evil.bat`, and from there on he's infected.

### Disguising the Attack

As soon as the user opens the "folder", he will notice that no folder has been opened. This is a factor that would increase the suspiciousness of EvilUSB. For that reason, in the very first lines of the malicious evil.bat File, it would be a good idea to include the following lines:
```
@echo off
mkdir ../New folder&cd ../New folder&start .
```

The purpose of the above lines is to make the Attack less suspicious. For that matter, below is the explanation of the above batch code:
* `&`: Command seperator that allows next command to be executed regardless of the previous command-execution's success/failure
* `@echo off`: Disable output
* `mkdir ../New folder`: Create new folder in root directory of the Drive (D:/) called "New folder"
* `cd ../New folder`: Change directory to the newly created folder
* `start .`: Open the newly created folder

## Can this be achieved with the use of any USB Flash Drive?

Technically, yes.

## Should you use your pre-owned USB Flash Drives for this Attack?

Definitely not. Considering you'll be sacrificing your USB Flash Drive, it is not a good idea to waste tens of dollars per attack. If you don't want to risk losing your USB Stick and would attempt to get the USB Flash Drive back from your target Victim, you are putting your anonymity in risk and the chances of you getting caught are just as high.

## So, what should I do if I want to perform this attack "for educational purposes"?

Since this Social Engineering attack does not require a USB Flash Drive with over 64MB Capacity Storage, it is recommended that you order a couple of some cheap 64MB USB Flash Drives.

## Demonstration

[![](https://img.youtube.com/vi/-2OkljFzW3s/0.jpg)](https://www.youtube.com/watch?v=-2OkljFzW3s)

## Credits

EvilUSB was created by [@0xCoto](https://github.com/0xCoto).

[![Analytics](https://ga-beacon.appspot.com/UA-85426772-5/EvilUSB/?pixel)](https://github.com/igrigorik/ga-beacon)
