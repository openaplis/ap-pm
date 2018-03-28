# Slide Tracking: Barcode Tracking Implementation
The current workflow prior to microtome is for slides to be pre-printed on a slide printer that contains identifying, human readable information.  These slides are currently printed by viewing and printing a report in Cerner CopathPlus.

Note: I am working on a process to have add-on Cytology/NONGYN slides printed on a Zebra Label printer.  Cytology/NONGYN slides are currently using preprinted slide labels and add-on slides are hand written.  This is a different project that is outside our scope for now, however, the report used to print to our slide printers and the zebra label printers are nearly identical.

Steps for Drew prior to implementation:
1. Keep current slide printing process as is, however, include scannable linear barcode on slides (I am close to being able to implement this).
2. Linear barcode will contain the following:  specimen_id, part_inst, stain_inst, level, this information is enough to uniquely identify every stain that is tracked within CoPathPlus, as well as the block it is tied to.  

*Note - this is a change after our discussion yesterday.  Using our current process, I should be able to include a linear barcode that includes this information, this would involve no workflow changes and allow us to start scanning slides.

*Current Challenges:  Having all of the necessary information included on a linear barcode that fits on a slide is a challenge.  Instead of using the specimen number formatted field, there is a specimen_id field that CoPath uses that contains a "mwd" prefix on every id.  My plan is to use this id and strip the prefix.  Also, I may be converting that id from deciman to hex to save room, so when scanned, there may be a hex to decimal conversion that happens to match the database fields.

Also - The CoPath database has slides tracked in p_stainprocess, however, when a stain has multiple levels, there is not a unique entry.  It tracks how many levels under slide count, but someone how if each individual slide would be scanned, we would need to account for multiple levels.

Once slides contain scannable barcode:
1. Import the data from Cerner CoPath from the p_stainprocess table, as well as related tables in a timely manner
2. Faciltate a way to scan the slide and lookup the value in CoPath
3. Once slide is scanned, information will need to be tracked in mysql database
4. Show this information in a meaningful way.


Note: Preprinting slide is not the best practice.  The goal would be to work toward printing slides at microtome as cases are cut.


