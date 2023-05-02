# Index
* [6.0.x](#60x)
* [4.1.x](#41x)
* [4.0.x](#40x)

# 6.0.x
- updated to FullCalendar 6.1.6
- Migrated from Polymer 3 to Lit 2
- Migrated source code from JavaScript to TypeScript (ongoing process, not yet finished)
- Folder structures changed
- Tag names prefixed with "vaadin-"
- Content is now part of the light dom, thus styling will be easier
- Client side eager loading removed, items will now always be fetched
- Added prefetch mode to allow smoother transition between periods
- Breaking changes regarding methods and fields (client side and server side). Also usage of private / protected modifiers in TS.
- Deprecated code from previous versions has been removed
- JsonItem has been removed, Entry is a "normal field" class again due to issues with proxying frameworks
- setHeight has been minimalized to be more aligned with Vaadin standards. FC internal height settings / options are not
  supported anymore. Calendar content will take only as much space as needed.

Minor changes:
- getResources now may return null. Use getOrCreateResources. Has been aligned to other namings in Entry.
- CalendarLocale is now an enum. Use getLocale() to obtain the contained locale value.
- week numbers within days is no longer available, weeknumbers are now always display inside days. simply remove
- RenderingMode and alike namings have been named to DisplayMode / display to match the FC library naming. Also DisplayMode is now a top level class.
- added resize observer to client side to automatically take care of resizes

Other things that we may have overseen :) 

# 4.1.x
[Details](https://github.com/stefanuebe/vaadin_fullcalendar/wiki/Release-Notes-4.1.x)
- added EntryProvider, a data provider like callback based class to allow lazy loading entries based on the actual displayed timespan

# 4.0.x
[Details](https://github.com/stefanuebe/vaadin_fullcalendar/wiki/Release-Notes-4.0.x)
- introduced a new type JsonItem for creating item classes with dynamic property handling and automated conversion from and to json
- integrated json item api into Entry types for dynamic type conversion. Due to that entries will not send all data to the client, when updating existing ones
- changed date time handling on server side and communication to be always utc
- entries are not resent to server anymore when changing timezone on server
- entry data changes are now sent at once the the client
- client side entries ("event") have now a getCustomProperty method inside eventDidMount or eventContent callbacks
- removed official support of custom timezones for entries
- renamed several methods
- recurrence has some changes regarding enable recurrence and timezones