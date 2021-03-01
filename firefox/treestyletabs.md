# Tree Style Tabs

This is a recreation (and better) version of my pseudo-popular Vivaldi vertical tab integration, for tree style tabs in firefox. 

```/* Hide .twisty and adjust margins so favicons have 7px on left. */
.tab .twisty {
	visibility: hidden;
	margin-left: -8px;
  display: none;
}

tab-item:hover {
  background:    var(--in-content-box-background-hover) !important;
  opacity: 1;
}


/* Push tab labels slightly to the right so they're completely hidden in collapsed state */
.tab .label {
	font-size: 16px;
  	padding-left: 5px
}

.tab:not(:hover) > .closebox {
  display: none;
}

.closebox:hover {
  font-weight: 900;
}

.tab, .tabs, body, #background {
   /* #F5F6F7; */
  background: transparent;
}


.favicon {
  --favicon-size: 17px !important;
  margin: 0;
  padding: 0 !important;
  --svg-small-icon-size: var(--favicon-size);
  /*! text-align: center; */
  margin-left: .5px;
}
tab-item {
  border: 1px solid transparent !important;
  height: auto !important;
  position: relative !important;
  font-size: 13px;
  background: none !important;
  overflow: hidden !important;
  text-align: center;
  box-shadow: none !important;
  border-radius: 5px;
  padding: 5px !important;
  margin: 7.5px 11px !Important;
  text-align: center;
}
.tab .label {
  font-size: 13px !important;
}
#tabbar-container:not(:hover) {
  width: 50px;
  /*! margin: 2px; */
}
#all-tabs {
}
#tabbar {
}
#tabbar:hover {
  max-width: 100%;
}
#tabbar:not(:hover) tab-item {
  overflow: hidden !important;
  width: 100%;
  width: 30px;
  text-align: center;
}
tab-item:not(:hover) {
}
tab-item .label, tab-item .highlighter, tab-item .contextual-identity-marker, tab-item .extra-items-container, tab-item .counter {
  /*! display: none; */
  /*! margin: 0px !Important; */
}
tab-item.active {
  background-color: var(--in-content-box-background) !important;
  box-shadow: 0px 5px 10px var(--in-content-box-background-active) !important;
}

:root .tab .highlighter::before {
    display: none;
}

.after-tabs button {
  border: none;
  box-shadow: none;
  padding: 5px;
  margin: 11px;
  text-align: left;
  background: none;
}

.after-tabs button:hover {
    background: var(--in-content-box-background-hover) !important;
    opacity: 1;
    border-radius: 5px;
}

#tabbar:hover [data-level="1"] {
    margin-left: 22px !important;
}

#tabbar:hover [data-level="2"] {
    margin-left: 32px !important;
}

#tabbar:hover [data-level="3"] {
    margin-left: 42px !important;
}

#tabbar:hover [data-level="4"] {
    margin-left: 52px !important;
}

#tabbar:hover [data-level="5"] {
    margin-left: 62px !important;
}

#tabbar:hover [data-level="6"] {
    margin-left: 72px !important;
}

#tabbar:hover [data-level="7"] {
    margin-left: 82px !important;
}

#tabbar:hover [data-level="8"] {
    margin-left: 82px !important;
}

#tabbar::before {
  content: " ";
  height: 21px;
  width: 100%;
  background:   url('data:image/png;base64,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');
  background-size: contain;
  background-repeat: no-repeat;
  margin-top: 16px;
  margin-bottom: 3px;
  text-align: right;
  margin-right: -15px !important;
  opacity: 0.65;
}


.newtab-button {
  /*! text-align: left; */
  /*! margin: 8px !important; */
}

.newtab-button::after {
  content: "New Tab";
  font-size: 13px;
  padding-left: 10px;
  margin-top: 0px;
  position: absolute;
  opacity: 0.85;
  display: none;
}

.after-tabs {
  border-top: 1px solid var(--in-content-border-color);
}

#tabbar-container:hover .newtab-button::after {
  display: inline-block;
}


#tabbar-container {
  background: var(--theme-colors-toolbar);
}

.newtab-button::before {
    padding-left: 1.5px;
}
```
