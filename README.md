# onvifdm-code-r96-trunk

ONVIF Device Manager (ODM) - an open-source Network Video Client for discovering and managing ONVIF-compliant IP cameras, encoders, storage, and analytics devices. Implements Discovery, Device, Media, Imaging, Analytics, Events, and PTZ services, with a WPF UI and an FFmpeg/live555-backed media player. Upstream project by Synesis (SourceForge `onvifdm`); this repo is my working copy of the r96 trunk tree.

**Source last updated:** 2019-10-10 · **Language:** C# / F# / C++ · **Framework:** .NET Framework 4.0 (some projects also 4.5) · **Output:** WinForms/WPF WinExe (`odm`) plus class libraries and native player DLLs

## Solution structure

| Project / area | Language | Type | Purpose |
|---|---|---|---|
| odm.ui.app | C# | WPF WinExe | Main ODM application shell |
| odm.ui.views / odm.ui.models / odm.ui.activities | C# / F# | Libraries | UI views, models, and activity workflows |
| odm.localization / odm.extensibility / odm.infra | C# / F# | Libraries | Localisation, plugins, infrastructure |
| odm.onvif.extensions / synesis plugin | F# / C# | Libraries | ONVIF extensions and Synesis plugin |
| odm.player.* | C# / C++ | WinExe + native libs | Media player host, .NET wrappers, FFmpeg/live555 player |
| onvif.services / onvif.session / onvif.discovery / onvif.utils | C# / F# | Libraries | ONVIF SOAP services, sessions, WS-Discovery, helpers |
| utils.* | C# / F# | Libraries | Async, bindings, WPF, XML, diagnostics, bootstrapping |
| libs (bccrypto, WPFToolkit.Extended, live555, ffmpeg) | C# / C++ | Vendored deps | Crypto, WPF controls, RTP/RTSP, media decode |

## How to open

- Open `odm.sln` in Visual Studio (preferred), or `odm.vc110.sln` for the VS 2012 / toolset v110 native player projects.
- Build the `odm.ui.app` startup project (assembly name `odm`).

## Requirements

- Visual Studio 2012 to 2017 (solution Format Version 12.00 / `# Visual Studio 2012`; ToolsVersion 4.0). VS 2010-era C++ toolsets also appear (`v100` / `v110` PlatformToolset on player projects).
- .NET Framework 4.0 (primary TargetFrameworkVersion; some projects also declare 4.5)
- Visual C++ with PlatformToolset v100 or v110 for `odm.player.lib` / `odm.player.net` and live555
- F# tools matching the VS install (several `.fsproj` projects)
- NuGet packages already under `packages/` (Prism 4.1, Unity 2.1, Rx 2.0, CommonServiceLocator)

## Attribution and provenance

Original project: **ONVIF Device Manager (ODM)** by Synesis / contributors (SourceForge project `onvifdm`), licensed under **GNU GPL v2**. Assembly metadata in the Synesis plugin notes Copyright © Synesis 2011.

Vendored third-party components under `libs/` and `packages/` retain their own licenses (see `THIRD_PARTY_NOTICES.md`), including Bouncy Castle, live555 (LGPL), FFmpeg (LGPL/GPL), WPF Toolkit Extended, Prism, Unity, and Reactive Extensions.

Working copy from my Development folder `onvifdm-code-r96-trunk`.

## License

GNU General Public License version 2.0 (upstream). See `LICENSE`. This working copy retains the original license; it is not re-licensed under MIT.
