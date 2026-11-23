# Orbit Cloud V12

Single-page Orbit attendance tracker with Supabase authentication and cloud sync.

## Deploy to GitHub Pages

Upload `index.html` to a public `orbit-tracker` repository. In Settings → Pages choose main / root. Open the published HTTPS URL.

## Supabase Auth URL configuration

In Supabase Dashboard → Authentication → URL Configuration, set **Site URL** to your GitHub Pages URL, e.g. `https://YOURNAME.github.io/orbit-tracker/`, and add the same under redirect URLs. This ensures signup confirmation links return to your app.

## Authentication

Choose Create an account, enter email/password. Confirm email if prompted. Return to Orbit and sign in. Same credentials on any device.

## Sync

Data is stored in the Supabase `orbit_cloud_state` table protected by RLS. Orbit saves edits after about half a second. Upon opening or switching back to the tab, it reloads cloud records. Keep one tab/device actively editing at a time; simultaneous edits may overwrite one another (last-write-wins).

Older V11 browser records can be explicitly imported under Settings → Import older V11 browser records if they exist on that browser. Export JSON backup regularly.

This app requires Internet connectivity for initial authentication and syncing. Do not add private API keys to client code. The included `sb_publishable_` key is intended for public browser usage with RLS.
