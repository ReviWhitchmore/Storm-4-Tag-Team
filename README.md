# Storm 4 Tag Team — v0.8 Beta (source code)

Unofficial fan-made mod for **NARUTO SHIPPUDEN: Ultimate Ninja STORM 4** (Steam). It turns battles into
**simultaneous 3 vs 3 fights with six fighters on the field**, with a six-fighter HUD, extra cameras, lock-on styles
and new combat mechanics. Created by **Revi Whitchmore**.

> Not affiliated with Bandai Namco Entertainment or CyberConnect2. This repository contains **no game files**,
> textures, models, music, GFX or other copyrighted assets. Use offline only.

*Português mais abaixo.*

## What the mod does (v0.8)

| Feature | Status |
|---|---|
| 3v3 with six simultaneous fighters, CPU or up to 4 XInput controllers | Beta |
| Six-fighter HUD, 5 camera modes, 3 lock-on styles | Beta |
| Jutsu Clash (power struggle when two jutsu collide, 3D black-background presentation) | Tested in game |
| Dual Combo (an ally joins a teammate's combo) | Tested with CPU |
| Perfect Substitution, Grab Defense | Tested with CPU |
| Chronicles Mode: 40 classic Naruto missions in an in-game menu | Beta (Storm 4 Evolution) |
| Awaken at battle start (option) | Tested |
| Wall Running on 3 arenas (SI43B, sd03e tree trunk, Kamui dimension) | Experimental |
| Parry (RT/R2 just before a hit) | Beta, off by default |
| Adaptive CPU AI (`ia_adaptativa=1`) | Experimental, off by default |
| Mod text in English (`idioma=en`) or Portuguese | Done |

The mod targets **Storm 4 Evolution (`NSUNS4e.exe`)**. The DLL also recognizes the original Storm 4 1.09 (`NSUNS4.exe`)
and loads its 3v3 core there, but that path has not been verified in a full fight for this release; the v0.8
mechanics are enabled only on Evolution.

## Build

Requirements: Windows 10/11 x64, **Visual Studio 2022 Build Tools** (MSVC x64 + MASM), **CMake 3.20+**, Ninja (or the
Visual Studio generator).

```bat
:: from an "x64 Native Tools Command Prompt for VS 2022"
cmake -S . -B build -G Ninja -DCMAKE_BUILD_TYPE=Release
cmake --build build --target storm6
```

The result is `build/bin/winmm.dll`. MinHook is included in `third_party/minhook` (BSD 2-Clause license).

## Install a build

Recommended: use the installer from the GitHub release (it finds the game, backs up any existing `winmm.dll`, and
installs an uninstaller). Manual install: close the game and copy `winmm.dll` next to `NSUNS4e.exe`. Delete it to
remove the mod. Settings live in `storm6.ini` in the game folder (also editable from the in-game menu: **F1** or
**SELECT/Back** outside a battle). A log is written to `storm6.log`.

## How it works (short)

- `src/proxy/`: `winmm.dll` proxy; every export is forwarded to the system DLL.
- `src/addresses.*`: per-executable address table (1.09 and Evolution, chosen by the PE timestamp).
- `src/census.*`, `src/promote.*`: put the support members on the field as fighters and answer the game's
  "who is my fighter / target" queries per fighter.
- `src/hud.*`, `src/menu.*`: Direct3D 11 overlay (HUD, mod menu, banners).
- `src/camera.*`, `src/trailer_cam.*`: group/tournament/Revolution-style cameras and an optional filming camera.
- Mechanics: `jutsu_clash*`, `dual_combo.*`, `perfect_sub.*`, `grab_defense.*`, `parry.*`, `wall_run*`, `cpu_adapt*`.
- Chronicles Mode: `chronicles*`, `scene_probe.*`.

---

## Português

Mod de fã, não oficial, para **NARUTO SHIPPUDEN: Ultimate Ninja STORM 4**: lutas **3 contra 3 com seis lutadores ao
mesmo tempo**, HUD de seis, câmeras, estilos de lock-on e mecânicas novas. Criado por **Revi Whitchmore**.
Nenhum arquivo do jogo está incluído. Use somente offline.
https://livepix.gg/revi

**Compilar:** Visual Studio 2022 Build Tools (MSVC x64), CMake 3.20+ e Ninja. No "x64 Native Tools Command Prompt":
`cmake -S . -B build -G Ninja -DCMAKE_BUILD_TYPE=Release` e depois `cmake --build build --target storm6`.
A DLL sai em `build/bin/winmm.dll`.

**Instalar:** use o instalador da página de Releases (recomendado) ou copie `winmm.dll` para a pasta do `NSUNS4e.exe`
com o jogo fechado. Configurações em `storm6.ini` ou no menu do mod (**F1** / **SELECT** fora da luta).

A versão foca o **Storm 4 Evolution**. O Storm 4 original (1.09) carrega a base do 3v3, mas não foi conferido numa
luta completa nesta versão.
