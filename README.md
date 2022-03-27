This is a modified version of the original mod for OriginalSoundTrack by Kyle (https://thunderstore.io/package/Kyle/OriginalSoundTrack/)
I just trimmed down, and reformanted the document aswell as adding new ID's that were not in the original mod document*****

Put scene IDs in the "scenes" attribute to have audio play on that scene in settings.xml. 

The scenes attribute is comma separated. A scene only has to be "contained" in the real scene ID for it to match: ("golemplains" in the scene attr will match for the golemplains2 scene id.)

Example for playing MyFile.mp3 on the title screen and main menus:
```
<song
    name="MyFile.mp3"
    scenes="title,lobby,logbook,crystalworld,eclipseworld"
    boss="false"
    volume="1"
/>
```

Setting boss to "true" means that music can only play when the player activates the teleport on a level (or on the final boss fight). 

Otherwise music can only play elsewhere (non teleport events). 

"volume" is a decimal between 0 and 1.

It's ok to have multiple <song> definitions with the same name or scenes. The plugin will choose a song randomly among the matching songs.

The top level <volume> tag is the master volume for all this plugin's music. Again, a decimal between 0 and 1.

The top level <loop> tag determines if music should loop or pick another song (from matching songs) after a song ends.

The top level <music-path> tag specifies where the plugin should scan for music. It does not traverse down directories. 

The default path it scans for music is: Risk of Rain 2\BepInEx\plugins\OriginalSoundTrack

Scene IDs (level IDs).

(As of the Sotv update)
```

Non Level ID's     Description
===============================================
splash         -   ("Hopoo Games" Logo)

loadingbasic   -   (Loading Bar)

intro          -   (Intro Cutscene)

outro          -   (Outro Cutscene)

title          -   (The Title Screen)

lobby          -   (The Select Character Screen)

logbook        -   (View Logs Screen)

crystalworld   -   (Prismatic Trials Menu)

eclipseworld   -   (Eclipse Menu)

infinitetowerworld - (Simulacrum Menu)


Level ID's         Level Name / Description
===============================================
bazaar         -   Bazaar Between Time (The Shop)

blackbeach     -   Distant Roost (Flying Creatures Cliffs Level 1)
+ blackbeach2

golemplains    -   Titanic Plains (Grassy Level 1)
+ golemplains2

foggyswamp     -   Wetland Aspect (Swamp Level)

goolake        -   Abandoned Aqueduct (Tar Desert Level)

frozenwall     -   Rallypoint Delta (Snow Level w/ The Caves)

wispgraveyard  -   Scorched Acres (Circle platforms Level)

dampcavesimple -   Abyssal Depths (Hell Level) 
+ dampcave

shipgraveyard  -   Siren's Call (Eggs Level)

skymeadow      -   Sky Meadow (Guitar solo Level) 

moon2          -   Commencement (Final Level)

rootjungle     -   Sundered Grove (Big Tree Level w/ Mushroom Launch Pads)

Survivors Of The Void Id's
===============================================
snowyforest    -   Siphoned Forest (Snowy level 1)

ancientloft    -   Aphelian Sanctuary (Big cube pillar level) 

sulfurpools    -   Sulfur Pools (Green bubble level) 

itancientloft  -   Simulacrum version of stage

itdampcave     -   Simulacrum version of stage 

itfrozenwall   -   Simulacrum version of stage

itgolemplains  -   Simulacrum version of stage

itgoolake      -   Simulacrum version of stage

itmoon         -   Simulacrum version of stage

itskymeadow    -   Simulacrum version of stage

voidstage      -   Sotv DLC void stage 

voidraid       -   Sotv DLC Boss arena 

Misc Id's
===============================================
artifactworld  -   Bulwark's Ambry (Area Where You Unlock Artifacts.) 

arena          -   Void Fields (The Area Where You Unlock Acrid.) 

mysteryspace   -   A Moment, Fractured (The Place Where You Can Obliterate Yourself.) 

limbo          -   A Moment, Whole (The Mega Scavenger Boss) 

goldshores     -   Glided Coast (Golden Stone Titan Boss Arena)
```
##Other Info

This plugin uses NAudio.dll https://github.com/naudio/NAudio to help load and play music at runtime. 
This is done to make it very easy for players to supply their own music. 
The downside is that the normal in game music isn't disabled.
This plugin sets your in game music volume setting to 0. 
