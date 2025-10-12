---
title: "Scripted Importer for Ink"
date: "2025-01-01"
company: default
cover: "/projects/ink-unity-importer/cover.png"
media: []
tags:
- project
- code
layout: project
---

[Ink](http://www.inklestudios.com/ink) is [inkle's](http://www.inklestudios.com/) scripting language for writing interactive narrative, both for text-centric games as well as more graphical games that contain highly branching stories. It's designed to be easy to learn, but with powerful enough features to allow an advanced level of structuring.

Ink has a [Unity package](https://github.com/inkle/ink-unity-integration) which integrates it into the Unity Editor. However the the package was created prior to Unity's introduction of [custom scripted importers](https://docs.unity3d.com/6000.2/Documentation/Manual/ScriptedImporters.html) which means the package needed to generate [side-car](https://en.wikipedia.org/wiki/Sidecar_file) JSON files to be used at runtime. 

I set out to change this and opened a PR to add a scripted imported for ink files, which also had some additional benefits:

1. There is no longer separate source .INK files and compiled .JSON files that can get out of sync. Which means designers don't need to remember commit both .INK and JSON files, which can happen if they're testing/writing outside Unity with Inky.
2. No need to deal with managing a ink file compilation queue, and fighting with the Editor. Ink files are compiled when imported, either when added or changed.
3. You can expose `InkFile` references instead of generic `TextAsset` references in game code.
4. This codebase becomes significantly less complex, and less prone to weird errors that have to deal with compiling assets outside of Unity's normal import process.

## Links
- [Pull request on Github](https://github.com/inkle/ink-unity-integration/pull/205)