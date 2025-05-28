# M.E.C.H.A. Pre-Alpha
Two months(ish) to make my final project and prove I can learn on my own.

# Game Concept
You play as an android in the H sector, working to infiltrate facilities and steal critical data. Play in teams of 10 and beat the clock solving puzzles, fighting enemies and finding secrets along the way. Or go rouge and battle against homebase while they play clean up. **Welcome to the Dome.**


## Update 05/27/2025 (11:30):
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
## Scripts
- [Issactly](https://github.com/issactly)


## Art
- [aaami988](https://github.com/aaami988)
- [Issactly](https://github.com/issactly)

  
<!--## Voices-->

## Testers
**PC:** [aaami988](https://github.com/aaami988)

**Console:** [Ibra-Hud](https://github.com/Ibra-Hud), [KrisNoel23](https://github.com/KrisNoel23)

**Mobile:** ray666666
