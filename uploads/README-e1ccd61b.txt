PREVIEW BOOK — EMBEDDING INSTRUCTIONS
======================================

WHAT'S IN THIS FOLDER
----------------------
index.html              – the flipbook itself
page-flip.browser.js    – page-turn engine (local file, no internet/CDN needed)
pages/page-01.jpg ...    – the 28 pages (front cover, inside-front cover, 24 inside
                           pages, inside-back cover, back cover), in reading order

HOW TO PUBLISH IT
------------------
1. Upload the ENTIRE "site" folder (keep index.html, page-flip.browser.js and
   the pages/ folder together, same relative paths) to your web host —
   e.g. yoursite.com/catalog/

2. Embed it on the page with an iframe:

   <iframe
     src="https://yoursite.com/catalog/index.html"
     style="width:100%; max-width:900px; height:650px; border:0; background:transparent;"
     allowtransparency="true"
     title="Book preview">
   </iframe>

   Adjust height/width to taste — the book itself resizes responsively inside
   the iframe, and the space around the book stays fully transparent so it
   blends into the page background.

BACKGROUND
----------
The area around the book is transparent by design (html/body background is
set to "transparent"). The pages/covers themselves keep their own white/
printed background, as expected for a paper book.

COPY PROTECTION — WHAT'S INCLUDED AND ITS LIMITS
--------------------------------------------------
Included deterrents:
  - Right-click / context menu disabled
  - Image dragging and text selection disabled
  - Common shortcuts blocked (F12, Ctrl+Shift+I/J/C, Ctrl+U, Ctrl+S)
  - Pages are rendered as CSS backgrounds rather than plain <img> tags,
    which stops the simplest "save image as" attempts

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
