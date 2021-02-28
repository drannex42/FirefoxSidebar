# Tree Style Tabs

This is a recreation (and better) version of my pseudo-popular Vivaldi vertical tab integration, for tree style tabs in firefox. 

```
/* Hide .twisty and adjust margins so favicons have 7px on left. */
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
  background: #F5F6F7; /* #F5F6F7; */
}


.favicon {
  --favicon-size: 21px !important;
  margin: 0;
  padding: 0 !important;
  --svg-small-icon-size: var(--favicon-size);
}
tab-item {
  border: 1px solid transparent !important;
  height: auto !important;
  position: relative !important;
  margin: 0px !important;
  font-size: 13px;
  background: none !important;
  overflow: hidden !important;
  text-align: center;
  box-shadow: none !important;
  border-radius: 5px;
  margin-bottom: 11px !important;
  margin: 10px !important;
  padding: 5px !important;
  margin-right: 12.5px !important;
  margin-left: 12px !important;
}
.tab .label {
  font-size: 13px !important;
}
#tabbar-container:not(:hover) {
  width: 58px;
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
  width: auto;
  text-align: center;
}
tab-item:not(:hover) {
  /*! display: none; */
}
tab-item .label, tab-item .highlighter, tab-item .contextual-identity-marker, tab-item .extra-items-container, tab-item .counter {
  /*! display: none; */
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
    border-top-color: currentcolor;
    border-top-style: none;
    border-top-width: medium;
box-shadow: none;
border-top: 1px solid var(--in-content-border-color);
padding: 10px;
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
```
