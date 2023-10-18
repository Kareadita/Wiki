---
title: Filtering
media_order: 'new-filtering.png,customize-dashboard.png,smart-filters.png'
---

! This is a WIP for the new metadata filtering screen and Dashboard/Side Nav Customization

## Metadata Filtering
Kavita (v0.7.8+) has a rich metadata interface which allows you to build complex filters to find exactly what you're looking for. The system allows for you to build a series of statements that AND or OR together with custom sorting and a limit feature (for those that have large libraries). 

![new-filtering](new-filtering.png "new-filtering")

#### Filter Combination
(Table here of the different comparisons and how they work)

| Filter Combination           |   | Applies on           |  |           Description            |
|:-------------------|:---:|:-----------------------|:---:|:------------------------------------------:|
| `Matches`      |    | `String`              |   |                  Applies a search-like match on the field                   |
| `Equal`      |   | `Summary`              |   |                  Equals exactly                  |
| `Not Equal`      |    | `Summary`              |    |                  Doesn't Equal                  |

| Field Type           |   | Field           |  |           Description            |
| String 				  |   | Series Name || The Name of the Series | 
| String 				  |   | Summary || The Summary of the Series | 
| String 				  |   | Path || The file path to the highest level of the Series | 
| String 				  |   | File Path || The full file path for any file within the Series (note: this is slower than other fields) | 

### Smart Filters
A Smart Filter is essentially a saved filter (best created on All Series page). The underlying filter can be loaded and changed and anything that is bound with the Smart Filter will automatically be reflected of the new filters. Once you have a Smart Filter created, check out [Customization](https://wiki.kavitareader.com/en/guides/customization) to learn about how you can utilize the filters.

To create a Smart Filter, just add a name in the Name field and hit Save. Smart Filter names must be unique per user. Smart Filters are user-bound. 
![create_smart_filter](create_smart_filter.png "create_smart_filter")
![smart%20filter%20list](smart%20filter%20list.png "smart%20filter%20list")