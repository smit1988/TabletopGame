# TabletopGameVersion 2:
Quality of life features discovered in version 1. I suspect it'll be things like deck searching and ordering, distrubuting a certain number of cards or pieces to specific players, snapping to grid, saving games, etc.

Version 3:
Multiplayer. Game area replaced by users' phones. This is likely mandatory due to 10 touch input limit on a single touch screen.

TODO:
Check project properties for "fullscreen in browser", "sampling", and "downscaling"
Doubletap option to enlarge card
Segment out menu a little more. Section off one time setup stuff to submenu.
Give everyone their own deck/board upload buttons
Lock angle of options to angle of object (upsidedown for player 2). Though don't want it upside down if they uploaded it upside down...May actually lock it to which side of the board the menu was opened on
Hidden divider (send to table button)
Add ability to take cards out when viewing deck (maybe add them to hand or some card specific option)
Add gifs as options for pieces
Make view deck have top card on top or somehow indicate which is top and bottom

Future TODO:
Save game requires putting sprite images in storage or online https://www.scirra.com/store/royalty-free-game-templates/my-image-upload-4355

bugs:
The save function (or at least how it is implemented) draws too much memory and crashes chrome
Fix 1308 frame being default card back. Need to make it unique to the deck in case cardback changes.
