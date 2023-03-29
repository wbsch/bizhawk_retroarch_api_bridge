## Make BizHawk pretend to be RetroArch('s UDP command API)

This Lua script makes the [BizHawk emulator](https://github.com/TASEmulators/BizHawk) pretend to be [RetroArch](https://github.com/libretro/RetroArch), at least as far as its UDP command API is concerned.

It was initially written for the [Archipelago Multi-Game Randomizer](https://github.com/ArchipelagoMW/Archipelago)'s LADX client, which only worked with RetroArch until this script was released.

Only the parts relevant for Archipelago's LADX client (and, since both share code, the [LADXR Magpie Tracker](https://github.com/kbranch/Magpie)) were implemented, namely:

 - VERSION
 - GET_STATUS
 - READ_CORE_MEMORY
 - WRITE_CORE_MEMORY

Additionally, GET_STATUS was only implemented for GB(C) cores.

No testing has been done on cores other than Gambatte and SameBoy. If you do test other cores, and especially other systems, feel free to adjust this info.

If you need more functionality than this, it should be fairly easy to add it. Pull requests are welcome as long as the main functionality is preserved.

### Usage

[Download](https://github.com/wbsch/bizhawk_retroarch_api_bridge/releases) a release `.zip`, unpack it, and load the `retroarch_api_faker.lua` in BizHawk:

```
"Tools" -> "Lua Console" -> "Script" -> "Open Script" -> "retroarch_api_faker.lua"
```

### Dev Dependencies

This script has only been tested with the LuaSocket version coming with Archipelago's other Lua scripts, which is version 1.22 from 2005. Since there was a 12 year hiatus for LuaSocket development, this is not as bad as it sounds.

The LuaSocket version is bundled in the release `.zip` file.
