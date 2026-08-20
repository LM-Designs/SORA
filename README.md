# S°ORA Landing Page

This is the S°ORA restaurant website — a single static page (`index.html`) plus an `assets/` folder of images, icons, and menu PDFs. 

## Replacing a photo (no coding needed)

Every photo on the site lives in `assets/`, sorted by which section of the page it appears in. To swap one out, you don't need to touch any code — just replace the file on GitHub:

1. In the GitHub repo, open the folder for the photo you want to change (e.g. `assets/brunch/`).
2. Click **Add file → Upload files** (top right of the file list).
3. Drag in your new photo and **give it the exact same filename** as the one you're replacing (e.g. `brunch-2.jpg`) — same name, same extension.
4. GitHub will show "This will replace the existing file" — confirm it.
5. Scroll down and click **Commit changes**.
6. If the site is deployed (e.g. GitHub Pages), it updates automatically within a minute or two. If you're not sure how it's hosted, ask whoever set that up.

**One thing to know:** each photo fills a fixed-shape box on the page (the boxes crop to fill, they don't squish). A replacement photo with a similar aspect ratio (portrait vs. landscape, roughly matching width-to-height) will look best — a very differently-shaped photo will get cropped in unexpected places.

## Where each photo appears

| File | Shows up in |
|---|---|
| `assets/hero/hero.jpg` | The big arch-shaped photo at the top of the page |
| `assets/about/about-1.jpg` | About section — person holding two wine glasses |
| `assets/about/about-2.jpg` | About section — person reading the menu |
| `assets/about/about-3.jpg` | About section — the bar shelf |
| `assets/about/about-4.jpg` | About section — cocktail on a tray |
| `assets/about/about-5.jpg` | About section — restaurant interior through the arch |
| `assets/brunch/brunch-1.jpg` … `brunch-4.jpg` | The 4 brunch photos in the scrolling brunch gallery |
| `assets/aperitivo/aperitivo-1.jpg` … `aperitivo-4.jpg` | The 4 photos in the scrolling aperitivo gallery |
| `assets/menus/brunch.pdf`, `dinner.pdf`, `drinks.pdf` | The PDFs that open when someone clicks Brunch / Dinner / Drinks in the menu section |

`assets/brand/` holds the logo, line-art illustrations, and small decorative icons (not photos) — you generally won't need to touch these.

## Updating a menu PDF

Same process as photos: go to `assets/menus/`, **Add file → Upload files**, upload your new PDF with the exact same filename (`brunch.pdf`, `dinner.pdf`, or `drinks.pdf`), and commit.

## Editing text or contact details

Things like the address, phone number, opening hours, and body copy live directly in `index.html` rather than a separate file. Search for the text you want to change and edit it in place — or ask your developer to make the change if you're not comfortable editing HTML directly.
