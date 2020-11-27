# TabletopGameVersion 2:
Quality of life features discovered in version 1. I suspect it'll be things like deck searching and ordering, distrubuting a certain number of cards or pieces to specific players, snapping to grid, saving games, etc.

Version 3:
Multiplayer. Game area replaced by users' phones. This is likely mandatory due to 10 touch input limit on a single touch screen.

TODO:
Spacedesk almost works. Lots of window sizing problems.
-Chrome cannot be larger than the monitor span. So pushing the taskbar out of the way causes desktop to be shown on the third monitor
-The corner of a window has to be in the leftmost monitor. So stacking three monitors on top of each other does not work.
If number of monitors can be detected (or just manually enter how many players) then increase card size when put in players hand. Then decrease size when sent to table. Also change play area based on this.
Make menu drag and droppable again
Pinch to zoom options (Keep all resize and rotate options in menu. Add option to enable pinch to zoom. Add option to enable free rotation. Would also need option to reset size and position)
Segment out menu a little more. Section off one time setup stuff to submenu.
Lock angle of options to angle of object (upsidedown for player 2). Actually that's probably bad for things like the chance card. May actually lock it to which side of the board the menu was opened on. Or better yet make a customizable rectangle that depicts specific player areas and common area. There's a lot of tertiary stuff too like viewing deck will display upsidedown.
Hidden divider (send to table button). Actually I'm thinking the physical barrier will have a notch in it (like hook shape) to slide your finger under
Add gifs as options for pieces
Make view deck have top card on top or somehow indicate which is top and bottom

Future TODO:
Save game requires putting sprite images in storage or online https://www.scirra.com/store/royalty-free-game-templates/my-image-upload-4355
Might cause a bug. "DeckSprite.ActiveCard" might as well be a random animation frame. I don't think it's necessarily greater than CardBack.ActiveCard in all instances. If there's anywhere a condition is "DeckSprite.ActiveCard >= CardBack.ActiveCard" it might break with enough deck play

bugs:
The save function (or at least how it is implemented) draws too much memory and crashes chrome
Fix 1308 frame being default card back. Need to make it unique to the deck in case cardback changes.
fix send to bottom of deck
-had all the power grid cards in one deck. Dealt 3-15. Sent big one to bottom of deck. Next card drawn was the previous card drawn for some reason. Am not able to recreate the issue.
Bug: infinite resource doesn't work.
It seems like it's only when it's the first deck made?
1. Made $1 deck
2. set card back to $1
3. Dealt, maybe set deal location, toggle infinite resource
4. the action seems to fire i.e. it sets active card to 0 but the conditional "?" is false I guess for some reason?
5. It seems like the second deck made works properly for infinite resources
