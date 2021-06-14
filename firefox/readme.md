# Firefox Utils / Edge-like Vertical Tabs (but better!)

Video of the extension in action: [https://i.imgur.com/HaLvkFc.mp4](https://i.imgur.com/HaLvkFc.mp4)

Features: 
  - Edge-like Vertical tab design 
  - Dynamic Indentation (for tree style)

## Updates

12021.06.14: I have added Sideberry support, sideberry is faster, more responsive, and far easier to customize. I may keep going forward with this version. 

## How to use

To use my custom styles you will need to copy the userChrome.css to your firefox profile and then follow the Sideberry or TST sections below.

## Sideberry

Add the sideberry-data-*.json file to your Sideberry addon by using the 'import' section under 'Help'. 

## TreeStyleTabs

Either add the treestyletabs.css to your TST addon preferences or import the treestyletabs-\*.json preferences to your TST addon (_prefered_)

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
