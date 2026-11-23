# SeaBubbles Hawaii — Reflection draft

Prepared from the measured local tests. Review these explanations and practice the changes before submitting.

## Alignment

The header uses a row direction. `justify-content: space-between` spreads the brand and navigation along that row. `align-items: center` centers them across the other axis, which is vertical here. The navigation has its own flex container because its links are not direct children of the header.

## Starting size and final size

`flex-basis` is a starting size, not a guarantee of the final width. At 768 CSS pixels, the course grid measured about 691.22 pixels. A 40% basis gives a card about 276.49 pixels. With `flex-grow: 1`, two cards each became about 335.61 pixels wide after sharing the spare space and leaving the 20-pixel gap. `flex-shrink: 1` allows shrinking if space is tight.

## Two tested experiments

1. At 768 pixels, changing card growth from `1` to `0` reduced each card from about 335.61 to 276.48 pixels. Two cards still fit, but spare space remained at the end of the row. The finished page keeps growth at `1`.
2. At 992 pixels, changing the header from `space-between` to `center` moved the brand's left edge from about 49.59 to 248.42 pixels. The two groups moved together toward the middle instead of occupying opposite ends. The finished page keeps `space-between`.

The experiments were made in separate local copies, so experimental declarations are not in the finished stylesheet.

## One corrected bug

Without responsive sizing, the supplied hero image stayed 643 pixels wide in a 375-pixel document, producing horizontal overflow. Adding `width: 100%` and `height: auto` made it 375 pixels wide while keeping its proportions. The corrected document had no horizontal overflow.

## Breakpoints and checks

The base rule uses a 100% basis: one card per row. At 768 pixels, a 40% basis makes two columns. At 992 pixels, the later 20% rule makes four columns. The gaps still need room; using 25% for four cards would leave no room for three gaps.

Measured results: 375, 576, and 767 pixels showed one card per row; 768 and 991 showed two; 992 and 1200 showed four. There was no horizontal overflow at these widths, images kept their proportions, and action-link bottoms aligned within each row. Screenshots are included at 576, 768, and 992 pixels.

Tests used same-origin, fixed-width browser frames because the browser viewport override did not change the measured document width. Each frame's document width was checked, rather than assuming the requested size applied.

Navigation anchors, the classroom PDF link, loaded icons, and keyboard focus were checked. The PDF opened as “SeaBubbles Hawaii | Read Between the Tides.” The icon stylesheet is the instructor-specified Font Awesome CDN and requires an Internet connection.

## Submission status

Local work only. Nothing was submitted to Canvas or pushed to GitHub. The personal GitHub fork and final push remain for the release/submission step.
