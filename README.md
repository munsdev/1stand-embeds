# 1stand-embeds

Interactive embeds and datasets for 1STAND.org posts.
Served by GitHub Pages, pulled into Webflow with an iframe.

## Layout

One folder per project. Each `embed.html` is fully self-contained: no build
step, no external CSS or JS, no relative dependencies. It works at any URL.

    <project-slug>/embed.html      the interactive piece
    <project-slug>/*               datasets and reports published alongside

## Using one in a post

In the Webflow CMS, in Section 1 or Section 2, put the cursor on a blank line,
click the + button, choose Code block, and paste:

    <div style="width:100%;margin:0 0 .5rem;border:1px solid #02090a26;
         border-radius:4px;overflow:hidden;background:#F9FAFB">
      <iframe src="https://munsdev.github.io/1stand-embeds/<slug>/embed.html"
        style="display:block;width:100%;border:0;height:780px"
        title="Interactive map" loading="lazy" referrerpolicy="no-referrer"
        sandbox="allow-scripts allow-popups allow-popups-to-escape-sandbox"></iframe>
    </div>

Change the slug and the height. 780 suits a full map, 480 a chart.

## Projects

### tarrant-polling
Tarrant County, Texas cut its Election Day polling places from 316 to 223 for
the 3 November 2026 midterms. The widely reported figure of 92 is a net: 149
sites closed and 56 opened. Early voting went 50 to 47, and five of the
fourteen removals are college campuses.

Derived from four documents published by Tarrant County Elections. Sites
matched on ZIP plus house number plus street rather than on name, because 25
sites changed name without moving. 431 of 433 records geocoded, every point
checked against a Tarrant County bounding box.

Counts reconcile both ways: 167 kept + 149 closed = 316, and 167 + 56 = 223.

Files: `embed.html`, the full workbook, the closures CSV, the coordinates,
and a printable report.

## Privacy

The embeds load no third-party scripts. Leaflet and the typeface are inlined.
Map tiles are requested from OpenStreetMap, which receives the visitor's IP as
part of that request. Hosting is GitHub Pages.
