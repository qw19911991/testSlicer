![alt text][logo]

SynDaver Symple Slicer
======================

Symple Slicer is a simple-to-use, web-based slicer for 3D printers,
built on the robust and dependable [CuraEngine].

Symple Slicer was developed at the Loveland, Colorado division of
[SynDaver Labs, Inc.] for use with SynDaver 3D printers. Symple Slicer
is licensed under the [GNU Affero General Public License Version 3].

To run the online version of Symple Slicer, use the following links:

| Release     | Live URL                                 |
|-------------|------------------------------------------|
| Stable      | https://syndaverco.github.io/slicer      |
| Development | https://syndaverco.github.io/slicer-beta |

The current web version has experimental support for [Web Serial API]
when "Experimental Web Platform features" is enabled in Chrome and
"?enableSerial=1" is appended to the URL.

An Electron based desktop version of Symple Slicer which can print
to USB attached printers and flash printer firmware is also available.
For developers familiar with [Electron], there are build instructions
in the 'docs' directory.

Issues and Feature Requests
---------------------------

If you have issues or feature requests for Symple Slicer, please reach out to "3dsupport@syndaver.com"

Adding User Profiles
--------------------

*User made profiles are not supported by SynDaver. Use this functionality at your own risk*

If you have created profiles for your own printers or materials, you can add them to Symple Slicer.
To add profiles to Symple Slicer, host your customized profiles on [GitHub Pages] and then add the
network URL of the "profile_list.toml" file to the "Data Sources" box under "Advanced Options":

![Data Sources](https://github.com/SynDaverCO/symple-slicer/raw/master/docs/images/DataSources.PNG)

For an example profile and documentation, look in the [src-app/config/profiles] directory.

Easy to use, easy to print
--------------------------

For end-users, Symple Slicer brings the following advantages:

- Easy-to-use interface, with a step-by-step wizard 
- Runs on many platforms, requiring only a compatible web browswer
   - Installable as an app on Chromebooks
   - After being run once, it will be cached and can be used off-line
   - Automatic updates when connected to the web
- Uses the [CuraEngine] for slicing

Easy for developers as well
---------------------------

For developers and contributors, Symple Slicer brings the following
advantages:

- Open-source and build using [THREE.js] and WebGL
- Written in modern JavaScript (ES6)
- Fast development turn-around times
   - Web UI can be executed-in-place with no compilation
   - Updates can be pushed to users in minutes
- No server-side code for straight-forward deployment
- Clean, human-readable profile configuration files ([TOML])
- [CuraEngine] is far easier to compile than for Cura:
   - Uses a simple command-line build of [CuraEngine]
   - No dependencies on libarcus or protobuff
   - CuraEngine can be compiled into [WebAssembly] in minutes
- Compatibility with Cura's JSON files (fdmprinter and fdmextruder):
   - Simplifies upgrades to the CuraEngine
   - Allows automatic computation of related values
   - Implements Python to JavaScript translation for formulas

Scope and limitations
---------------------

Symple Slicer is not meant as a replacement for Cura for advanced
users. Slicing is currently limited to a single extruder and the
GUI allows access to a subset of all Cura settings (although
exporting, editing and importing a TOML configuration file allows
advanced users to access to all Cura command-line slicer options).

History
-------

Symple Slicer is a spin off from earlier work done by the author
in 2016 on a native JavaScript slicing engine and web GUI. There
are still references to a JSSlicer engine in the code. Such code
isn't necessarily useful or functional in Symple Slicer, but is
being kept around for posterity and/or future work.

Re-Building CuraEngine from source
----------------------------------

This repo contains pre-built [WebAssembly] binaries for [CuraEngine].
If needed, these may be re-generated from the [CuraEngine] C++
submodule (in `src-cura/`) using the `build-cura-engine.sh` shell
script. Rebuilding the [CuraEngine] requires the [EMSCRIPTEN]
toolchain. Refer to the documentation in [config/README.md] for
information on upgrading the slicing engine and associated
configuration files.

[THREE.js]: https://threejs.org
[EMSCRIPTEN]: https://emscripten.org
[CuraEngine]: https://github.com/Ultimaker/CuraEngine
[GNU Affero General Public License Version 3]: https://github.com/SynDaverCO/symple-slicer/raw/master/LICENSE.txt
[config/README.md]: https://github.com/SynDaverCO/symple-slicer/blob/master/config/README.md
[SynDaver Labs, Inc.]: https://syndaver.com
[WebAssembly]: https://webassembly.org
[TOML]: https://en.wikipedia.org/wiki/TOML
[Electron]: https://www.electronjs.org/
[GitHub Pages]: https://pages.github.com/
[Web Serial API]: https://www.chromestatus.com/feature/6577673212002304
[src-app/config/profiles]: https://github.com/SynDaverCO/symple-slicer/tree/master/src-app/config/profiles

[logo]: https://github.com/SynDaverCO/symple-slicer/raw/master/src-app/images/screenshot.png "SynDaver Symple Slicer"