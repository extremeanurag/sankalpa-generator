# Sanskrit Sankalpa iPhone Web App — Full Version

## What this version does

- Runs in Safari on iPhone; no Pyto required.
- Calculates Panchanga in the browser using `@ishubhamx/panchangam-js`.
- Explicitly requests `calendarType: "purnimanta"`.
- Uses IST (+330 minutes).
- Calculates Tithi, Nakshatra, Masa, Paksha, sunrise and sunset.
- Deity selector.
- Ritual selector.
- Place selector/input.
- Default place: Kadugodi, Bengaluru.
- Default place adds `मम गृहे`.
- Any explicitly changed place omits `मम गृहे`.
- Copy and Share buttons.
- PWA manifest for Add to Home Screen.

The Panchanga library is loaded from esm.sh, so the first use needs internet access. After the browser has cached resources, behavior may vary by Safari cache rules.

## Built-in locations

Kadugodi, Bengaluru
Tarapith, West Bengal
Tarapith
Kolkata, West Bengal
Puri, Odisha
Jajpur, Odisha
Ujjain, Madhya Pradesh
Varanasi, Uttar Pradesh

For an arbitrary location, the app can request the iPhone's current coordinates. The Sanskrit location text is kept as the supplied place rather than inventing a Sanskrit translation.

## Important verification note

The JavaScript Panchanga library documents Purnimanta support and says its scalar day-level Tithi/Nakshatra/Masa fields follow the sunrise convention. It also reports validation against Drik Panchang. The app therefore uses the library's sunrise-day values rather than scraping Drik Panchang HTML.

For ritual use, you should still compare an unfamiliar location/date against your preferred Panchanga source before relying on it.
