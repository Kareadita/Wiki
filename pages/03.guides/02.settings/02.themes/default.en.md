---
title: Themes
---

As of v0.5.2 Kavita now supports reading a .css file for custom theming.

There are a few things to note:
- The filename must only contain characters, numbers, and `-`
- The filename must match the top level css property
- The file must be .css
- The .css file must be placed in `/config/themes`

So for instance if we created `test-theme-123` then css within should be structured as follows
``` 
:root .bg-test-theme-123 {
	/* CSS Variables here */
  } 
  ```
  <hr style="border:5px solid #4ac694"> </hr>
## Available CSS Variables
**Note**: You can use `color: var(--css-variable-name)` to refer to a defined css variable.

**Color-scheme**
*This refers to the scroll bar color as well as which color placeholder images to use.*  
--color-scheme: dark/light;  
    
**Main Colors**  
*These refer to base colors you can override, you can add more here and use them as additional colors for hovers.*  
--primary-color: hex/rgb(a);  
--error-color: hex/rgb(a);  
--bs-body-bg: hex/rgb(a);  
--body-text-color: hex/rgb(a);   
--btn-icon-filter: filter(px);  
  
**Navbar**  
--navbar-bg-color: hex/rgb(a);    
--navbar-text-color: hex/rgb(a);  
--navbar-fa-icon-color: hex/rgb(a);  
  
**Inputs**  
--input-bg-color: hex/rgb(a);  
--input-bg-readonly-color: hex/rgb(a);  
--input-focused-border-color: hex/rgb(a);  
--input-text-color: hex/rgb(a);  
--input-placeholder-color: hex/rgb(a);  
--input-border-color: hex/rgb(a);  
  
**Buttons**  
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

**Nav**  
--nav-tab-border-color: hex/rgb(a);  
--nav-tab-text-color: hex/rgb(a);  
--nav-tab-bg-color: hex/rgb(a);  
--nav-tab-hover-border-color: hex/rgb(a);  
--nav-tab-active-text-color: hex/rgb(a);  
--nav-link-bg-color: hex/rgb(a);  
--nav-link-active-text-color: hex/rgb(a);  
--nav-link-text-color: hex/rgb(a);  
--nav-tab-hover-text-color: hex/rgb(a);  
--nav-tab-hover-bg-color: hex/rgb(a);  
--nav-tab-border-top: hex/rgb(a);  
--nav-tab-border-left: hex/rgb(a);  
--nav-tab-border-bottom: var(--bs-body-bg);  
--nav-tab-border-right: hex/rgb(a);  
--nav-tab-border-hover-top: hex/rgb(a);  
--nav-tab-border-hover-left: hex/rgb(a);  
--nav-tab-border-hover-bottom: hex/rgb(a);  
--nav-tab-border-hover-right: hex/rgb(a);  

**Toasts**  
--toast-success-bg-color: hex/rgb(a);  
--toast-error-bg-color: hex/rgb(a);  
--toast-info-bg-color: hex/rgb(a);  
--toast-warning-bg-color: hex/rgb(a);  
  
**Checkboxes**  
--checkbox-checked-bg-color: hex/rgb(a);  
--checkbox-border-color: hex/rgb(a);  
--checkbox-focus-border-color: hex/rgb(a);  
  
**Tag Badge**  
--tagbadge-border-color: hex/rgb(a);  
--tagbadge-text-color: hex/rgb(a);  
--tagbadge-bg-color: hex/rgb(a);  
  
**List items**  
--list-group-item-text-color: hex/rgb(a);  
--list-group-item-bg-color: hex/rgb(a);  
--list-group-item-border-color: hex/rgb(a);  
--list-group-hover-text-color: hex/rgb(a);  
--list-group-hover-bg-color: hex/rgb(a);  
  
**Popover**  
--popover-body-bg-color: hex/rgb(a);  
--popover-body-text-color: hex/rgb(a);  
  
**Pagination**  
--pagination-active-link-border-color: hex/rgb(a);  
--pagination-active-link-bg-color: hex/rgb(a);  
--pagination-active-link-text-color: hex/rgb(a);  
--pagination-link-border-color: hex/rgb(a);  
--pagination-link-text-color: hex/rgb(a);  
--pagination-link-bg-color: hex/rgb(a);  
--pagination-focus-border-color: hex/rgb(a);  
  
**Dropdown**  
--dropdown-item-hover-text-color: hex/rgb(a);  
--dropdown-item-hover-bg-color: hex/rgb(a);  
--dropdown-item-text-color: hex/rgb(a);  
--dropdown-item-bg-color: hex/rgb(a);  
--dropdown-overlay-color: hex/rgb(a);  
  
**Accordion**  
--accordion-header-text-color: hex/rgb(a);  
--accordion-header-bg-color: hex/rgb(a);  
--accordion-body-bg-color: hex/rgb(a);  
--accordion-body-border-color: hex/rgb(a);  
--accordion-body-text-color: hex/rgb(a);  
--accordion-header-collapsed-text-color: hex/rgb(a);  
--accordion-header-collapsed-bg-color: hex/rgb(a);  
  
**Breadcrumb**  
--breadcrumb-bg-color: hex/rgb(a);  
--breadcrumb-item-text-color: hex/rgb(a);  
  
**Rating star**  
--ratingstar-color: hex/rgb(a);  
--ratingstar-star-empty: hex/rgb(a);  
--ratingstar-star-filled: hex/rgb(a);  
  
**Global**  
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
  
**Card**  
--card-bg-color: hex/rgb(a);  
--card-text-color: hex/rgb(a);  
--card-border-color: hex/rgb(a);  
--card-progress-bar-color:: hex/rgb(a);  
--card-overlay-hover-bg-color: hex/rgb(a);  

**Slider**  
--slider-text-color: hex/rgb(a);  
  
**Manga Reader**  
--manga-reader-overlay-filter: Filter(px);  
--manga-reader-overlay-bg-color: hex/rgb(a);  
--manga-reader-overlay-text-color: hex/rgb(a);  
--manga-reader-bg-color: hex/rgb(a);  
--manga-reader-next-highlight-bg-color: hex/rgb(a);  
--manga-reader-prev-highlight-bg-color: hex/rgb(a);  
    
**Radios**  
--radio-accent-color: hex/rgb(a);  
--radio-hover-accent-color: hex/rgb(a);  
	
 **Carousel**  
 --carousel-header-text-color: hex/rgb(a);  

