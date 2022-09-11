---
title: 'File Structure Examples'
---

As of v.0.5.6 file structure changed due to the scanner update
[Read how the new Scanner works here](https://wiki.kavitareader.com/en/guides/misc/how-the-scanner-works)
!! # Not Supported
Examples of Library Structures NOT SUPPORTED
```Library Root
  ┠── Series Name A
      ┠── Series Name A - v01.cbz
      
  ┖── Series Name B
      ┠── Series Name A - v02.cbz
```
```Library Root
  ┠── Publisher A
  │   ┖── Series Name A
  │       ┠── Series Name A - v01.cbz
  │       ⋮
  │       ┖── Series Name A - v06.cbz
  │
  ┖── Publisher B
      ┖── Series Name A
          ┠── Series Name A - v07.cbz
          ⋮
          ┖── Series Name A - v09.cbz
```
