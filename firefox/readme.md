# Firefox Utils / Edge-like Vertical Tabs (but better!)

Video of the extension in action: [https://i.imgur.com/HaLvkFc.mp4](https://i.imgur.com/HaLvkFc.mp4)

Features: 
  - Edge-like Vertical tab design 
  - Dynamic Indentation (for tree style)

## Updates

v12021.12.14 :: Sideberry updated to use configs for easier theming, fixed font rendering, and fixed font sizing. 

**12021.12.01 :: Sideberry is the preferred method, and has been since June. I will not be updating the TST extension moving forward. Sideberry is better in nearly every regard to memory usage, responsiveness, speed, and useability.**

12021.06.14 :: I have added Sideberry support, sideberry is faster, more responsive, and far easier to customize. I may keep going forward with this version. 

## How to use

To use my custom styles you will need to copy the userChrome.css to your firefox profile and then follow the Sideberry section below.

## Sideberry

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


## If you use FF without the bookmarks bar

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
