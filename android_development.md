# Android Development Utils

## Grade Sync failed

This was a nightmare to figure out, especially because all the error message said was ``Grade sync failed: reason unknown``, so whoever got to write that error message, I am coming for you. 

To fix this was a lot of trial-and-error, (and uninstalling and reinstalling Android Studio and removing my .gradle folder in my home directory) and reading and trying a lot of responses on basically all stackoverflow questions answer with "Do this thing that worked eight years ago, or this that worked five years ago, three years ago, and two years ago" and none of those work for now. 

**Here is what works in 12021:** Go to ```Tools => SDK Manager => SDK Tools``` Then check the `Google Play Licensing Library` item, and click apply (this installs it - all 73kb to make up for an hour of headaches....). Click on the 'elephant icon' in the top right of Android Studio and your gradle build should be working properly. 
