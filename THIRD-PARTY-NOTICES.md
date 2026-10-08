# Third-party notices

The FMG Client installer also puts other people's software on your PC, so FMG Client works out of
the box (versions as bundled with FMG Launcher 1.1.0 / FMG Client 1.0.4). None of it is made by FMG-PLUGINS, and none of it is covered by the FMG Client License.
Each component keeps its own license and its authors keep all their rights. The mods are the
authors' original, unchanged files. Where FMG Client ships a settings file for a mod, only that
settings file comes from FMG Client.

Nothing in the FMG Client License limits the rights these licenses give you.

## Fabric mods

| Mod | Version | Made by | License | Source |
| --- | --- | --- | --- | --- |
| BetterHurtCam | 1.14.0+mc26.2 | uku | MIT | https://github.com/uku3lig/betterhurtcam |
| BetterShields | 1.11.0+mc26.2 | uku | MPL-2.0 | https://github.com/uku3lig/bettershields |
| Cloth Config | 26.2.155 | shedaniel | LGPL-3.0 | https://github.com/shedaniel/ClothConfig |
| CookeyMod | 1.7.19+26.2 | RizeCookey | CC0-1.0 | https://github.com/rizecookey/CookeyMod |
| Crosshair Indicator | 1.0.3 | SwimmingDog1, MGC8 | CC0-1.0 | (the mod gives no source link) |
| EntityCulling | 1.11.2 | tr7zw | tr7zw Protective License (below) | https://github.com/tr7zw/EntityCulling |
| Fabric API | 0.161.0+26.2 | FabricMC | Apache-2.0 | https://github.com/FabricMC/fabric |
| Fabric Language Kotlin | 1.14.1+kotlin.2.4.20 | FabricMC | Apache-2.0 | https://github.com/FabricMC/fabric-language-kotlin |
| FerriteCore | 9.0.0 | malte0811 | MIT | https://github.com/malte0811/FerriteCore |
| Inventory HUD+ | 3.4.34 | DmitryLovin | All Rights Reserved | https://www.curseforge.com/minecraft/mc-mods/inventory-hud-forge |
| Iris | 1.11.4+mc26.2 | coderbot, IMS212, Justsnoopy30, FoundationGames | LGPL-3.0-only | https://github.com/IrisShaders/Iris |
| Lithium | 0.25.3+mc26.2 | JellySquid, 2No2Name | LGPL-3.0-only | https://github.com/CaffeineMC/lithium-fabric |
| Marlow's Crystal Optimizer | 1.1.0 | Bram, Marlow | MIT | https://github.com/Bram1903/MarlowsCrystalOptimizer |
| Mod Menu | 20.0.3 | Prospector, haykam821, gniftygnome, TerraformersMC | MIT | https://github.com/TerraformersMC/ModMenu |
| oωo (owo-lib) | 0.13.1+26.2 | glisco | MIT | https://github.com/wisp-forest/owo-lib |
| Placeholder API | 3.1.0-beta.1+26.2 | Patbox | LGPL-3.0 | https://github.com/Patbox/TextPlaceholderAPI |
| Shield Fixes | 2.0.4+26.2 | Walksy | MIT | https://github.com/Walksy/ShieldFixes |
| Shield Status | 4.1.8+26.2 | Walksy | MIT | https://github.com/Walksy/ShieldStatus |
| Simple Voice Chat | 2.6.24+26.2 | Max Henkel | All Rights Reserved | https://github.com/henkelmax/simple-voice-chat |
| Sodium | 0.9.2+mc26.2 | JellySquid (CaffeineMC) | PolyForm Shield 1.0.0 | https://github.com/CaffeineMC/sodium |
| TierTagger | 2.6.0+mc26.2 | uku, netiyiy (original creator) | MPL-2.0 | https://github.com/mctiers-dev/TierTagger |
| Toggle Toggle Sprint | 1.4.2 | celeste | zlib | https://codeberg.org/celestialfault/toggle-toggle-sprint |
| TotemCounter | 1.13.0+mc26.2 | uku | MIT | https://github.com/uku3lig/totemcounter |
| ukulib | 2.1.1+26.2 | uku | MPL-2.0 | https://github.com/uku3lig/ukulib |
| uku's Armor HUD | 0.12.0+mc26.2 | BerdinskiyBear, uku | MIT | https://github.com/uku3lig/armor-hud |
| Walksy Lib | 1.0.12+26.2 | Walksy | MIT | https://github.com/Walksy/WalksyLib |
| YetAnotherConfigLib | 3.9.7+26.2 | isXander | LGPL-3.0-or-later | https://github.com/isXander/YetAnotherConfigLib |
| Zoomify | 2.16.3+26.2 | isXander | LGPL-3.0-or-later | https://github.com/isXander/Zoomify |

Most mods also carry their own license file inside their .jar.

**LGPL and MPL mods:** their complete source code is at the links above. They are separate .jar
files in your `mods` folder, so you can swap any of them for your own build or another version.

## Fabric Loader's version file

The installer carries Fabric Loader's version file for Minecraft 26.2 (`fabric-loader-0.19.5-26.2.json`, exactly as
https://meta.fabricmc.net serves it), so FMG Client installs without Fabric's own installer. Fabric Loader is made by
FabricMC under the **Apache-2.0** license (https://github.com/FabricMC/fabric-loader). The loader itself and its
libraries are not included: the launcher downloads them from Fabric's official servers.

## LZMA SDK (the launcher's .7z reader)

The FMG Launcher opens .7z mod archives for the S.T.A.L.K.E.R. 2 tab with the C decoder of the **LZMA SDK** by Igor
Pavlov (https://www.7-zip.org/sdk.html, version 25.01), which its author placed in the **public domain**. Two small
changes, both in 7zDec.c: PPMd-packed archives are read too, and PPMd settings longer than 5 bytes are accepted (as
7-Zip itself does).

## FFmpeg

FMG Clips uses FFmpeg to save clips as MP4 (and the launcher for clip thumbnails). Since 1.3 the installer
includes a small build made for FMG Client from the upstream sources - FFmpeg 8.1.2 with
x264 0.165.3223, nv-codec-headers 12.1.14.0 and oneVPL 2023.3.0 - containing only what Clips needs (the one
change: a version-information resource). It is
not packed or compressed (the earlier UPX-packed build made antivirus programs suspicious).

- License: **GPL-2.0-or-later**. FFmpeg itself is LGPL-2.1-or-later, but this build includes libx264
  (GPL-2.0-or-later), which makes the whole build GPL. nv-codec-headers and oneVPL are MIT. Full text:
  https://www.gnu.org/licenses/old-licenses/gpl-2.0.html
- Source code: the exact source archives and the build script (`installer/ffmpeg/build_ffmpeg.sh`) are
  published with every release at https://github.com/mgnfrdnw-code/FMG-Client/releases; upstream:
  https://git.ffmpeg.org/ffmpeg.git, https://code.videolan.org/videolan/x264
- A copy of this notice, `FFMPEG-LICENSE.txt`, is installed next to `ffmpeg.exe`.

## Microsoft WebView2 (pages inside the launcher, since launcher 1.2.0)

The launcher shows Steam's store page and Nexus Mods inside its own window with Microsoft Edge WebView2,
which is part of Windows 10 and 11 (it is not included here). To reach it, the installer puts Microsoft's
`WebView2Loader.dll` (version 1.0.2957.106, signed by Microsoft) next to `FMG Launcher.exe`. Without
it the launcher simply opens those pages in your browser.

- `WebView2Loader.dll` - Copyright (C) Microsoft Corporation. All rights reserved. Redistributed under
  the license of the Microsoft WebView2 SDK:

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

## Online data shown in the launcher

- **Weather data by [Open-Meteo.com](https://open-meteo.com/)**, used under the Creative Commons
  Attribution 4.0 International license (https://creativecommons.org/licenses/by/4.0/). The weather
  on the Play page's background (rain, snow, hail, fog, thunder, wind) is drawn from it, only when you
  set a town in Settings. Open-Meteo's free service is for non-commercial use; FMG Client is free.
- **Add-ons and modpacks on Modrinth:** the names, descriptions, pictures and numbers in the Add-Ons tab
  and its overview window come from Modrinth (https://modrinth.com) and belong to their authors. They
  are shown as Modrinth serves them and are not part of FMG Client. Modpacks and their mods are
  downloaded from Modrinth when you install them, under their own licenses.
- **e4mc** (https://modrinth.com/mod/e4mc, by Skye, **MIT**) is not in the installer: the launcher
  downloads it from Modrinth when you switch world hosting on, and its relay (e4mc.link) carries the
  connection while you host.
- **Minecraft capes:** the pictures of the capes your Minecraft account owns come from Mojang
  (textures.minecraft.net) and belong to Mojang.
- **S.T.A.L.K.E.R. 2 tab:** the GSC Game World patch notes come from Steam's public news for the game;
  the names, descriptions, pictures and numbers of Steam Workshop items come from Steam, and those of
  Nexus Mods mods from Nexus Mods (https://www.nexusmods.com). They belong to GSC Game World and to the
  mods' authors, are shown as served, and are not part of FMG Client. Mods you install from the tab
  keep their authors' terms. S.T.A.L.K.E.R. 2: Heart of Chornobyl is a trademark of GSC Game World.

## License texts

| License | Full text |
| --- | --- |
| MIT | https://opensource.org/license/mit |
| Apache-2.0 | https://www.apache.org/licenses/LICENSE-2.0 |
| MPL-2.0 | https://www.mozilla.org/en-US/MPL/2.0/ |
| LGPL-3.0 | https://www.gnu.org/licenses/lgpl-3.0.html (together with the GPL-3.0 it builds on) |
| GPL-3.0 | https://www.gnu.org/licenses/gpl-3.0.html |
| PolyForm Shield 1.0.0 | https://polyformproject.org/licenses/shield/1.0.0/ |
| zlib | https://zlib.net/zlib_license.html |
| CC0-1.0 | https://creativecommons.org/publicdomain/zero/1.0/ |

### tr7zw Protective License (EntityCulling)

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

## Not included

Minecraft itself is not included and is not handed out by FMG Client: you need your own copy of
Minecraft: Java Edition. Minecraft, Fabric Loader (apart from its version file, above) and their
libraries are not included either; they come from Mojang's and Fabric's official servers.
S.T.A.L.K.E.R. 2 is not included either: you need your own copy of the game.

NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.
