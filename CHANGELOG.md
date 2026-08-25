# Overhead release history

## 1.3.4 — 2026-08-25
- Fit All, Home, Watch Here and the map style have moved off the map and into the toolbar, so the map is all map. Each one is still in the View menu with its keyboard shortcut, and the toolbar itself can be rearranged or trimmed from right-click, Customize Toolbar
- Your toolbar arrangement resets once with this update, so the three controls that just moved are on it when you open the app
- A new app icon, drawn in layers so macOS 26 can light it the way it lights everything else

## 1.3.3 — 2026-08-24
- Helicopters now show as helicopters, on the map and in the sidebar: rotor and tail, pointing the way they are going
- Aircraft sitting at airports are hidden by default, since they are not overhead. Bring them back from the filter menu

## 1.3.2 — 2026-08-23
- The logbook has a gallery: every aircraft that has flown over, with a photo of that exact airframe wherever one exists
- Open any of them for its own page: when you first saw it, how many days it has been over, its closest pass, and how old it is
- Sort the gallery by recent, most seen, closest, or oldest airframe
- Search the gallery by registration, type or operator: "alaska", "737", "N236"
- Arrow keys move through the gallery, Space shows the photo in Quick Look, and Return opens the aircraft
- Right-click any aircraft to copy its registration or photo, or open the photo on Planespotters
- Drag an aircraft out of the gallery into Notes, Mail or the Finder
- File > Export Logbook writes the whole collection as a CSV that opens in Numbers
- Overhead now has Shortcuts actions: get the aircraft overhead, get sky conditions, or follow a flight
- Aircraft come back as real items, so a shortcut can use one flight's altitude, distance or age on its own
- Ask Siri or Spotlight what's flying over you, without setting anything up first
- Every toolbar button now has a place in the menus too, with keyboard shortcuts: a new Sky menu, Legend in View, Logbook in Window
- Right-click the toolbar to customise it: add, remove and reorder buttons, and choose whether names show
- The toolbar palette offers five buttons that aren't there by default: Fit All, Watch Here, Map Style, Color by Altitude and Filter
- The Settings option for toolbar names is gone, because the Customize Toolbar sheet already does it, where the Mac keeps that control. If you had names switched on, right-click the toolbar and choose Icon and Text to get them back

## 1.3.1 — 2026-08-22
- Aircraft cards now show the year the airframe was built, and how old it is
- The sidebar's Low Altitude filter grows into a full set of height bands, on the same boundaries as the map's altitude key
- Height bands narrow the other filters rather than widening them, so Airliners plus Above 30,000 ft means high airliners
- The app icon now shows contacts on the scope, not just the rings
- The About window's radar paints those same contacts as the beam reaches them
- The radar now sits in the middle of the app icon, instead of a little low
- The aircraft is shaded and casts a shadow on the scope, so it reads as an object rather than a cut-out

## 1.3.0 — 2026-08-22
- Selecting an airline flight now draws its route on the map, from the aircraft to its destination
- The Legend explains the difference between a trail (where an aircraft has been) and a route (where it is going)
- Turn routes off with View > Show Flight Routes
- ATC feeds can be renamed, or pointed at a new address, without removing and adding them again
- The radar in the About window now sweeps the way a radar does, instead of pulsing
- Fixed: quitting could lose up to a minute of logbook entries
- Fixed: watching another spot no longer files that spot's traffic in your logbook
- Fixed: the sky conditions tooltip never showed when the reading was taken
- Fixed: the menu bar could count more aircraft than it listed while a filter was on
- Fixed: a followed flight could be checked twice at once when a data source was slow
- Fixed: aircraft parked at an airport near you no longer count as flying overhead in the menu bar or the widgets

## 1.2.9 — 2026-08-21
- The toolbar now shows icons only, with a setting in General to put the names back

## 1.2.8 — 2026-08-21
- The nearest aircraft can now live in your menu bar, with the six closest a click away
- Choose how much the menu bar shows: callsign and distance, distance only, or just the icon
- First sightings: Overhead learns what normally flies over you, then tells you when something new does
- Sky conditions on the map, so you know whether anything up there is actually visible
- Watch Here follows any spot on the map instead of home, for travelling or watching someone else's airport
- ATC Audio lists the airports nearest you and walks you through adding one of their feeds
- Saved ATC feeds can be exported and shared, and a downloaded .pls file opens straight into Overhead
- Launch at login moved to Settings → General, where you would look for it
- The alert watchlist takes one code at a time, each becoming a pill you can remove
- Alert range is now a slider, shown in your own distance units
- Fixed: the aircraft list could stay empty when a data source was slow to answer

## 1.2.7 — 2026-08-21
- Follow a flight by number and get a notification when it takes off and when it lands
- Flight numbers are checked as you add them, so a typo doesn't sit there waiting forever
- Airline flights now show an estimated landing time, in your own time zone
- Keep several aircraft on screen at once: pin cards and they stack, folded down to the essentials
- With two cards up, a line between them shows how far apart the aircraft are and whether they're converging
- Aircraft cards can be dragged anywhere on the map, and no longer sit under the zoom controls
- Routes that clearly belong to a different leg of the day are now hidden rather than shown as fact
- Flight progress no longer reads 100% while an aircraft is still a couple of minutes out

## 1.2.6 — 2026-08-20
- Airline flights now show their route up front: origin, destination, and city names
- A progress bar shows how far along the flight is and how far it has left to go
- Photo credits are now readable, and clicking a photo opens it on Planespotters

## 1.2.5 — 2026-08-20
- Overhead now updates itself from seeoverhead.app, its new home on the web
- Release notes now live on the website, and open there from Help → Release History
- Widget images on the website center properly on smaller screens

## 1.2.4 — 2026-08-19
- New Style button on the map switches between Standard, Muted, Satellite, and Hybrid
- Map controls are easier to see over bright satellite imagery

## 1.2.3 — 2026-08-19
- Sidebar filters and search now apply to the map as well, so the list and map always show the same aircraft
- Alerts and the logbook still watch all traffic, even while filtered

## 1.2.2 — 2026-08-19
- Update notifications now show what's new in each release
- Release history link in the About window and Help menu

## 1.2.1 — 2026-08-19
- Fixed map controls covering the Apple Maps logo and Legal link

## 1.2 — 2026-08-19
- Automatic updates: Overhead now updates itself (Overhead menu → Check for Updates…)
- ATC Audio: listen to live air-traffic-control streams from the toolbar
- Aircraft photos, flight routes, and operator names in the detail card
- "Spot it" guidance: which way to look and how high, for every aircraft
- Full aircraft make/model names throughout (Boeing 737-900 instead of B739)
- Flight trails with adjustable length and width
- Altitude color-coding with an on-map key
- Sidebar filters: emergency, military, helicopters, airliners, GA, low altitude, in any combination
- Alerts: fly-over prediction, military/helicopter/low-altitude/watchlist rules, alert range, launch at login
- Logbook: daily sighting counts, busiest hours, and newly spotted types
- Widget accent color; distance units (mi/nm/km); text size and accessibility options
- Redesigned Settings with General, Map, Alerts, Accessibility, and Privacy panes

## 1.1 — 2026-08-19
- Universal app: runs natively on Apple Silicon and Intel Macs
- Notarized by Apple for safe distribution

## 1.0 — 2026-08-18
- Initial release: live aircraft map and list around your home, desktop widgets,
  emergency and military highlighting, powered by community ADS-B data
