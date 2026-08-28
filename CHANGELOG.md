# Overhead release history

## 1.4.3 — 2026-08-28
- Fixed: "Use this Mac's location" failed instantly on first run. Asking macOS for permission puts a panel on screen and returns straight away, and Overhead was asking for the location on the very next line, before anyone could answer. It waits for the answer now
- When it does go wrong it says which thing went wrong: not allowed, never asked, Location Services switched off for the whole Mac, or a Mac that simply cannot place itself. Being told to type an address instead is no help when the real answer is in System Settings
- Fixed: the address box could not find places with names. "Tidewater Marina Portsmouth, VA" came back as "kCLErrorDomain error 8", which is a sentence for a developer. Overhead now searches the way Maps does, so marinas, parks, airports by name and businesses all work, in Go to Place as well
- Toolbar tooltips name their keyboard shortcut. With labels switched off the tooltip is the only thing a button can say about itself, and it is where the shortcut is worth finding
- Help has caught up: a section of its own for the Logbook, the light and golden hour, going somewhere else and saving it, the newer alert rules and their sounds. It also stopped telling you the house button changes your home location, and stopped describing a toolbar order that has not existed for three versions
- The Logbook tooltip said "Sighting statistics", which described one of its two tabs
- The toolbar is in a more sensible order. Left to right it now reads the way the app works: what is being searched and whether it is live, then where that search is pointed, then the things that open a window of their own, then how the map is drawn. The two appearance controls used to sit at opposite ends, with the altitude key stranded between the Logbook and the Home button
- The alert range now applies to every rule. First sightings and rare visitors used to ignore it, so setting three miles could still bring an alert about an aeroplane eleven miles away. Nothing is lost by the change: the logbook still records your whole search radius, and a type first met out at the edge waits, then announces itself when one comes close enough to be worth looking at
- Fixed: an airliner could name a bank as its operator. The name that comes with an aircraft is its registered owner, and for a leased airframe that is a trustee: one scheduled flight was reading "Umb Bank Na Trustee". Where the owner is plainly holding title rather than flying, the callsign's airline is used instead
- Cards can say where an aircraft is going even when no schedule knows: an aeroplane descending towards a runway, pointed at it and low enough to be arriving, is landing there. It reads "Arriving PDX" with the minutes left, and it needs no database, so it works for the light aircraft and charters no schedule service has heard of
- The Show the search radius switch has left Settings. It is in the View menu at Shift-Command-K, and as a toolbar button you can add in Settings, General, Toolbar
- Fixed: a flight could be labelled with the wrong destination for its whole journey. Routes come from a database keyed on the callsign, and an airline reuses a number across the legs of a day, so Portland to Fort Lauderdale was shown for an aircraft on its way to New York. Overhead now also checks the direction the flight has made good since departure, which catches that within about twenty minutes of take-off instead of never
- The blue search radius ring can be switched off, in Settings, Map, Search radius. It only stops the map drawing the ring: the same circle is still searched and the same aircraft still listed
- The house in the toolbar takes you home now. It used to open the panel for setting where home is, which is something you do once, and people were clicking it expecting the map to come back over their own roof. Changing home moved to the Sky menu, as Change Home Location
- Fixed: pressing Watch This Spot while the map was already centred on home started watching home, which put up a banner reading "watching a spot 0 mi from home" and offering to take you home, from home
- The Logbook button is a book rather than a bar chart. It is a logbook, and the chart was describing one tab of it
- The Home Location panel is the size of what is in it. It was being given the height of most of a first-run window to hold a title, a field and two buttons, and opened as a mostly empty box
- The sky and light capsules on the map are legible again. They sat on a translucent material that let the map through, so the station code and the time were washed out over dark water and fine over a pale field
- The pulse around a selected aircraft starts clear of the marker instead of on it. The ring was born at exactly the marker's own size, so every second or so the edge of the icon appeared to throb: slight at normal size, and obvious to anyone using the Mac's zoom
- Reduce motion in System Settings now stills the map too. Overhead had a switch of its own and honoured the system one only in the About window, though Help said otherwise
- Fixed: aircraft markers rocked in place. The heading a marker points is whatever the feed last reported, and that wanders: an airliner holds its track to half a degree, a light aircraft wanders two to five, and a Robinson R22 was measured swinging ten degrees with no turn behind it. Overhead now ignores the wander and follows the turns, so a marker points where the aeroplane is going and holds still when it is going straight. It was never an animation, which is why Reduce Motion made no difference to it
- The map keeps to its five-second refresh when a data source goes down. Overhead asks adsb.lol first and falls back to adsb.fi, and adsb.lol goes quiet for long stretches: every refresh was spending eight seconds waiting for it to time out, so updates were arriving every ten seconds instead of five. It now asks whichever source answered last time first
- Fixed: a flight could keep a route it had plainly finished. The altitude test had a ceiling but no floor, so a 737 descending through 3,600 ft over Portland still carried a Seattle to Kansas City label with 1,465 miles to run. It was landing here, and the database had a different leg of its day. An aircraft on the way down, low, with a long way still to go, is no longer believed
- Fixed: an aircraft could be reported as arriving somewhere it was far too low to reach. The check asked whether it was low enough to be coming down at a field and never whether it was high enough to still be flying there, so a Cessna in the circuit at 825 ft, pointed the right way, was arriving at an airport twenty two miles off that it would have reached underground
- Use this Mac's location names the place. It recorded your coordinates as "My location", which is the label the window title and the home callout then showed you
- Click the house on the map to see where Overhead is watching and change it. The marker is the one thing on screen that is your location, so it is now the place you set it, rather than a menu you had to know about first. Right-clicking it offers the same thing
- The window says which place you are watching. Nothing in it named the point that every distance, alert and record is measured from
- Your location is the first thing in Settings, General, with the place, its coordinates and a Change button. It used to live under Privacy, where the only thing on offer was forgetting it: you could throw your location away but not edit it
- The word "Home" is gone from the places that name that setting. It read as somewhere Overhead already knew about, rather than the point you chose for it to watch
- The first-run screen says what the app is for, explains what your location is used for and that you can change it later, and describes what actually leaves the Mac. It also sizes its window to itself instead of borrowing the map's, which left a small form adrift in a lot of empty space

## 1.4.2 — 2026-08-27
- Alerts sound different from one another. Overhead used one sound for all ten kinds, so an emergency squawk and a first sighting arrived indistinguishable: an emergency is its own sound now, a fly-over gets the shortest one there is because it is the alert you most need to hear from another room, and a first sighting or rare visitor gets a third. Everything else keeps the standard alert sound
- Four sounds made for this app join the fourteen macOS ships: Blip, a single radar return and the shortest thing in the list at a tenth of a second; Ident, the two-tone a transponder sends; Sweep, something detected and closing; and Contact, two soft notes for a first sighting
- Any sound you drop into your own Library/Sounds folder shows up in the list too, which is how custom alert sounds have always worked on the Mac
- Which sound goes in each of the three slots is yours to pick. Settings previews the choice as you make it, and one switch puts them all back to a single sound
- Records gains Lowest overhead: the lowest an aircraft has been when it actually came over you, rather than the lowest reading anywhere in the search circle. Those are different facts, and near an airport the second one always belongs to something on short final miles away
- It needs the height at the moment of closest approach, which was not being kept, so this record starts empty and fills over a day or two
- Forty-eight more aircraft types have names. A real logbook had 103 designators arriving nameless, so the common ones are named now: Cessna Stationairs and Skylanes, the Kodiak, the Husky, the Citabria, the Hawker 800 and the rest
- Five helicopters were being drawn with wings, among them the Hughes 500 that turned out to be the lowest thing ever to pass overhead here

## 1.4.1 — 2026-08-26
- Lowest seen in the logbook was usually nothing of the sort: an airliner on the runway at the airport down the road is doing 140 knots with its transponder still reporting the height of the tarmac, and Overhead filed that as a 25 ft pass over your house. It now knows where every airfield in the world is and how high it stands, so a reading taken over one stops counting as a pass over you
- Genuine low traffic is untouched. A light single at 800 ft over the houses is nowhere near a runway and still counts, which was the whole point of the figure
- The closest pass is judged the same way, so a landing at the strip two miles away can no longer file itself as the closest thing that ever came over
- Lowest seen carries the date it happened now, the way the closest pass does. They are rarely the same day and the card no longer implies they were
- Heights recorded before this cannot be sorted out after the fact, because all that survives of each one is a number. The ones a nearby runway could explain have been cleared, and fill in again the next time the aircraft comes over: a regular takes a day or two

## 1.4.0 — 2026-08-26
- **Go to Place**: type a city, an airport or an address and Overhead flies there and watches its sky. The banner names where you are, so it reads "Watching Boston, MA" rather than a distance from home, and clicking that name flies back if you have dragged the map away
- **Saved places**: star the spot you are watching and it is one click away from then on, instead of something you type the name of every time. Go to Place opens with them already listed, and they are in the Sky menu under Go to Saved Place
- **Golden hour**: a capsule on the map names the light where you are watching and how long it lasts. After sunset it names the altitude above which aircraft are still in sunlight and marks those aircraft in the sidebar, which is why an airliner can be lit orange against a sky that has already gone dark
- **Rare visitor alerts**: Overhead can tell you when a type you have hardly ever logged comes back after a long absence, which is a different thing from a first sighting. You set how few times counts as rare and how long it must have been away, and Settings reads your logbook to say how many alerts a day that works out to before you commit to it
- **Types to watch for**: a second watchlist for kinds of aircraft rather than particular ones, so Overhead can tell you about any 747, every A380, the next C-17. You do not need to know the ICAO codes: type 747 and it finds the 747-8 and the 747-400 by itself, and Settings lists what each entry catches so a typo says so rather than just staying quiet
- Right-click any aircraft on the map, in the sidebar, or in the logbook and choose Alert Me About Any to watch its type without opening Settings
- **Records in the logbook**: the closest thing ever to pass over you, the oldest aircraft you have logged, your busiest day, and the aircraft that turns up more than any other
- Most seen types and most seen operators, ranked as rows with the counts in a column you can read down. Click one to see every aircraft of that kind in the Gallery
- Operator names have lost their Inc and Llc endings, which also merges the airlines that were being counted twice under two spellings
- The note under the statistics says how many days your logbook covers, since a busiest day out of eight days recorded means something different from one out of eight years
- Fixed: watching another spot left the sky conditions from the place you came from on screen, station code and all, until a new report arrived
- Fixed: Fit All, and changing the search radius, threw the map back to home while you were watching somewhere else, leaving the banner and the sidebar describing a place the map was no longer showing

## 1.3.5 — 2026-08-26
- Settings, General, Toolbar now lists every toolbar button with a checkbox, so you can switch off the ones you never press. The buttons you keep stay in the order they have always been in
- Each one names where the same thing lives in the menus, so switching a button off is never the same as losing the feature. Hover a name to see which menu it is in
- Show All puts every button back
- Click a flight in Follow a Flight to see it on the map. One you are already tracking gets selected, with its halo, its detail card and its trail; one too far away to be on the map yet just takes the map to it

## 1.3.4.2 — 2026-08-26
- Fixed: buttons you added with Customize Toolbar came back in a different order the next time you opened the app, so they often looked like they had been dropped altogether. They had not been, but the toolbar could no longer be trusted to stay as you left it
- The toolbar now has one fixed order and keeps it. Customize Toolbar has gone with the fault, which is a real loss and not one made lightly: the reordering was in the toolbar machinery itself rather than in anything Overhead could reach, and a toolbar that stays put beat a customisable one that did not
- Every button on the toolbar is also in the menu bar, most of them with a keyboard shortcut, so nothing has become harder to get to
- Color by Altitude and Filter are no longer on the toolbar, where they were hidden by default anyway. Both are in the View menu

## 1.3.4.1 — 2026-08-25
- A bell on any aircraft adds it to the alert watchlist, so you can ask to be told when that aeroplane flies over again without opening Settings and typing its registration. It sits on the detail card and on the aircraft's own page in the logbook, and what it saves is the airframe, not the flight number
- Aircraft symbols sit properly centred in their circles now, in the sidebar, on the map and in the widgets

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
