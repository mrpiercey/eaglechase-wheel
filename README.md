# The Ashland Eagle Chase 5K Wheel-O-Registration

Play it:

- https://mrpiercey.github.io/eaglechase-wheel/ (works right away)
- https://wheel.eaglechase5k.com (once the DNS record is in place, see below)

A rigged decision wheel for the Ashland Eagle Chase 5K. A CRT TV in the corner types out a question like "Should I register for the Ashland Eagle Chase 5K?", you pull the lever, and a giant Price-Is-Right-style drum of YES / NO panels rolls past you, ticking as each panel goes by, and stops on YES. Every time. A pop-up then sends you to [eaglechase5k.com](https://eaglechase5k.com) to register.

The drum is drawn at low resolution and upscaled with pixelated scaling for a 16-bit look, with the Eagle Chase eagles as sprites on the YES panels.

Open `index.html` in any browser. No build step, no dependencies. Works on phones too, where the lever becomes a big SPIN THE WHEEL button under the drum.

Ten questions rotate in random order. Press **Space** to pull the lever. Click anywhere off the TV pop-up (or press Escape) to load the next question and spin again.

Colors, lettering, and the eagle logo match the [Eagle Chase typing game](https://github.com/mrpiercey/eaglechasegame). Sounds are generated with the Web Audio API.

## Embed it

The page works inside an iframe and adapts to the frame's size. Small or short frames get a SPIN THE WHEEL button instead of the lever.

```html
<iframe src="https://mrpiercey.github.io/eaglechase-wheel/" width="960" height="540"
        style="border:0;max-width:100%" title="Eagle Chase 5K Wheel-O-Registration"></iframe>
```

## How it is published

The same code is pushed to two GitHub repos, each deployed to GitHub Pages by the workflow in `.github/workflows/pages.yml`:

- `mrpiercey/eaglechase-wheel` has no custom domain, so its github.io address plays directly.
- `mrpiercey/wheel-eaglechase5k` holds the custom domain `wheel.eaglechase5k.com`.

Both are remotes of this folder, so `git push` sends every change to both. The domain needs one DNS record at GoDaddy: `CNAME  wheel  mrpiercey.github.io`, the same setup as game.eaglechase5k.com.
