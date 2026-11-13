# Third-party notices

For FMG Launcher 1.6.0 / FMG Client 1.7.0.

FMG Client works together with software and content made by other people. This file lists it, with
its authors, licences and sources. None of it is made by FMG-PLUGINS and none of it is covered by the
FMG Client License. Every component remains the property of its authors and is subject only to its
own licence. Nothing in the FMG Client License limits the rights those licences give you, and
nothing in it claims rights in these components for FMG-PLUGINS.

This file distinguishes three things, because they are legally different:

1. **Carried:** files that are inside the FMG Client installer or the FMG Launcher (sections 1 to 5).
2. **Downloaded for you:** files the launcher fetches from their author's own distribution channel
   (Modrinth) onto your PC. FMG Client does not hand out copies of them (section 6).
3. **Offered:** mods the launcher only suggests; nothing is downloaded unless you click (section 7).

## For rights holders

If you hold rights in something listed here, or believe FMG Client contains, downloads or displays
your work in a way your licence does not allow, write to **mgn.frd.nw@gmail.com** with the work
concerned. Justified requests are acted on without undue delay: the component is removed from the
next release, and earlier releases that carry it are withdrawn from the releases page.

Up to FMG Launcher 1.5.1 the installer carried the files of the mods in sections 6 and 7 itself.
Since FMG Launcher 1.6.0 it no longer does: none of those mods is inside the installer, the
launcher or the source archive.

## 1. Fabric API (carried in the installer)

| Component | Version | Made by | Licence | Source |
| --- | --- | --- | --- | --- |
| Fabric API | 0.161.0+26.2 | FabricMC | Apache-2.0 | https://github.com/FabricMC/fabric |

FMG Client needs Fabric API to start, so the installer carries the unchanged file as FabricMC
published it. The Apache License 2.0 permits this; its text is at
https://www.apache.org/licenses/LICENSE-2.0 and inside the .jar. For Minecraft 26.3 the launcher
downloads Fabric API 0.163.0+26.3 from Modrinth instead.

## 2. Fabric Loader's version file (carried in the installer)

The installer carries Fabric Loader's version file for Minecraft 26.2
(`fabric-loader-0.19.5-26.2.json`, exactly as https://meta.fabricmc.net serves it), so FMG Client
installs without Fabric's own installer. Fabric Loader is made by FabricMC under the **Apache-2.0**
licence (https://github.com/FabricMC/fabric-loader). The loader itself and its libraries are not
carried: the launcher downloads them from Fabric's official servers (for Minecraft 1.12.2 from
Legacy Fabric's, https://legacyfabric.net).

## 3. LZMA SDK (compiled into the launcher)

The FMG Launcher opens .7z mod archives for the S.T.A.L.K.E.R. 2 tab with the C decoder of the
**LZMA SDK** by Igor Pavlov (https://www.7-zip.org/sdk.html, version 25.01), which its author placed
in the **public domain**. Two small changes, both in 7zDec.c: PPMd-packed archives are read too,
and PPMd settings longer than 5 bytes are accepted (as 7-Zip itself does).

## 4. FFmpeg (carried in the installer)

Clips uses FFmpeg to record games and save clips as MP4, to trim them and for clip thumbnails. The
installer carries a small build made for FMG Client from the upstream sources - FFmpeg 8.1.2 with
x264 0.165.3223, nv-codec-headers 12.1.14.0, oneVPL 2023.3.0, libogg 1.3.5 and libvorbis 1.3.7 -
containing only what Clips and the launcher need (Ogg Vorbis is used to turn your own emote sounds
into the format Minecraft plays). It differs from upstream in four places: a version-information
resource; one log line in the screen capture (ddagrab) that says when its first frame was taken, to
line the picture up with the sound; a precise timer in the screen capture, so frames are taken at
even intervals; and one filter of our own, fmghdr (`vf_fmghdr.c`, published with the sources), that
turns an HDR desktop into normal colours for HDR clips. It is not packed or compressed.

- libogg and libvorbis: Copyright (c) Xiph.Org Foundation, **BSD-3-Clause**
  (https://xiph.org/downloads/). Their licence texts are part of the published sources.

- Licence: **GPL-2.0-or-later**. FFmpeg itself is LGPL-2.1-or-later, but this build includes
  libx264 (GPL-2.0-or-later), which makes the whole build GPL. nv-codec-headers and oneVPL are MIT.
  Full text: https://www.gnu.org/licenses/old-licenses/gpl-2.0.html
- Complete corresponding source code: the exact source archives, the patches and the build script
  (`installer/ffmpeg/build_ffmpeg.sh`) are published with every release that carries this build, as
  "FFmpeg sources (GPL).zip" at https://github.com/mgnfrdnw-code/FMG-Client/releases. Upstream:
  https://git.ffmpeg.org/ffmpeg.git, https://code.videolan.org/videolan/x264
- You may copy, modify and redistribute this FFmpeg build under the terms of the GPL. The FMG Client
  License does not restrict that. FFmpeg is a separate program (`ffmpeg.exe`) that the launcher
  starts; it is not linked into FMG Client.
- A copy of this notice, `FFMPEG-LICENSE.txt`, is installed next to `ffmpeg.exe`.
- FFmpeg comes with NO WARRANTY, to the extent permitted by law; see the GPL for details.

## 5. Microsoft WebView2 loader (carried in the installer)

The launcher shows Steam's store page and Nexus Mods inside its own window with Microsoft Edge
WebView2, which is part of Windows 10 and 11 (it is not carried). To reach it, the installer puts
Microsoft's `WebView2Loader.dll` (version 1.0.2957.106, signed by Microsoft) next to
`FMG Launcher.exe`. Without it the launcher opens those pages in your browser.

- `WebView2Loader.dll` - Copyright (C) Microsoft Corporation. All rights reserved. Redistributed
  under the licence of the Microsoft WebView2 SDK:

```
Redistribution and use in source and binary forms, with or without modification, are permitted
provided that the following conditions are met:

   * Redistributions of source code must retain the above copyright notice, this list of conditions
     and the following disclaimer.
   * Redistributions in binary form must reproduce the above copyright notice, this list of
     conditions and the following disclaimer in the documentation and/or other materials provided
     with the distribution.
   * The name of Microsoft Corporation, or the names of its contributors may not be used to endorse
     or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR
IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND
FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR
CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER
IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF
THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

- The pages shown belong to their sites (Valve's Steam store, Nexus Mods) and appear as those sites
  serve them. Signing in there happens on the sites' own pages; the launcher does not read what is
  typed into them. Their sign-ins are kept in `<game folder>\launcher\webview`, the launcher's own
  browser profile - delete that folder to sign out everywhere at once.

## 6. Mods the launcher downloads for you (not carried)

So that the game runs well out of the box, the launcher downloads the mods below from **Modrinth's
own servers** (cdn.modrinth.com) the first time a Minecraft version is started, and checks each file
against the exact version FMG Client was tested with. They are their authors' original, unchanged
files, published there by their authors, and they are used under their authors' licences. FMG Client
does not modify them and does not hand out copies of them. Each is a separate .jar in your `mods`
folder that you can remove, switch off or replace in the launcher's Add-Ons tab.

| Mod | Version (26.2 / 26.3) | Made by | Licence | Source | When |
| --- | --- | --- | --- | --- | --- |
| Sodium | 0.9.2+mc26.2 / 0.9.3-alpha.1+mc26.3 | JellySquid (CaffeineMC) | PolyForm Shield 1.0.0 | https://github.com/CaffeineMC/sodium | first start |
| Lithium | 0.25.3+mc26.2 / 0.26.2+mc26.3 | JellySquid, 2No2Name | LGPL-3.0-only | https://github.com/CaffeineMC/lithium-fabric | first start |
| FerriteCore | 9.0.0 | malte0811 | MIT | https://github.com/malte0811/FerriteCore | first start |
| EntityCulling | 1.11.2 / 1.11.3 | tr7zw | tr7zw Protective License (below) | https://github.com/tr7zw/EntityCulling | first start |
| Iris | 1.11.4+mc26.2 / 1.11.7+mc26.3 | coderbot, IMS212, Justsnoopy30, FoundationGames | LGPL-3.0-only | https://github.com/IrisShaders/Iris | when you first switch a shader on |
| e4mc | newest for your version | Skye | MIT | https://modrinth.com/mod/e4mc | when you first host a world |
| Fabric API (26.3 only) | 0.163.0+26.3 | FabricMC | Apache-2.0 | https://github.com/FabricMC/fabric | first start of 26.3 |

FMG Client is free and non-commercial: it is not sold, carries no advertising and earns nothing.
e4mc's relay (e4mc.link) carries the connection while you host a world.

## 7. Mods the launcher offers (nothing is downloaded unless you click)

The Add-Ons tab shows a "Recommended" list. Choosing "Install" there downloads the mod from
Modrinth's own servers, exactly as installing any other mod from the Add-Ons tab does, together with
the libraries its author declares as required. Nothing on this list is carried by the installer or
installed without your click.

| Mod | Made by | Licence | Source |
| --- | --- | --- | --- |
| BetterHurtCam | uku | MIT | https://github.com/uku3lig/betterhurtcam |
| BetterShields | uku | MPL-2.0 | https://github.com/uku3lig/bettershields |
| CookeyMod | RizeCookey | CC0-1.0 | https://github.com/rizecookey/CookeyMod |
| Inventory HUD+ | DmitryLovin | All Rights Reserved | https://modrinth.com/mod/inventory-hud-forge |
| Marlow's Crystal Optimizer | Bram, Marlow | MIT | https://github.com/Bram1903/MarlowsCrystalOptimizer |
| Mod Menu | Prospector, haykam821, gniftygnome, TerraformersMC | MIT | https://github.com/TerraformersMC/ModMenu |
| Shield Fixes | Walksy | MIT | https://github.com/Walksy/ShieldFixes |
| Shield Status | Walksy | MIT | https://github.com/Walksy/ShieldStatus |
| Simple Voice Chat | Max Henkel | All Rights Reserved | https://github.com/henkelmax/simple-voice-chat |
| TierTagger | uku, netiyiy (original creator) | MPL-2.0 | https://github.com/mctiers-dev/TierTagger |
| Toggle Toggle Sprint | celeste | zlib | https://codeberg.org/celestialfault/toggle-toggle-sprint |
| TotemCounter | uku | MIT | https://github.com/uku3lig/totemcounter |
| uku's Armor HUD | BerdinskiyBear, uku | MIT | https://github.com/uku3lig/armor-hud |
| Zoomify | isXander | LGPL-3.0-or-later | https://github.com/isXander/Zoomify |

Libraries these mods may bring along from Modrinth: Cloth Config (shedaniel, LGPL-3.0), Fabric
Language Kotlin (FabricMC, Apache-2.0), Placeholder API (Patbox, LGPL-3.0), ukulib (uku, MPL-2.0),
Walksy Lib (Walksy, MIT), YetAnotherConfigLib (isXander, LGPL-3.0-or-later).

"All Rights Reserved" means the author has not given anyone permission to pass on copies. FMG Client
does not pass on copies of these mods: the file you install comes from the author's own Modrinth
page. The same is true of every mod, modpack, pack and shader you install from the Add-Ons tab.

Where FMG Client's installer writes a settings file for one of the mods in sections 6 and 7 (only
if none exists yet), that settings file comes from FMG Client; the mod does not.

## 8. Sounds

- The sounds of emotes, of the launcher's backgrounds and of the games were made for FMG Client and
  are part of it, with the two exceptions below.
- **"FAH" and "TUNG TUNG" emotes:** these two emotes play short sound clips of widely shared
  internet memes (about 1 second and 10 seconds). They were supplied by the publisher of FMG Client;
  their original creators are not known to FMG-PLUGINS and no licence was obtained. They are kept as
  two separate files (`assets/fmgclient/sounds/emote/fah.ogg`, `tung_tung.ogg`) and are removed on
  request of a rights holder (see "For rights holders").
- A sound file a player places in the `emote-sounds` folder replaces an emote's sound on that
  player's own PC only. Such files are not part of FMG Client and are never transmitted.

## 9. Online data shown in the launcher and the game

- **Weather data by [Open-Meteo.com](https://open-meteo.com/)**, used under the Creative Commons
  Attribution 4.0 International licence (https://creativecommons.org/licenses/by/4.0/). The weather
  on the Play page's background (rain, snow, hail, fog, thunder, wind) is drawn from it, only when
  you set a town in Settings. Open-Meteo's free service is for non-commercial use; FMG Client is
  free and non-commercial.
- **Add-ons and modpacks on Modrinth:** the names, descriptions, pictures and numbers in the Add-Ons
  tab, its overview window and the game's Modrinth screens come from Modrinth
  (https://modrinth.com) and belong to their authors. They are shown as Modrinth serves them and
  are not part of FMG Client. Modpacks and their mods are downloaded from Modrinth when you install
  them, under their own licences.
- **Minecraft capes and skins:** the pictures of the capes your Minecraft account owns, and skins,
  come from Mojang (textures.minecraft.net) and belong to Mojang or to the players who made them.
- **S.T.A.L.K.E.R. 2 tab:** the GSC Game World patch notes come from Steam's public news for the
  game; the names, descriptions, pictures and numbers of Steam Workshop items come from Steam, and
  those of Nexus Mods mods from Nexus Mods (https://www.nexusmods.com). They belong to GSC Game
  World and to the mods' authors, are shown as served, and are not part of FMG Client. Mods you
  install from the tab keep their authors' terms.
- **Server lists (Discover):** server names and addresses are listed as their operators publish
  them; the servers are not operated by or associated with FMG-PLUGINS.

## 10. Built after other mods' ideas

- **Elytra Indicator** (an FMG Client mod) is modelled on **ElytraIndicator** by ItsFlory
  (https://github.com/ItsFlory/ElytraIndicator, **MIT**): the same idea - a small elytra under the
  crosshair while you wear one - in the same place, with the same three settings. FMG Client's code
  is its own. The 16x16 elytra picture of the original is used as it is, under the MIT licence
  reproduced below. Thanks for the idea and the picture.
- **Saturation** (an FMG Client mod) shows hunger and saturation the way **AppleSkin** by squeek502
  (https://github.com/squeek502/AppleSkin, released into the public domain under the Unlicense)
  made familiar. FMG Client's code and pictures are its own; no file of AppleSkin is included.

## 11. Names and trademarks

Names of games, companies, works and people that appear in FMG Client - for example in the names of
emotes, in patch notes or in server lists - are used only to say what is meant. They belong to their
owners. FMG Client is not associated with, sponsored by or approved by any of them. An owner who
objects to such a use can have it changed (see "For rights holders").

Emote animations are FMG Client's own animations, made for Minecraft's player model. Where an emote
is named after a well-known dance or meme, the name refers to that dance or meme; no recording,
model or animation data of another game or work is included.

## 12. Licence texts

| Licence | Full text |
| --- | --- |
| MIT | below, and https://opensource.org/license/mit |
| Apache-2.0 | https://www.apache.org/licenses/LICENSE-2.0 |
| MPL-2.0 | https://www.mozilla.org/en-US/MPL/2.0/ |
| LGPL-3.0 | https://www.gnu.org/licenses/lgpl-3.0.html (together with the GPL-3.0 it builds on) |
| GPL-3.0 | https://www.gnu.org/licenses/gpl-3.0.html |
| GPL-2.0 | https://www.gnu.org/licenses/old-licenses/gpl-2.0.html |
| LGPL-2.1 | https://www.gnu.org/licenses/old-licenses/lgpl-2.1.html |
| PolyForm Shield 1.0.0 | https://polyformproject.org/licenses/shield/1.0.0/ |
| zlib | https://zlib.net/zlib_license.html |
| CC0-1.0 | https://creativecommons.org/publicdomain/zero/1.0/ |
| CC BY 4.0 | https://creativecommons.org/licenses/by/4.0/legalcode |
| The Unlicense | https://unlicense.org/ |

### MIT License (ElytraIndicator's elytra picture, Copyright (c) ItsFlory)

```
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### tr7zw Protective License (EntityCulling)

EntityCulling is not carried by FMG Client (section 6). Its licence is reproduced here for your
information, because the launcher downloads the mod for you:

```
tr7zw Protective License

Copyright (c) tr7zw, 2021

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software (in source or binary form) and associated documentation files
(the "Software"), to use, modify and compile the Software, subject to the
following conditions:

The Software may not be used to get a) a commercial advantage, or b) monetary
compensation.

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```

## 13. Not included

Minecraft itself is not included and is not handed out by FMG Client: you need your own copy of
Minecraft: Java Edition, and the game's files are downloaded from Mojang's servers with your own
account. Fabric Loader (apart from its version file, section 2) and its libraries come from
Fabric's official servers. S.T.A.L.K.E.R. 2 is not included either: you need your own copy of the
game.

NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.
