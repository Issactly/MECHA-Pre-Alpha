# M.E.C.H.A. Pre-Alpha || 0.4.3
Two months(ish) to make my final project and prove I can learn on my own.

# Game Concept
You play as an android in the H sector, working to infiltrate facilities and steal critical data. Play in teams of 10 and beat the clock solving puzzles, fighting enemies and finding secrets along the way. **Welcome to the Dome.**

## Update 06/13/2025 (04:29):
**PC:**
We are back gun blazing baybee! No for reals I got 41 days to finish this and I know I could do it all in 2 weeks if I didn't stop for rests but lowkey not good (edited tmi out lmaoo) So whats new? (i say getting more unprofessional by the day) Well the pod is physically being built now. Some bugs it had are being fixed today as well before todays Geek Out. The second place where you actually play the game is being cleared as well to transfer a few scripts I worked on in the main world but dont need to keep there. There was a memory leak issue happening too which on a small scale isnt an issue but potetially duplicated with even 5 players, it could affect serverside performance greatly. (Unsure if I should be saying this haha, pls don't hack my game)

Up next:
- Debug pod completely for Geek Out
- Finish building hub, exclude character rooms bc i said so and like thats not functionally important
- Finish moving files to second place, finish the maths for attacks/dmg
- Create UI's for health, shield, general controls in game
- Stretch feature: Min Map :0 would totes be cool!

## Update 06/13/2025 (04:29):
**PC:**
HIII I feel like I got a LOT done this session. I may fall asleep writing this so please excuse the difference in commit times <3 My biggest issue aside from the character selector was not being able to move the camera from the center of the screen which was set with the `RunService.RenderStepped:Connect(function()` IN MY MIND it was the clamps but DUH the clamps are called by the funtion and because its using the `:Connect` to be rendered I could just `:Disconnect` via having the entire connect and function under a variable `cameraConnect`:
```Lua
if cameraConnection then
	
 	cameraConnection:Disconnect()
	cameraConnection = nil
end
```
Not gonna get into the whole reconnection cause its a lil self explanatory just know disconnecting does use a `:Destroy()` and you have to make sure you're always using clones!

- Player now has a general Instructional UI will be updated soon to always display only necessary info
- Player can enter and exit pod with correct camera positioning!!!
- Player now has min and max camera zoom values (considering setting a static distance) as well as an offset only visible when outside of various menus
- 

Up next:
- Theres a bug where hitting tab in a sub menu disables rotation too early so Ill get that fixed in the next patch
- General UI sometimes showing less or more info than needed
- Building the home area very simple tho as I wanna keep moving with the mechanics
- Hitting play will enter camera cutscene that makes the transition from menu to pod visually pleasing :] (plus get experience with more camera controls!

$${\color{lightblue}Dev \space Diary:}$$
I feel like I said a lot in the update chunk but whatevs. Again I think I moved pretty quick yesterday or at least it feels like a weight is off me since I figured out camera connections a function which I can connect to any part in a matter of seconds! Another thing I want to do is have a pause menu which means I need to figure out how to remove the default `Esc` to the platform menu and guide it to my own in game menu. I also need to add a part I believe to the player to use as the camera reference ORRRR I could probably have a pause part that moves to a specific distance away from the characters head `CFrame`? I dunno its something to look into. Once I move into the  main world Im unsure how to split it up... How do I move players together into specific servers? Each game mode I guess is a different place as to not cram servers? which hey, if i make the same maps but change the layouts i can then do a math.random for it to select which map instead of getting into the world of map generation. I guess you pick a game mode and then get taken to the waiting area which would be the transport hub? you could walk around until the proper number of players join? Honestly a `wait()` could work to delay teleportation? but it wouldnt be affected by players joining or leaving... okay wait so home area right off main menu, from home area you can find the secret area, explore character rooms, in the future be able to decorate your own room. then from the terminal you'll be able to pick a mission. from home to mission you get taken to the transport area where you wait for players to join. transport is just the same building as home but outside the main doors. simillar to star wars rise of the resisitance ride's loading zone! once the players are selected a client side cutscene plays before teleporting the group to a random map. they play the map, get their XP and can play again or go home. That sounds pretty simple on paper! Obviously ill keep updating here and you'll see if its going great or if im on my 4th crashout of the day but hopefully things will keep going smoothly. byeeeeeeee.

## Update 06/11/2025 (20:38):
**PC:**
Wow its been a HOT minute. Okay today I was able to do the Pod UI and menus!
- Clicking play no longer teleports the player to the next place, instead the camera moves to `podCam.position` and maintains the minor movements that follow the mouse.
- The pod main menu has 4 buttons
  >Model
  
  >Mods
  
  >Gear
  
  >Stats
Each has its own sub menu, currently only Model is populated with buttons for the 3 models planned to be in the game.
- Pressing `tab` while in a sub menu returns the player to the main pod menu. Its planned pressing `tab` while in the main menu will let the player out of the pod and its UI
- A general and constant UI is planned for guidance, as well as a UI tutorial based on tester feedback
- Player can use the mouse scroll wheel to rotate the character model while customizing (push forwards to scroll right and pull backwards for left)

Up next:
- Figuiring out how to change the players model. (may have to import from blender or pull down from assets)
- General UI

$${\color{lightblue}Dev \space Diary:}$$
Im so tired ngl but I really wanna do this. Im going home so byeee

## Update 05/27/2025 (23:30):
**PC:**
Yay big update this time! The games start place is now just serving as a start menu (totally not because I couldnt figure out how to unlock the camera after closing the menu hahahahaha) I modeled a simple-ish background for the menu, and created 2 idle animations (impatient and swing) for the dummy that clones the characters appearance. The server size is currently set to 1, I will change this once I figure out how to set 1 player per spawn and then have the dummy clone the player closest to it :] The start menu has 3 buttons: 
- A play button that uses the teleport service to move the player to what will be the 'home'
- A credits button, when pressed changes the `Updates` scroll window to show everyone whos contributed to the game
- A quit button that uses the `kick()` function and remote event to disconnect the player

Up next:
- Transfering updates to game
- Building home set and menus
- Scripting parts like being able to open the computer, enter pod, open deco mode

$${\color{lightblue}Dev \space Diary:}$$
Some featres that would be nice, when the player hits esc, have it be the arm menu. camera rotates to front of character and the menu is on the right. the door in the home could open when the player is near enough. For the starter pod, cam should have bust view of character. Can edit colour, swap between models, decorate with stickers (stretch feature). Outside the pod at the computer can order mods and weapons. The wall terminal (stretch feature) has the option to open deco mode to decorate your room with collectibles you've gotten. UGHHHHGHHGKAJSNVA i cant believe i started this project lowkey couldve just gotten min wage at mcdonalds but noooo i wanna join in for capstoneee. I think I'm going to put way less effort in modeling the dorm THANK GOODNESS IM SMART ENOUGH TO KEEP THE LAYOUTS EXACTLY THE SAME FOR ALL OF EM. The only rooms that come with deco are the character rooms. I should be able to do this in like a week tops. I was persuaded to attend the class trip so i wont update tmmr unless i have energy after sixflags lmao. during the car ride im gonna do some concept art for the room because Ive only ever drawn one angle of it on the art of Mac on H1's counter and it shows in the modeling of the start menu LMAO. Anyways Im looking forward to starting the next area! I need to start researching player save data. I want to trrack stats later in the game and have a level system! but ofc thats allll stretch features

![What it looks like after hitting the credits button](ReadMeImages/CreditsEX.png)
What it looks like after hitting the credits button.


## Update 05/26/2025 (10:10):
**PC:**
Players can slide and the realistic things are implemented like you cant slide if youre crouching and cant crouch mid slide.

Sameday sub-updates:
- Began working on main menu, saved the code and layout elsewhere and redid with a semi-dynamic design
- Added rig that displays players avatar
- 

$${\color{lightblue}Dev \space Diary:}$$
Omg i pulled another all nighter lmao I said I would rest and animate and I did neither of those things


## Update 05/25/2025 (01:57):
**PC:**
Players have no walking animations, cant sprint or crouch. client > server > client file is untouched but everything else is scrapped. I found an easier way to achieve shift lock rather than setting `AutoRotation = false` everytime `C` was held. It was causing issues because the camera could still orbit. Thanks a lot Roblox for depreciating dev controls over shift lock >:[ Anyways, it's done and now I can move over the old animation lines to this new one with SOOO much less `if` `elseif` `else` statements that were just hurting my head lmao.

Sameday sub-updates:
- Players now have corresponding animations for crouching, forwards, backwards, left and right (although left and right is Larm up for Lwalk and Lleg out for Lrun and the corresponding for right BUT HEY im trying to get scripts done LOL we make it look pretty later :]) 
- The mechanics work for movement: walk/run forwards/backwards & walk/run left/right. Currently animations overtake one another as theres not been stricter priorities set (again cosmetics will be done later)
- HEAVILY simplified the movement. before it was something like `if IsRunning then RunTrack:Play()` then underneath in the actual button tracking mess `input.Keycode == Enum.Keycode.W then isRunning = true` blah blah blah hopefully you get it. _It was redundanttttt_ but now the button tracking immediately sets the animations and checks itself to now when I add _crouching_ will (hopefully) not have the same issue where you would tap to crouch but have to hold to get up (i do believe that was a `task.wait()` issue though)
- just threw in the crouching anims, it works perfectly (EXCEPT IT DOESNT) theres a visual/cosmetic bug: the head moves side to side for some reason? (i can totes fix it in 2 seconds but not now lol)
- (17:16) Proud to announce that movement is all set to build off of :] you can walk/sprint/crouch and theres only 1 visual bug with the head but ill fix that now before sliding since sliding also uses a cam following head mechanic
- (17:32) `HipHeight` used so now cam goes down when crouching! can now be adapted for sliding mechanic :D
- Up next: Creating a sliding mechanic

$${\color{lightblue}Dev \space Diary:}$$
I realize ive said `hopefully` like 10 times already, incluing the comments here to myself you can't see. Im gonna keep saying it lol its working!! i kinda spent 2 days learning the syntax i guess? and now ive spent one day implementing it and simplifying what i learned so im pretty sure thats a win. It is 04:11 buttttt something about worms right? I think as a treat ill spend today resting up and then animating because while tedious since im NOT PAYING 30$ (for a really nice in studio editing plugin >:'[ ) its still kinda fun and with my choppy style I lowkey dont need to put CRAZY effort and again its just going to be very simple until all the scripting is done :D An unfortunate thing is, this readme is not at all professional and if is this is to show how i am on projects _yeesh_ in the end Im unsure if this field is for me. I like to write how I think, be grammatically inccorect at 4am and write silly comments in my code. I don't think I'm very good at being serious nor do I really want to be! I know I'll find something right for me even if its not here :> for now all i need to do is make something that works, hits all the marks, and i enjoy. Wish me luck!


## Update 05/24/2025:
**PC:**
Players can walk, sprint w/Lshift, crouch w/C and see what direction other players are looking to. Walk speeds change accordingly and jump is disabled while crouching. Accidentally made the crouch good(???) You can _tap_ C to crouch, then any other movement key input will make the character stand or you can *hold* to stay crouched no matter the other movement key inputs.

Sameday sub-updates:
- yeah so about that tap to crouch,,, its pretty much a bug. Theres been an update to make it less in the way but after crouching and walking youll keep the crouched down pose. Thankfully that out of the way update fixed the speed so youll move as intended! Its a visual bug of sorts haha
- Camera now has a shorter Max zoom out. Invisicam is enabled to prevent any weird angles (hopefully) Camera movement with crouch is being considered but I may have to rebuild the Head and Neck stuff for it to not break :']
- Up next: Sliding mechanic

Due to Roblox's console guidelines I have to end console support. With the content my game will contain, it breaks the content agreement :[

[X] Blood or gore

[ ] Intense violence

[X] Strong language (Swearing)

[ ] Robux gambling

[ ] Drug reference or use

My game aims to have cutscenes that will have 'blood' in black but I don't wanna risk it ^^'
Support for Mobile is also temporarily suspended.

<!--**Console:**~~
Players can walk, sprint while holding ButtonL3, and see what direction other players are looking to. Walk speeds change accordingly

-Support for Mobile (hopefully) begins next week. While mobile players can join the game, their walk speed by default is less than crouch speed(?)(I honestly don't know why lmao)

Sameday sub-updates:
- The default walk speed had been set to 7. I mustve done that in the early AM cause I do not remember doing that! Glad I checked!-->


# Credits
_**Art**_

**- Animation -**
- [tatyb2016](https://github.com/Issactly)
	
**- Character Design -**
- [tatyb2016](https://github.com/Issactly)
- UltimateCollection42
	
**- Decals -**
- [LovelySkylar06](https://github.com/aaami988)
- [tatyb2016](https://github.com/Issactly)
	
**- Modeling -**
- [tatyb2016](https://github.com/Issactly)
	
**- World Building -**
- [LovelySkylar06](https://github.com/aaami988)
- [tatyb2016](https://github.com/Issactly)
- UltimateCollection42
	
_**Scripting**_
- [tatyb2016](https://github.com/Issactly)


_**Testers**_
- [airbomberofaqua](https://github.com/MarioACrespo)
- [rhyomai](https://github.com/KrisNoel23)
- Wheresthemilkat
- [Xenox5815](https://github.com/Ibra-Hud)
	
_**Special Thanks**_
- [benspector-mls](https://github.com/benspector-mls)
- [carmensalas14](https://github.com/carmensalas14)
- [Gonzalomarcylabschool](https://github.com/Gonzalomarcylabschool)
- iinar_2004
- Itzyogurldavita
- nightnolly23
- [pwacinqz](https://github.com/kurasmagnolia)
