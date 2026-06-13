# Rhino Plugin Development Glossary

Core terminology for RhinoCommon plugin development.

## Plugin Architecture

**RhinoCommon**:
The cross-platform .NET SDK for building Rhino plugins. Provides managed wrappers over the native Rhino C++ SDK.
_Avoid_: Rhino SDK, Rhino API (ambiguous)

**PlugIn**:
The base class for a Rhino plugin. Each plugin has exactly one `PlugIn` subclass that acts as the entry point and manages the plugin's lifecycle, document data, and settings.
_Avoid_: PluginManager, PluginMain

**Command**:
A single user-invokable action that inherits from `Rhino.Commands.Command`. Each command has a unique `EnglishName` that becomes the Rhino command name. Commands are stateless — they receive a `RhinoDoc` and return a `Result`.
_Avoid_: CommandClass, RhinoCommand

**RhinoDoc**:
The active Rhino document — the central object that owns all geometry, layers, materials, and user data. Passed to every command; never use `RhinoDoc.ActiveDoc` inside a command.
_Avoid_: Document, ActiveDoc (inside commands)

**Result**:
The return type of a command's `RunCommand` method. Values: `Success`, `Failure`, `Cancel`, etc. Rhino uses this to determine undo behavior.

## Data Persistence

**UserData**:
Plugin-defined data attached to Rhino objects (geometry, layers, etc.) or stored at the document level. Serialized into `.3dm` files automatically when `ShouldWrite` returns true.
_Avoid_: CustomData, PluginData

**UserString**:
A key-value string pair attached to any `CommonObject`. Simpler than custom `UserData` — automatically serialized, no GUID needed. Preferred for simple string-based data.

**UserDictionary**:
An `ArchivableDictionary` attached to any `CommonObject`. Supports nested dictionaries and common value types. Richer than UserString, simpler than custom UserData.

**Document User Data**:
Plugin-level data saved/loaded via `WriteDocument()`/`ReadDocument()` on the `PlugIn` class. Use for data that belongs to the whole document (scene settings, plugin state).

## User Interface

**Panel**:
A dockable, tabbed UI window registered via `Panels.RegisterPanel()`. Hosts any Windows Forms or WPF control inside Rhino's panel container.

**Eto**:
A cross-platform UI toolkit bundled with Rhino. Recommended for panels that need to work on both Windows and Mac. Windows Forms and WPF also work but are Windows-only.

**DisplayConduit**:
A class that hooks into Rhino's display pipeline to draw custom graphics (wireframe, highlights, overlays) in viewports.

## Packaging

**Yak**:
Rhino's built-in package manager and file format (`.yak`). Used to package, distribute, and install plugins. A `.yak` file is a compressed archive containing the plugin DLL and metadata.
_Avoid_: YakPackage, Yak file
