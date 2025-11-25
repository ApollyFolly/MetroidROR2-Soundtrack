This is a modified version of the original mod for OriginalSoundTrack by Kyle (https://thunderstore.io/package/Kyle/OriginalSoundTrack/)

I just trimmed down, added my own music files aswell as adding new ID's that were not in the original mod document

Includes music from Prime 1, 2, 3, 4, Pinball, Dread, Other M, AM2R, Fan Made Super Metroid renditions, and more.

#Manual Download

Just drag and drop into BepinEx plugins folder, the path should look something like this. (SteamLibrary\steamapps\common\Risk of Rain 2\BepInEx\plugins)

##Making Your Own Version

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

(As of the Alloyed Collective update)
```

Non Level ID's     Description
===============================================
splash         -   ("Hopoo Games" Logo)

loadingbasic   -   (Loading Bar)

intro          -   (Intro Cutscene)

outro          -   (Outro Cutscene/Credits)

title          -   (The Title Screen)

lobby          -   (The Select Character Screen)

logbook        -   (View Logs Screen)

crystalworld   -   (Prismatic Trials Menu)

eclipseworld   -   (Eclipse Menu)

infinitetowerworld - (Simulacrum Menu)


Level ID's         Level Name / Description
===============================================

Base Game ID's
===============================================

            -Level 1 Variants-
blackbeach     -   Distant Roost (Flying Creatures Cliffs Level 1)
+ blackbeach2

golemplains    -   Titanic Plains (Grassy Level 1)
+ golemplains2

lakes  -   Verdant Falls (Big flower Level 1)
+lakesnight

            -Level 2 Variants-
foggyswamp     -   Wetland Aspect (Swamp Level)

goolake        -   Abandoned Aqueduct (Tar Desert Level)

            -Level 3 Variants-
frozenwall     -   Rallypoint Delta (Snow Level w/ The Caves)

wispgraveyard  -   Scorched Acres (Circle platforms Level)

            -Level 4 Variants-
dampcavesimple -   Abyssal Depths (Hell Level) 
+ dampcave

shipgraveyard  -   Siren's Call (Eggs Level)

rootjungle     -   Sundered Grove (Big Tree Level w/ Mushroom Launch Pads)

            -Level 5 Variants-
skymeadow      -   Sky Meadow (Guitar solo Level) 

                 -Final-
moon2          -   Commencement (Final Level)


Survivors Of The Void ID's
===============================================

            -First Level-
snowyforest    -   Siphoned Forest (Snowy level 1)

            -Second Level-
ancientloft    -   Aphelian Sanctuary (Big cube pillar level) 

            -Third Level-
sulfurpools    -   Sulfur Pools (Green bubble level) 

            -Simulacrum Variants-
itancientloft  -   Simulacrum version of stage

itdampcave     -   Simulacrum version of stage 

itfrozenwall   -   Simulacrum version of stage

itgolemplains  -   Simulacrum version of stage

itgoolake      -   Simulacrum version of stage

itmoon         -   Simulacrum version of stage

itskymeadow    -   Simulacrum version of stage

                 -Final-
voidstage      -   Sotv DLC Boss stage 

voidraid       -   Sotv DLC Boss arena 

Seekers Of The Storm ID's
===============================================

            -Level 1 Variants-
village        -   Shattered Abodes (Big circle first level)
+villagenight

            -Level 2 Variant-
lemuriantemple -   Reformed Alter (Path of the Colossus first level)

            -Level 3 Variants-
habitat        -   Treeborn Colony (Path of the Colossus second level)
+habitatfall
            -Level 5 Variant-
helminthroost  -   Helminth Hatchery (Hell but with paths)

                 -Final-
meridian       -   Prime Meridian (False Sun boss level)

Alloyed Collective ID's
===============================================

            -Level 2 Variants-
nest?           -   Pretender's Precipice (Snowy with robo corpse)

conduitcanyon  -   Conduit Canyon (Decompile Level 1)

            -Level 3 Variants-
ironalluvium   -   Iron Alluvium (Big drill in the desert)
+

solutionalhaunt -   Solutional Haunt (Decompile Level 2)

            -Level 4 Variants-
repurposedcrater -   Repurposed Crater (Crater with big arch)

computationalexchange -   Computational Exchange (Decompile Level 3)

              -Final-
solusweb?      -   Neural Sanctum (Decompile Boss)

Misc ID's
===============================================
bazaar         -   Bazaar Between Time (The Shop)

artifactworld  -   Bulwark's Ambry (Area Where You Unlock Artifacts.) 

arena          -   Void Fields (The Area Where You Unlock Acrid.) 

mysteryspace   -   A Moment, Fractured (The Place Where You Can Obliterate Yourself.) 

limbo          -   A Moment, Whole (The Mega Scavenger Boss) 

goldshores     -   Glided Coast (Golden Stone Titan Boss Arena)

##Other Info

This plugin uses NAudio.dll https://github.com/naudio/NAudio to help load and play music at runtime. 
This is done to make it very easy for players to supply their own music. 
The downside is that the normal in game music isn't disabled.
This plugin sets your in game music volume setting to 0. 