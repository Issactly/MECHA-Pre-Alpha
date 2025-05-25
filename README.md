# M.E.C.H.A. Pre-Alpha
Two months(ish) to make my final project and prove I can learn on my own.

# Game Concept
You play as an android in the H sector, working to infiltrate facilities and steal critical data. Play in teams of 10 and beat the clock solving puzzles, fighting enemies and finding secrets along the way. Or go rouge and battle against homebase while they play clean up. **Welcome to the Dome.**


## Update 05/25/2025 (01:57):
**PC:**
Players have no walking animations, cant sprint or crouch. client > server > client file is untouched but everything else is scrapped. I found an easier way to achieve shift lock rather than setting `AutoRotation = false` everytime `C` was held. It was causing issues because the camera could still orbit. Thanks a lot Roblox for depreciating dev controls over shift lock >:[ Anyways, it's done and now I can move over the old animation lines to this new one with SOOO much less `if` `elseif` `else` statements that were just hurting my head lmao.

Sameday sub-updates:
- Up next: Setting Crouch to `ctrl` and creating a sliding mechanic
- Empty
- Empty




## Update 05/24/2025:
**PC:**
Players can walk, sprint w/Lshift, crouch w/C and see what direction other players are looking to. Walk speeds change accordingly and jump is disabled while crouching. Accidentally made the crouch good(???) You can _tap_ C to crouch, then any other movement key input will make the character stand or you can *hold* to stay crouched no matter the other movement key inputs.

Sameday sub-updates:
- yeah so about that tap to crouch,,, its pretty much a bug. Theres been an update to make it less in the way but after crouching and walking youll keep the crouched down pose. Thankfully that out of the way update fixed the speed so youll move as intended! Its a visual bug of sorts haha
- Camera now has a shorter Max zoom out. Invisicam is enabled to prevent any weird angles (hopefully) Camera movement with crouch is being considered but I may have to rebuild the Head and Neck stuff for it to not break :']
- Up next: Slide mechanic

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
