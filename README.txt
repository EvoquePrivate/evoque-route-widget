EVOQUE ROUTE PREVIEW — SETUP

What this version does
- Replaces the two separate GeoComplete fields with one custom widget.
- Provides pickup and drop-off autocomplete.
- Displays one route map.
- Displays distance and estimated drive time.
- Saves pickup, drop-off, distance, and duration to the Jotform submission as JSON.

1. Google Cloud setup
Enable these APIs for your project:
- Maps JavaScript API
- Places API
- Directions API

Create or use a browser API key.
Restrict it by HTTP referrer after you know your hosting URL.
Do not put a server-secret key in this file.

2. Add your API key
Open index.html and replace:
AIzaSyCDYzOzfdMdN25Ad_yxyypQTnNjdTf5aYY
with your browser key.

3. Host the file for free
Recommended: Cloudflare Pages or GitHub Pages.
The final URL must use HTTPS, for example:
https://yourname.github.io/evoque-route-widget/

4. Register it as a private Jotform widget
- Open Jotform Developers > Widgets > Add Widget.
- Choose iFrame Widget.
- Name: Evoque Route Preview
- IFrame URL: your hosted index.html URL
- Width: 700
- Height: 455
- Keep it private while testing.

5. Add it to your form
- Remove the separate pickup and drop-off GeoComplete widgets.
- Add Evoque Route Preview in their place.
- Mark it required if both locations must be entered.

Submission value format
{"pickup":"...","dropoff":"...","distance":"19.2 mi","duration":"31 mins"}

Important limitation
A normal Jotform custom widget cannot directly read values from separate sibling GeoComplete fields using the documented widget API. This build therefore owns both address inputs itself. That is the reliable way to get one map and one route without duplicate fields.
