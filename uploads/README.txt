LUMI — INTERACTIVE COLORING BOOK — EMBEDDING INSTRUCTIONS
===========================================================

WHAT'S IN THIS FOLDER
----------------------
index.html              – the flipbook itself, now with drawing tools
page-flip.browser.js    – page-turn engine (local file, no internet/CDN needed)
pages/page-01.jpg ...   – the 28 pages (front cover, inside-front cover, 24
                          colorable inside pages, inside-back cover, back
                          cover), in reading order

HOW TO PUBLISH IT
------------------
1. Upload the ENTIRE folder (keep index.html, page-flip.browser.js and the
   pages/ folder together, same relative paths) to your web host —
   e.g. yoursite.com/lumi/

2. Embed it on the page with an iframe:

   <iframe
     src="https://yoursite.com/lumi/index.html"
     style="width:100%; max-width:900px; height:650px; border:0; background:transparent;"
     allowtransparency="true"
     title="Lumi coloring book">
   </iframe>

   Adjust height/width to taste — the book itself resizes responsively inside
   the iframe, and the space around it stays fully transparent so it blends
   into the page background.

   Works both hosted online and opened directly as a local file
   (double-click index.html) — no server required.

COLORING FEATURE
------------------
The 24 inside pages (front/back covers excluded) are colorable:
  - Pencil and Brush tools, toggled from the toolbar at the top
  - A color palette plus a custom color picker
  - Undo button
  - Drawing is limited to the printed page area (won't go onto the
    outer margins), and a stroke drawn across the spine flows smoothly
    from the left page onto the right one
  - Nothing is saved or downloadable — coloring only lasts for the
    current visit; refreshing the page resets it

NAVIGATION
------------
Pages turn only via the on-screen arrows or the keyboard's left/right
arrow keys. Click-and-drag / swipe-to-turn was intentionally turned off,
since it conflicted with drawing on the page.

COPY PROTECTION — WHAT'S INCLUDED AND ITS LIMITS
--------------------------------------------------
Included deterrents:
  - Right-click / context menu disabled
  - Image dragging and text selection disabled
  - Common shortcuts blocked (F12, Ctrl+Shift+I/J/C, Ctrl+U, Ctrl+S)
  - Non-colorable pages (covers) are rendered as CSS backgrounds rather
    than plain <img> tags, which stops the simplest "save image as"
    attempts

Please note honestly: no front-end technique can make images on a web page
100% impossible to copy — anyone can still take a screenshot, or a
technically determined visitor can find the files via browser dev tools.
These measures raise the bar for casual copying/downloading; they are not
a substitute for watermarking or DRM if that level of protection is needed.

CHANGING PAGES LATER
----------------------
If a page needs to be swapped or the order changed, replace the matching
pages/page-NN.jpg file (keep the same file name/number) or send me the
updated PDF and I'll regenerate the set.
