# પીયૂષ સંગ નિખાર — Wedding Invitation Website

A single static page with no build step. The folder contains:

```
index.html        ← the whole website (design, text, animations)
images/
  groom.jpg       ← Piyush
  bride.jpg       ← Nikhar
  couple-1.jpg    ← seaside photo (gallery)
  couple-2.jpg    ← traditional photo (gallery)
  og.jpg          ← preview image shown when the link is shared on WhatsApp
music.mp3         ← (optional) your own song; if present it replaces the built-in tune
```

## Music
When the kankotri is opened, an original shehnai tune plays with tanpura and dholak (Raag Bhupali).
It is generated live by the page itself, so no music file is needed. The round 🎵 button turns it on and off.
To use a song you own instead, name the file `music.mp3` and put it next to `index.html`.

## Shree Ganesh image
The envelope page shows a public-domain Ravi Varma Press painting (c.1910) from Wikimedia Commons,
loaded from upload.wikimedia.org. To keep a copy inside your own site, save the image from
https://commons.wikimedia.org/wiki/File:Ganesh_himself_has_two_wives,_Riddhi_and_Siddhi,_as_in_this_domestic_pose_from_the_Ravi_Varma_Press,_c.1910.jpg
as `images/ganesh.jpg`. The page uses the local file automatically when it is there.
You can also put any other Ganesh picture at `images/ganesh.jpg`.

## Deploy on Vercel

### Option A: GitHub (easiest to update later)
1. Create a new repository on github.com, for example `piyush-weds-nikhar`.
2. Upload everything in this folder (`index.html` and the `images` folder) using "Add file → Upload files".
3. On vercel.com, click **Add New → Project**, then import that repository.
4. Framework preset: **Other**. Leave the build settings empty and click **Deploy**.
5. Your link will be `https://piyush-weds-nikhar.vercel.app`, or similar.

Any later change you upload to GitHub redeploys the site automatically.

### Option B: Vercel CLI (needs Node.js)
```
npm i -g vercel
cd piyush-weds-nikhar
vercel --prod
```

## After deploying
- **WhatsApp preview:** in `index.html`, the `og:image` line points to
  `https://piyush-weds-nikhar.vercel.app/images/og.jpg`. If your Vercel URL is different, change that line to match your URL.
- **Personalised links per guest:** add `?to=Name` to the end of the link, for example
  `https://piyush-weds-nikhar.vercel.app/?to=રમેશભાઈ`
  The envelope and the letter will then say "સ્નેહી શ્રી રમેશભાઈ". The plain link without `?to=` works for everyone.
- **Maps:** to point each venue at the exact pin, open the place in Google Maps, click Share, copy the link, and replace the `href` of the "દિશા મેળવો" button for that venue in `index.html`.
