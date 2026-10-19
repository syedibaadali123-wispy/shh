# Clarity Digital House website

A static website (plain HTML, CSS and JavaScript). No build step, no dependencies, no server needed.

## Run it
Double-click `index.html`, or serve the folder:

    python3 -m http.server 8000     # then open http://localhost:8000

## Pages
| File | Page |
|---|---|
| index.html | Home |
| creators.html | For Creators (video editing and website redesign) |
| authors.html | For Authors |
| about.html | About Us (with the contact form) |
| privacy.html | Privacy Policy |
| terms.html | Terms & Conditions |

## Things to change before launch
1. **Email address.** Replace `hello@claritydigitalhouse.com` in `assets/js/main.js` (`CONTACT_EMAIL`) and in `source/common.py`, then re-run the build (below). The contact form opens the visitor's email app with the message filled in; it does not need a backend.
2. **Photos.** Each page picture is a "slot". The site first looks for `assets/images/<slot>.jpg`, then falls back to a stock photo link, then to a neutral pixel pattern. To use your own photos, save files with these names in `assets/images/`:
   `home-hero`, `svc-author`, `svc-video`, `svc-web`, `authors-hero`, `authors-cover`, `creators-hero`, `creators-web`, `about-story` (all `.jpg`).
   Portrait photos (4:5) suit the `*-hero`, `authors-cover` and `about-story` slots; the `svc-*` slots are landscape (4:3).
3. **Legal pages.** The Privacy Policy and Terms are sensible starting drafts written from your service details. Have a lawyer review them, and complete the governing-law clause.

## Editing text
Page copy lives in `source/*.py`. After editing, run from this folder:

    python3 source/build.py

This regenerates the six `.html` files. (You can also edit the `.html` files directly.)

## Design tokens
Colors, fonts and spacing are CSS variables at the top of `assets/css/styles.css`.
Fonts (Oswald, Inter) are self-hosted in `assets/fonts/` under the SIL Open Font License.
The green pixel band above the footer is rebuilt from the pixel strip you supplied (`assets/images/pixel-edge-reference.png`).
