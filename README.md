TODO:
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

Tablet description: 
For players to have their own hands, tablets and phones can technically be used. 
To setup, download spacedesk on the PC as well as the tablets. Setup spacedesk settings to not autorotate and do use the android resolution settings.
From here you now have the tablets connected as touchscreen monitors. In Windows, go into display settings to arrange them as the players around the table. 
Now...things get sketchy from here. There's a lot of problems with this method due to how Windows 10 handles window resizing and touch screen interactions. 
1. The top left of a window cannot go beyond the topleftmost monitor. Especially in the Y axis. What this translates to is you can't really put a smaller screen directly above the big screen or else the game window will not be able to fill the left half of the game board. To solve this, the tablet screen _can_ be above the main board but it has to be left aligned with it. Tablets below the game board do not have this same issue. I haven't nailed down how this translates to tablets to the left of the game board. 
2. Disable pinch to zoom in chrome by adding --disable-pinch to the target path (will show full target path later) 
3. Hide all unnecessary stuff in chrome. Unfortunately Windows 10 doesn't allow you to make a window larger than the extreme dimensions of all the monitors combined. And you can't F11 maximize chrome across multiple monitors. What this means is if you want to drag the chrome window across all monitors, you'll be stuck with your URL bar and bookmarks and whatnot showing. The best way to get rid of this is with this full target path ""C:\Program Files\Google\Chrome\Application\chrome.exe" --disable-pinch --window-size=3840,5500 --window-position=0,-800  --app=http://localhost:50001/". That is setup for two tablets, one at the top and one at the bottom of the screen. That localhost might not work the first time, but start construct 2 once and then close whatever chrome opens, then open that target path again. Again, very sketch... 
That should be it. That target path will have to be manually changed based on the number of tablets. I tried playing around with every magnifier out there to help out with zooming in on the tablets but they all fell flat for one reason or another. The windows 10 mangifier "works" but in tablet mode it has these obnoxious bars. A million third party ones don't work because they don't handle tablet interactions correctly. The closest one was "WindowWatcher". I couldn't figure out a way to automatically resize the zoom window. Maybe it's possible, idk. The only reason I gave up is because it didn't touch and hold properly. I would have to recode my program to bring up the menu without touching and holding and it wasn't worth it. 
