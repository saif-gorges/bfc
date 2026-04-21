# Image Guide — Saving Images from Your Current Site

Your images live on GoDaddy's CDN (`img1.wsimg.com`). Once your GoDaddy plan
expires, those image URLs die — so you need to save every image you want to
keep **before the renewal lapses**. This guide lists every image slot the new
site uses, and what to name each file when you save it.

## The Fast Way to Grab Images

1. Go to `https://babyfightclub.org` in Chrome, Safari, or Firefox (while it's still live).
2. On every page, **right-click each image → "Save Image As..."**
3. Save them all into the `images/` folder of the new site, using the filenames below.
4. On a Mac, you can also open Safari → **File → Save As... → Page Source → Web Archive**, which saves every image from a page at once.
5. Power-user shortcut: Chrome DevTools → Network tab → reload page → filter by "Img" → right-click each → Save.

After you drop images in, open each HTML file and replace the placeholder blocks (there's only one: the scoreboard page) and optionally add hero images where you'd like them.

---

## Images to Save

### Home Page (`index.html`)
| Save as | Where on the old site |
|---|---|
| `images/hero.jpg` | The main hero image at the top of the home page ("Screenshot 2025-03-04 at 1.31.22 PM.png" in the source) |
| `images/how-1.jpg` | "Pick your Baby" tile image |
| `images/how-2.jpg` | "Vote for your Baby" tile image |
| `images/how-3.jpg` | "Watch your Baby dominate" tile image |

*Note: The new home page doesn't use these images in the current layout (the
typography does the heavy lifting). Save them anyway — you may want to add them
back, and the source site is your only copy.*

### 2024 Tour (`2024-tour.html`)
| Save as | Where on the old site |
|---|---|
| `images/2024-lakes-of-fire.jpg` | Lakes of Fire event photo |
| `images/2024-sideburn.jpg` | SideBurn event photo |

### 2023 Tour (`2023-tour.html`)
| Save as | Where on the old site |
|---|---|
| `images/2023-nuit-noir.jpg` | Nuit Noir event photo |
| `images/2023-lakes-of-fire.jpg` | Lakes of Fire event photo |
| `images/2023-sideburn.jpg` | SideBurn event photo |

### 2022 Tour (`2022-tour.html`)
| Save as | Where on the old site |
|---|---|
| `images/2022-burning-man.jpg` | Burning Man event photo |
| `images/2022-denim.jpg` | Denim Entertainment party photo |
| `images/2022-electric-eclectics.jpg` | Electric Eclectics festival photo |
| `images/2022-soundbanks.jpg` | SoundBanks 7 photo |
| `images/2022-promise-cherry.jpg` | Promise Cherry Beach photo |

### 2021 Tour (`2021-tour.html`)
| Save as | Where on the old site |
|---|---|
| `images/2021-harvest.jpg` | Harvest Music Festival photo |
| `images/2021-promise-elsewhere.jpg` | Promise Elsewhere photo |
| `images/2021-soundbanks.jpg` | SoundBanks 5 photo |

### 2023 Scoreboard (`2023-scoreboard.html`) — **REQUIRED**
| Save as | Where on the old site |
|---|---|
| `images/scoreboard-2023.png` | The main scoreboard/bracket image on the 2023 Scoreboard page |

This one's required — the scoreboard page has a visible placeholder until
you drop this in.

### Logo / Favicon
| File | Status |
|---|---|
| `images/logo.png` | ✅ **Already included** — main hero logo (transparent PNG) |
| `images/logo-mark.png` | ✅ **Already included** — small nav version |
| `favicon.png` | ✅ **Already included** — browser tab icon |

If you want a proper multi-resolution `favicon.ico`, generate one from `favicon.png` at [realfavicongenerator.net](https://realfavicongenerator.net).

---

## Swapping Placeholder Images Into the HTML

Once you have images saved, here's how to add one into a page. Open the HTML file in any text editor and find a spot where you want an image. Add this line:

```html
<img src="images/2023-nuit-noir.jpg" alt="Nuit Noir event photo" style="width: 100%; max-width: 600px; margin: 1rem 0; border: 3px solid var(--ink);">
```

For the scoreboard page specifically, open `2023-scoreboard.html`, find this block:

```html
<div class="placeholder" id="scoreboard-image">
  [ SCOREBOARD IMAGE GOES HERE ...
</div>
```

And replace the whole `<div class="placeholder">` with:

```html
<img src="images/scoreboard-2023.png" alt="BFC 2023 Tournament Scoreboard" style="width: 100%; border: 2px solid var(--ink);">
```

---

## PayPal Donate Link

On the old site, the donate button was a PayPal-hosted button. I couldn't
extract the actual donation URL — you'll need to get yours from PayPal and
paste it into `child-support.html`. Look for this line:

```html
<a class="btn btn-hot" href="https://www.paypal.com/donate" ...
```

Replace `https://www.paypal.com/donate` with either:
- Your PayPal donation button URL (from PayPal → Pay & Get Paid → Donations), or
- A `https://paypal.me/yourhandle` link, or
- Your Stripe donation page, etc.
