# Firefox Utils / Edge-like Vertcal Tabs (but better!)

Video of the extension in action: [https://i.imgur.com/HaLvkFc.mp4](https://i.imgur.com/HaLvkFc.mp4)

To use my custom TST addons you will need to copy the userChrome.css to your firefox profile, add the treestyletabs.css to your TST addon preferences or just add the treestyletabs.json preferences to your TST addon.

## If you use FF without the bookmarks bar

Then the sidebar switcher will be missing, you need to add this to your userChrome.css

```
#sidebar-box {
  --menubar-height: -40px !important;
}
```

## Benefits:

  - Edge-like Vertical tab design 
  - Dynamic Indentation (for tree style)

## Other Considerations

If you dislike some of my my other changes to FF (added vivaldi's folder icon, removed the superbox, cleaned up the borders, removed the titlebar) then remove everything below CUSTOM MODIFICATIONS in userChrome.css
