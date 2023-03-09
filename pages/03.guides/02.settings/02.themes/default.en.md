---
title: Themes
---

As of v0.5.2, Kavita now supports reading a .css file for custom theming.

Community created custom themes can be found on our [Theme repo](https://github.com/Kareadita/Themes).

There are a few things to note:
- The file must be .css
- The filename must only contain characters, numbers, and `-`
- The filename must match the top-level CSS property
- The .css file must be placed in `/config/themes`
- After placing the file in the directory, you must scan for it using the Scan button on the User Settings > Themes page before you can apply it.
- Optionally, you can set it as Default and all new accounts will have this theme auto-selected (they can override with their preference)
- This is limited to the properties we have exposed. (*See Available CSS Variables Below*)
  - If you would like any other properties exposed, please feel free to suggest themes in our [Discord](https://discord.gg/b52wT37kt7) server or [feature request page](https://feats.kavitareader.com/).

So for instance, if we created `/config/themes/test-theme-123.css` then the CSS within the file should be structured as follows
```css
:root .bg-test-theme-123 {
  /* CSS Variables here */
  }
```
>>> As of v0.5.3, Kavita only supports the Dark theme out of the box. However, you can find a good starting point for [Light](https://wiki.kavitareader.com/en/guides/settings/themes/light-theme-starter)/[E-Ink](https://wiki.kavitareader.com/en/guides/settings/themes/eink-theme-starter) themes here. As of v0.7, you no longer need to maintain all the css variables, only those you need to override.
 
 <hr style="border:5px solid #4ac694"> </hr>

## Available CSS Variables
**Note**: You can use `color: var(--css-variable-name)` to refer to a defined css variable.

**Color-scheme**  
*This refers to the scroll bar color as well as which color placeholder images to use.*  
```
--color-scheme: dark/light;
```

*This refers to the tab color in the browser. Modifies the meta tag. (v0.6.1.27+)*  
```
--theme-color: hex/rgb;
```

*This refers to the tile color for windows tile view. Modifies the meta tag. (v0.6.1.28+)*  
```
--tile-color: hex/rgb;
```

    
**Main Colors**  
*These refer to base colors you can override, you can add more and use them as additional colors for hovers.*  
```css
--primary-color: hex/rgb(a);  
--primary-color-dark-shade: hex/rgb(a);  
--primary-color-darker-shade: hex/rgb(a);  
--primary-color-darkest-shade: hex/rgb(a);  
--error-color: hex/rgb(a);  
--bs-body-bg: hex/rgb(a);  // Background color for pages  
--body-text-color: hex/rgb(a);   
--btn-icon-filter: invert(1) grayscale(%) brightness(%));  // Any filter chain. Useful mainly for dark themes
--primary-color-scrollbar: hex/rgb(a); 
```
  
**Navbar**
```css
--navbar-bg-color: hex/rgb(a);    
--navbar-text-color: hex/rgb(a);  
--navbar-fa-icon-color: hex/rgb(a);  
--navbar-btn-hover-outline-color: hex/rgb(a);  
```

**Inputs**  
```css
--input-bg-color: hex/rgb(a);  
--input-bg-readonly-color: hex/rgb(a);  
--input-focused-border-color: hex/rgb(a);  
--input-text-color: hex/rgb(a);  
--input-placeholder-color: hex/rgb(a);  
--input-border-color: hex/rgb(a);  
--input-focus-boxshadow-color: hex/rgb(a);  
```

**Buttons**  
```css
--btn-primary-text-color: hex/rgb(a);  
--btn-primary-bg-color: hex/rgb(a);  
--btn-primary-border-color: hex/rgb(a);  
--btn-primary-hover-text-color: hex/rgb(a);  
--btn-primary-hover-bg-color: hex/rgb(a);  
--btn-primary-hover-border-color: hex/rgb(a);  
--btn-alt-bg-color: hex/rgb(a);  
--btn-alt-border-color: hex/rgb(a);  
--btn-alt-hover-bg-color: hex/rgb(a);  
--btn-alt-focus-bg-color: hex/rgb(a);  
--btn-alt-focus-boxshadow-color: hex/rgb(a);  
--btn-fa-icon-color: hex/rgb(a);  
--btn-disabled-bg-color: hex/rgb(a);  
--btn-disabled-text-color: hex/rgb(a);  
--btn-disabled-border-color: hex/rgb(a);  
--btn-focus-boxshadow-color: hex/rgb(a);  
--btn-alt-focus-boxshadow-color: hex/rgb(a);  
--btn-fa-icon-color: hex/rgb(a);  
--btn-disabled-bg-color: hex/rgb(a);  
--btn-disabled-text-color: hex/rgb(a);  
--btn-disabled-border-color: hex/rgb(a);  
```  

**Nav (Tabs)**
```css
--nav-tab-border-color: hex/rgb(a);  
--nav-tab-text-color: hex/rgb(a);  
--nav-tab-bg-color: hex/rgb(a);  
--nav-tab-hover-border-color: hex/rgb(a);  
--nav-tab-active-text-color: hex/rgb(a);  
--nav-link-bg-color: hex/rgb(a);  
--nav-link-active-text-color: hex/rgb(a);  
--nav-link-text-color: hex/rgb(a);  
--nav-tab-border-top: hex/rgb(a);  
--nav-tab-border-left: hex/rgb(a);  
--nav-tab-border-bottom: var(--bs-body-bg);  
--nav-tab-border-right: hex/rgb(a);  
--nav-tab-hover-text-color: hex/rgb(a);  
--nav-tab-hover-bg-color: hex/rgb(a);  
--nav-tab-hover-border-top: hex/rgb(a);  
--nav-tab-hover-border-left: hex/rgb(a);  
--nav-tab-hover-border-bottom: hex/rgb(a);  
--nav-tab-hover-border-right: hex/rgb(a);  
--nav-tab-active-hover-bg-color: hex/rgb(a);  
--nav-link-bg-color: hex/rgb(a);  
--nav-link-active-text-color: hex/rgb(a);  
--nav-link-text-color: hex/rgb(a);  
```

**Header**  
```css
--nav-header-text-color: hex/rgb(a);  
--nav-header-bg-color: hex/rgb(a);  
```

**Toasts**  
```css
--toast-success-bg-color: hex/rgb(a);  
--toast-error-bg-color: hex/rgb(a);  
--toast-info-bg-color: hex/rgb(a);  
--toast-warning-bg-color: hex/rgb(a);  
```  

**Checkboxes**  
```css
--checkbox-checked-bg-color: hex/rgb(a);  
--checkbox-border-color: hex/rgb(a);  
--checkbox-focus-border-color: hex/rgb(a);  
--checkbox-focus-boxshadow-color: hex/rgb(a);  
```  

**Tag Badge**  
```css
--tagbadge-border-color: hex/rgb(a);  
--tagbadge-text-color: hex/rgb(a);  
--tagbadge-bg-color: vhex/rgb(a);  
--tagbadge-filled-border-color: hex/rgb(a);  
--tagbadge-filled-text-color: hex/rgb(a);  
--tagbadge-filled-bg-color: hex/rgb(a);  
```

**Side Nav**  
```css
--side-nav-bg-color: hex/rgb(a);  
--side-nav-mobile-bg-color: hex/rgb(a);  
--side-nav-openclose-transition: s ease-in-out;  
--side-nav-box-shadow: hex/rgb(a);  
--side-nav-mobile-box-shadow: px/em hex/rgb(a);  
--side-nav-hover-text-color: hex/rgb(a);  
--side-nav-hover-bg-color: hex/rgb(a);  
--side-nav-color: hex/rgb(a);  
--side-nav-border-radius: px;  
--side-nav-border: hex/rgb(a)/none;  
--side-nav-border-closed: hex/rgb(a)/none;  
--side-nav-border-transition: s ease-in-out;  
--side-nav-companion-bar-transistion:s linear;  
--side-nav-bg-color-transition: s ease-in-out;  
--side-nav-closed-bg-color: hex/rgb(a);  
--side-nav-item-active-color: hex/rgb(a);  
--side-nav-item-active-text-color: hex/rgb(a);  
--side-nav-active-bg-color: hex/rgb(a);  
--side-nav-overlay-color: hex/rgb(a);  
```

**List items**  
```css
--list-group-item-text-color: hex/rgb(a);  
--list-group-item-bg-color: hex/rgb(a);  
--list-group-item-border-color: hex/rgb(a);  
--list-group-hover-text-color: hex/rgb(a);  
--list-group-hover-bg-color: hex/rgb(a);  
--list-group-active-border-color: hex/rgb(a);
```  

**Popover**  
```css
--popover-body-bg-color: hex/rgb(a);  
--popover-body-text-color: hex/rgb(a);  
--popover-outerarrow-color: hex/rgb(a);  
--popover-arrow-color: hex/rgb(a);  
--popover-bg-color: hex/rgb(a);  
--popover-border-color: hex/rgb(a);  
```

**Pagination**
``` css
--pagination-active-link-border-color: hex/rgb(a);  
--pagination-active-link-bg-color: hex/rgb(a);  
--pagination-active-link-text-color: hex/rgb(a);  
--pagination-link-border-color: hex/rgb(a);  
--pagination-link-text-color: hex/rgb(a);  
--pagination-link-bg-color: hex/rgb(a);  
--pagination-focus-border-color: hex/rgb(a);  
--pagination-link-hover-color: hex/rgb(a);
```

**Progress Bar**  
``` css
--progress-striped-animated-color: linear-gradient(deg, rgba %, deg, rgba %, ..., deg, rgba %));  
--progress-bg-color: hex/rgb(a);  
--progress-bar-color: hex/rgb(a);  
```  

**Dropdown**  
```css
--dropdown-item-hover-text-color: hex/rgb(a);  
--dropdown-item-hover-bg-color: hex/rgb(a);  
--dropdown-item-text-color: hex/rgb(a);  
--dropdown-item-bg-color: hex/rgb(a);  
--dropdown-overlay-color: hex/rgb(a);  
```

**Accordion**  
```css
--accordion-header-text-color: hex/rgb(a);  
--accordion-header-bg-color: hex/rgb(a);  
--accordion-body-bg-color: hex/rgb(a);  
--accordion-body-border-color: hex/rgb(a);  
--accordion-body-text-color: hex/rgb(a);  
--accordion-header-collapsed-text-color: hex/rgb(a);  
--accordion-header-collapsed-bg-color: hex/rgb(a);  
--accordion-button-focus-border-color: hex/rgb(a);  
--accordion-button-focus-box-shadow: hex/rgb(a);  
--accordion-active-body-bg-color: hex/rgb(a);  
--accordion-body-box-shadow: hex/rgb(a);  
```  

**Breadcrumb**  
```css
--breadcrumb-bg-color: hex/rgb(a);  
--breadcrumb-item-text-color: hex/rgb(a);  
```  

**Rating star**  
```css
--ratingstar-color: hex/rgb(a);  
--ratingstar-star-empty: hex/rgb(a);  
--ratingstar-star-filled: hex/rgb(a);  
```  

**Global**  
```css
--hr-color: hex/rgb(a);  
--accent-bg-color: hex/rgb(a);  
--accent-text-color: hex/rgb(a);  
--grid-breakpoints-xs: px;  
--grid-breakpoints-sm: px;  
--grid-breakpoints-md: px;  
--grid-breakpoints-lg: px;  
--grid-breakpoints-xl: px;  
--body-font-family: "Font-Family", sans-serif;  
--brand-font-family: "Font-Family", sans-serif;  
```  

**Card**  
```css
--card-bg-color: hex/rgb(a);  
--card-text-color: hex/rgb(a);  
--card-border-width: hex/rgb(a);  
--card-border-style: hex/rgb(a);  
--card-border-color: hex/rgb(a);  
--card-progress-bar-color: hex/rgb(a);  
--card-overlay-bg-color: hex/rgb(a);  
--card-overlay-hover-bg-color: hex/rgb(a);  
--card-progress-triangle-size: hex/rgb(a);  
```

**Slider**  
```css
--slider-text-color: hex/rgb(a);
--input-range-color: hex/rgb(a);
--input-range-active-color: hex/rgb(a);
```

**Manga Reader**
```css
--manga-reader-overlay-filter: Filter(px);  
--manga-reader-overlay-bg-color: hex/rgb(a);  
--manga-reader-overlay-text-color: hex/rgb(a);  
--manga-reader-next-highlight-bg-color: hex/rgb(a);  
--manga-reader-prev-highlight-bg-color: hex/rgb(a);  
```    

**Radios**  
```css
--radio-accent-color: hex/rgb(a);  
--radio-hover-accent-color: hex/rgb(a);  
--radio-focus-boxshadow-color: hex/rgb(a);  
```  

 **Carousel**  
```css
--carousel-header-text-color: hex/rgb(a);  
--carousel-header-text-decoration: hex/rgb(a);  
--carousel-hover-header-text-decoration: hex/rgb(a);  
```

**Drawer**  
```css
--drawer-bg-color: hex/rgb(a);
--drawer-text-color: hex/rgb(a);
```

**Event Widget**
```
--event-widget-bg-color: hex/rgb(a);  
--event-widget-item-bg-color: hex/rgb(a);  
--event-widget-text-color: hex/rgb(a);  
--event-widget-item-border-color: hex/rgb(a);  
--event-widget-border-color: hex/rgb(a);  
--event-widget-info-bg-color: hex/rgb(a);  
```

**Search Results** 
```css
--search-result-text-lite-color: hex/rgb(a);
```

**Bulk Selection** 
```css
--bulk-selection-highlight-text-color: hex/rgb(a);
--bulk-selection-text-color: hex/rgb(a);
```

**Card List Item** 
```css
--card-list-item-bg-color: hex/rgb(a);
```
