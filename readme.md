# Firefox Sidebar / Edge-like Vertical Tabs (but better!)

**Note:** This repo was originally a subdirectory of [drannex42/linux-utils](https://github.com/drannex42//linux-utils/), but has now become a standalone repo for my Firefox Sidebar CSS and Utilities. The original linux-utils files can be found [here](https://github.com/drannex42/utils). 

## Example
Video of the extension in action: [https://i.imgur.com/HaLvkFc.mp4](https://i.imgur.com/HaLvkFc.mp4)

## Features: 
  - Edge-like vertical tab design 
  - Dynamic Indentation (for tree style tabs)
  - Custom theme configuration using Sideberry 
  - Support for tab groups 
  - Support for Tab Containers with visual identification
  - Pinned tabs (right click to close) 

## Updates

Release notes have migrated to [here](https://github.com/drannex42/FirefoxSidebar/releases). You can find prior release notes before v12021.12.22 [here](https://github.com/drannex42/FirefoxSidebar/releases/tag/v12021.12.22). 

# How to use

To use my custom styles you will need to copy the userChrome.css to your firefox profile and then follow the Sideberry section below. Both are outlined below in how to do so. 

## 1. Sideberry

Add the sideberry-data-*.json file to your Sideberry addon by using the 'import' section under 'Help'. 

The default is for light themes, if you have a particular color scheme in mind navigate to Sideberry Settings > Style Editor (found at the end of the settings sidebar). 

To change the color: 

**--tabs-font** :: Changes the default font (uses system font by default) to change the font size. 
- I recommend changing it via Sideberry Settings > Appearance > Font Size
- default: 1rem -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";

**--tabs-fg** :: Changes the tabs text color 
- default: #000

**--tabs-bg-hover** :: Changes the hover background color for tabs 
- default: #dedddaff

**--tabs-activated-bg** :: This is the active tab background color 
- default: #fff

**--tabs-activated-shadow** :: Changes the active tabs shadow color 
- default: rgba(0,0,0,0.15);

## 2. userChrome.css 

Follow the instructions for adding a userChrome.css file to your Firefox Profile.

- Navigate to `[about:profiles]` in your address bar
- Click on the 'open root folder` button for your current profile 
- Create a 'chrome' folder (all lowercase)
- Add the userChrome.css file to that folder
- In firefox navigate to `[about:config]` in your address bar
- change the characteristic `toolkit.legacyUserProfileCustomizations.stylesheets` to `true` 
- Restart Firefox
- Visit [userchrome.org](https://www.userchrome.org/how-create-userchrome-css.html) if you are confused or have any questions. 

Values: 

 **--sidebar-bg-color**
 - Change this if you have a different theme than the default light one to match the rest of your sideberry theme colors 
 - default: #fafafa;


### If you use FF without the bookmarks bar

Then the sidebar switcher will be missing, you need to add this to your userChrome.css

```
#sidebar-box {
  --menubar-height: -40px !important;
}
```

Warning: TST support may be ending as I continue to test the Sideberry addon. 

## Other Considerations

If you dislike some of my my other changes to FF (added vivaldi's folder icon, removed the superbox, cleaned up the borders, removed the titlebar) then remove everything below CUSTOM MODIFICATIONS in userChrome.css


## TreeStyleTabs (Legacy)

Either add the treestyletabs.css to your TST addon preferences or import the treestyletabs-\*.json preferences to your TST addon (_prefered_)
