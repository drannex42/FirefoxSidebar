# Firefox Sidebar / Edge-like Vertical Tabs (but better!)

**Note:** This repo was originally a subdirectory of [drannex42/linux-utils](https://github.com/drannex42//linux-utils/), but has now become a standalone repo for my Firefox Sidebar CSS and Utilities. The original linux-utils files can be found [here](https://github.com/drannex42/utils). 

## Example
Video of the extension in action: [https://i.imgur.com/HaLvkFc.mp4](https://i.imgur.com/HaLvkFc.mp4)

## Features: 
  - Edge-like vertical tab design 
  - Tree style tab layout support (works with Sideberry & TST (legacy) version) 
  - Dynamic Indentation
  - Automatic theme configuration for light and dark themes 
  - Custom theme configuration using Sideberry 
  - Support for tab groups 
  - Support for Tab Containers with visual identification
  - Pinned tabs (right click to close) 
  - Built in CSS Extension Management

## Updates

Release notes have migrated to [here](https://github.com/drannex42/FirefoxSidebar/releases). You can find prior release notes before v12021.12.22 [here](https://github.com/drannex42/FirefoxSidebar/releases/tag/v12021.12.22). 

# How to use

To use FirefoxSidebar you will need to clone this repo into your firefox profile as the `chrome` folder and then follow the Sideberry section below. Both are outlined below in how to do so. 

## 1. userChrome.css 

Follow the instructions for adding this repository to your Firefox Profile.

1. Navigate to `about:profiles` in your address bar
2. Click on the 'open root folder` button for your current profile 
3. Open this folder in your terminal
4. Clone this repo with the following command: `git clone https://github.com/drannex42/FirefoxSidebar.git "chrome"`
5. InFfirefox navigate to `about:config` in your address bar
6. change the characteristic `toolkit.legacyUserProfileCustomizations.stylesheets` to `true` 
7. Restart Firefox

You could skip the clone step entirely if you manually add the FirefoxSidebar files to the "chrome" folder in your Firefox Profile (you will need to make a `chrome` folder if it doesn't exist!). 

Visit [userchrome.org](https://www.userchrome.org/how-create-userchrome-css.html) if you are confused or have any questions. 

## 2. Sideberry

Load the `sideberry-data.json` file into your Sideberry addon by using the 'import' section under 'Help'. 

If you dislike any of the theme presets for dark or light themes, or you have a particular color scheme in mind then navigate to Sideberry Settings > Style Editor (found at the end of the settings sidebar). The preference is to replace the values in the right panel, not in the theme editor to the left - this way you can easily update to newer versions in the future.  

### Extensions

All extensions can be found in `/extensions`. 

In version 2022.02.23 we broke up the components into extensions using css imports. This makes adding and removing features incredibly easy. 

**The following extensions are added:**

- [Window Controls / Client Side Decorations (CSD)](/extensions/window_controls.css) 
  - This adds the window controls to be inline with your address bar.
- [Superbox Removal](/extensions/superbox_removal.css) 
  - This removes the superbox and fixes the address bar padding.
- [Bookmark Arrows](/extensions/bookmark_arrow.css) 
  - This adds a nice little arrow next to your bookmark folders.

## User Settings

Please backup the `prefs.css` and the `custom.css` files before updating to a new versionof FirefoxSidebar. There may be new additions to these files, so you will need to re-add your preferencess to the file accordingly. These files should be updated *far less* than the other files, but just to make sure please save them. 

### Preferences

There are a number of preferences you can enable or disable in the `prefs.css` file. There are examples and descriptions of the different preferences within that file.

### Custom Extensions

For ease of use I suggest using the `custom.css` file to for your personal tweaks. 

### If you use FF without the bookmarks bar

Then the sidebar switcher will be missing, you need to add this to your userChrome.css

```
#sidebar-box {
  --menubar-height: -42px !important;
}
```

## Other Considerations

If you dislike some of my my other changes to FF (added vivaldi's folder icon, removed the superbox, cleaned up the borders, removed the titlebar) then remove everything below CUSTOM MODIFICATIONS in userChrome.css


## TreeStyleTabs (Legacy)

Either add the treestyletabs.css to your TST addon preferences or import the treestyletabs-\*.json preferences to your TST addon (_prefered_)
