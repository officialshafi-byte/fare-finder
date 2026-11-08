# Fare Finder (Netlify)

Type From, To, dates and adults. It shows live fares from Google Flights, compares each flight's price on every booking site, and gives a Book button for each site.

## Put it online (no coding)
Drag-and-drop uploads on Netlify only publish the page, not the live price search, so use GitHub:

1. Go to github.com/new, name the repository `fare-finder`, choose **Private**, and press **Create repository**.
2. On the next page, press **uploading an existing file**. Drag in everything from this unzipped folder: the `public` and `netlify` folders and `netlify.toml`. Press **Commit changes**.
3. In Netlify, choose **Add new project**, then **Import an existing project**, then **GitHub**. Pick `fare-finder` and press **Deploy**. Leave the build settings empty.
4. In Netlify, open the project, then **Project configuration**, then **Environment variables**. Add `SERPAPI_KEY` with your SerpApi key as the value.
5. Open **Deploys**, then **Trigger deploy**, then **Deploy project**. Your app is now live at the address Netlify shows.

## Install on your phone
- iPhone: open the address in Safari, then Share, then **Add to Home Screen**.
- Android: open it in Chrome, then the menu, then **Install app** (or **Add to Home screen**).

## Good to know
- Each search uses about 6 SerpApi searches (about 11 for a return trip). Your SerpApi dashboard shows how many you have left.
- Fares and Book links expire within hours. Search again before booking, and check the final price before paying.
- Google's self-transfer deals (two separate tickets) aren't included. Check Google Flights for those.

## For developers
Static page in `public/`, one Netlify Edge Function in `netlify/edge-functions/api.js` (`/api/search` and `/api/sites`). Deploy with `npx netlify deploy --prod` from this folder.
