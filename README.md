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


## Arbitrary places

You can type any city/place, for example:
- Kota
- Kota, Rajasthan
- Jaipur, Rajasthan
- Tarapith, West Bengal
- Varanasi, Uttar Pradesh

The app geocodes the typed place using Open-Meteo before calculating the Panchanga.
For a plain `Kota`, it prefers Kota, Rajasthan, India when multiple matches are returned.
For better accuracy with smaller places, include district/state/country.


## Tithi mapping fix

The Sankalpa Sanskrit tithi mapping is zero-based to match the Panchanga library's `tithi` index. This prevents Navami from being rendered as Ashtami, etc.


## Added options

Deities:
- Batuka Bhairava
- Krishna
- Rama
- Narasimha

Rituals:
- Tarpanam
- Marjanam

These options are included in the Sanskrit ritual mapping used by the generator.

## Current-time Tithi and Nakshatra fix

The app now uses the Panchangam library's transition arrays (`tithis` and `nakshatras`) to determine the element prevailing at the exact current instant, rather than using the sunrise-anchored scalar `tithi`/`nakshatra` fields. This means if Nakshatra changes during the day, the displayed Nakshatra and Sankalpa update accordingly.
