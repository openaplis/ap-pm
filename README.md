# Slide Tracking: 2D Barcode Implementation
The current workflow prior to microtome is for slides to be pre-printed with a paper label that contains identifying, human readable information.  These slide labels are currently printed by viewing a log extracted from Sunquest and (**I'm a bit fuzzy on this process***).  Slide labels are printed on a Zebra label printer and do not contain a 2D barcode, but chemical resistant paper is used.

Proposed evolution of slide label printing:
1. Include a 2D barcode on the slide label along with appropriate human readable identifying information.
2. Use the Leica Slide Printers to print direct to slides
3. 2D barcode will represent an ID that is extracted from the Sunquest Sybase database via a MYSQL database
4. 2D barcode will be used in subsequent project track slides.
5. A list of slides that have been created in Sunquest can be viewed and subsequently printed.

Note: Preprinting slide is not the best practice.  The goal would be to work toward printing slides at microtome as cases are cut.
