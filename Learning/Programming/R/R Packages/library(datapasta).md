---
tags: wip, R
---
Link: 

clipr::write_clip()


https://rdrr.io/cran/datapasta/f/README.md

Getting data into source

tribble_paste which pastes a table as a nicely formatted call to tibble::tribble()

    Recommend Ctrl + Shift + t as shortcut.
    Table can be delimited with tab, comma, pipe or semicolon.

Massaging data in source

There are two Addins that can help with creating and aligning data in your editor:

    Fiddle Selection will perform magic on a selection. It can be used to:
        Turn raw data delimited by any combination of commas, spaces, and newlines into a c() expression
        Pivot a c() expr between horizontal and vertical layout.
        Reflow messy tribble() and data.frame() exprs.
        Recommend Ctrl +Shift + f as shortcut.

    Toggle Vector Quotes will toggle a c() expr between all elements wrapped in "" and all bare unquoted form. Handy in combination with above to save mucho keystrokes.
        Recommend Ctrl +Shift + q as shortcut.

Getting Data out of an R session

There are two R functions available that accept R objects and output formatted text for pasting to a reprex or other application:

    dpasta accepts tibbles, data.frames, and vectors. Data is output in a format that matches in input class. Formatted text is pasted at the cursor.

    dmdclip accepts the same inputs as dpasta but inserts the formatted text onto the clipboard, preceded by 4 spaces so that is can be as pasted as a preformatted block to Github, Stackoverflow etc.
