# SeaBubbles Reflection — Draft to Review

## Alignment
`justify-content` spreads items along a row. The header uses `space-between` to put the name on one side and the navigation on the other. `align-items: center` lines them up vertically.

## Card size
`flex-basis` is the starting size. `flex-grow: 1` lets the cards share extra room. At 768 pixels, a card started at about 276 pixels and grew to about 336 pixels. The 20-pixel gap stayed between the cards.

## Two experiments
1. Changing `flex-grow` from `1` to `0` made the cards narrower and left unused space. The finished page uses `1`.
2. Changing the header's `justify-content` from `space-between` to `center` moved the name and navigation together toward the middle. The finished page uses `space-between`.

## A fixed problem
The turtle image was too wide on a phone-sized screen. At 375 pixels, the original image was 643 pixels wide. `width: 100%` made it fit, and `height: auto` kept it from stretching.

## Screen sizes
Below 768 pixels, each card takes a row. From 768 to 991 pixels, there are two cards per row. At 992 pixels and wider, there are four. The later media query replaces the earlier card width.

The page was checked at 375, 576, 767, 768, 991, 992, and 1200 pixels. The buttons lined up, the image kept its shape, and the page did not scroll sideways. The tests used fixed-width frames in Chrome. Screenshots at 576, 768, and 992 pixels are included. The navigation links and sample PDF also worked.
