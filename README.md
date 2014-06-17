HL2-mod-fixes
=============

A compilation of contributed fixes for Half-Life 2 / EP1 / EP2 mods that were broken by SteamPipe updates.

References
----------

Steam community fixes thread: http://steamcommunity.com/app/420/discussions/0/864971765497379056
Older Steam forums thread with many more fixes: http://forums.steampowered.com/forums/showthread.php?t=1289845

Half-Life 2 mods
----------------

Most HL2 mods can be fixed by modifying the FileSystem block in the gameinfo.txt file with this:

```
	FileSystem
	{
		SteamAppId 220

		SearchPaths
		{
			game+mod	|gameinfo_path|.
			platform	|gameinfo_path|.

			game_lv		hl2/hl2_lv.vpk
			game+mod	hl2/hl2_sound_vo_english.vpk
			game+mod	hl2/hl2_pak.vpk
			game		|all_source_engine_paths|hl2/hl2_textures.vpk
			game		|all_source_engine_paths|hl2/hl2_sound_misc.vpk
			game		|all_source_engine_paths|hl2/hl2_misc.vpk
			platform	|all_source_engine_paths|platform/platform_misc.vpk

			mod+mod_write+default_write_path	|gameinfo_path|.
			game+game_write	|gameinfo_path|.
			gamebin		hl2/bin

			game		|all_source_engine_paths|hl2
			platform	|all_source_engine_paths|platform
		}
	}
}
```

Working mods
------------

In my experience, the following mods work fine without modification:

- Riot Act (July 2007) - http://www.moddb.com/mods/riot-act
