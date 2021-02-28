# userChrome.css

This is a collection of my UserChrome scripts, may be seperated, more than likely not. 

```
#main-window[tabsintitlebar="true"]:not([extradragspace="true"]) #TabsToolbar > .toolbar-items {
  opacity: 0;
  pointer-events: none;
}
#main-window:not([tabsintitlebar="true"]) #TabsToolbar {
    visibility: collapse !important;
}

#sidebar-box[sidebarcommand="treestyletab_piro_sakura_ne_jp-sidebar-action"] #sidebar-header {
  display: none;
}

/*Collapse in default state and add transition*/
#sidebar-box[sidebarcommand="treestyletab_piro_sakura_ne_jp-sidebar-action"] {
    overflow: hidden;
    min-width: 40px;
    max-width: 40px;
    border-right: 1px solid #ccc;
    z-index: 2;
}

/*Expand to 260px on hover*/
#sidebar-box[sidebarcommand="treestyletab_piro_sakura_ne_jp-sidebar-action"]:hover,
#sidebar-box[sidebarcommand="treestyletab_piro_sakura_ne_jp-sidebar-action"] #sidebar {
  min-width: 260px !important;
  max-width: 260px !important;
  z-index: 1;
  margin-right: -204px !important;
}

:root {
  --sidebar-width: 58px;
  --toolbar-height: -50px;
  --menubar-height: -75px;
  --toolmenubar-height: -80px;
  --sidebar-padding: calc(var(--sidebar-width) + 5px);
}


#main-window #PersonalToolbar {
    margin-left: var(--sidebar-width);
}

/* lock sidebar to height by doing the inverse margin of the toolbar element */
#sidebar-box {
  z-index: 1000 !important;
  position: relative!important;
  margin-top: var(--menubar-height) !important;
  border-right: 1px solid #ccc;
}

#main-window[title^="Firefox Developer Edition"] #sidebar-box {
  margin-top: var(--toolmenubar-height) !important;
}

/* lock sidebar to specified width */
#sidebar-box, #sidebar-box #sidebar {
    min-width: var(--sidebar-width) !important;
    max-width: var(--sidebar-width) !important;
}

/* hide sidebar header for tree style tabs sidebar */
#sidebar-box[sidebarcommand="treestyletab_piro_sakura_ne_jp-sidebar-action"] #sidebar-header {
  display: none;
}

/* Hide the title bar */
#titlebar{ visibility: collapse; }

/* hide normal horizontal tab bar */
#TabsToolbar { visibility: collapse; }

#sidebar { border-right: 1px solid #ccc; }

toolbar#nav-bar {
  padding-top: 12px;
  padding-bottom: 7px;
  margin-left: var(--sidebar-padding);
  padding-left: 7px;
}

.sidebar-splitter {
  opacity: 0 !important;
  width: 0px !important;
  border: none !Important;
  --avatar-image-url: none !important;
}
```
