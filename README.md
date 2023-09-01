# timezone-to-country
Retrieve the user's country location using their timezone

Mapping file of timezone names to ISO country codes. 
A very, very modest extension of the work detailed by this more clever developer here: 
https://www.techighness.com/post/get-user-country-and-region-on-browser-with-javascript-only/

Usage
```javascript
const timezones = require('./timezone_countries.json');
const fips = require('./fips_to_iso.json');

const timezoneName = new Intl.DateTimeFormat('en-US').resolvedOptions().timeZone;
let countryIso = timezones[timezoneName];
let countryName = fips.find(obj => obj.ISO === countryIso).Country;
console.log(countryName);
```

If you do not have a current countries data source that maps to ISO codes, highly recommend this project:
https://github.com/mledoze/countries
