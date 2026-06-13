# Rhino Plugin Development Resources

## Knowledge

### Official Docs (Primary)

- [developer.rhino3d.com — Rhino Developer Portal](https://developer.rhino3d.com)
  The single source of truth. Guides, API reference, samples, videos. Start here for everything.
- [RhinoCommon Guides](https://developer.rhino3d.com/guides/rhinocommon/)
  Cross-platform .NET plugin SDK documentation. Covers installation, first plugin, fundamentals.
- [Your First Plugin (Windows)](https://developer.rhino3d.com/guides/rhinocommon/your-first-plugin-windows/)
  Step-by-step tutorial for scaffolding a RhinoCommon plugin using the VS template.
- [Plugin User Data Guide](https://developer.rhino3d.com/guides/rhinocommon/plugin-user-data/)
  How to save/load plugin data in `.3dm` files — document-level and object-level.
- [Tabbed Panels Guide](https://developer.rhino3d.com/guides/rhinocommon/tabbed-panels/)
  Creating custom docking UI panels with RhinoCommon.
- [Event Watchers Guide](https://developer.rhino3d.com/guides/rhinocommon/event-watchers/)
  Synchronizing UI with Rhino document state changes.
- [RhinoCommon API Reference](https://developer.rhino3d.com/api/RhinoCommon/html/R_Project_RhinoCommon.htm)
  Full .NET API docs for every RhinoCommon class.

### Official Samples

- [mcneel/rhino-developer-samples (GitHub)](https://github.com/mcneel/rhino-developer-samples)
  Official sample code repository. Contains C# examples for RhinoCommon, Grasshopper, openNURBS, etc.
- [SampleCsPanel (GitHub)](https://github.com/Jack-1800/SampleCsPanel)
  Third-party sample demonstrating a tabbed docking panel in RhinoCommon.

### Video

- [Rhino 3D Developer Course C# (9 hours, free)](https://www.youtube.com/watch?v=7U9DzVkhUng)
  Free video course covering Rhino plugin development in C#. Part 6 covers user interfaces.

### Geometry & File Format

- [openNURBS Initiative](https://developer.rhino3d.com/guides/opennurbs/what-is-opennurbs/)
  The open-source toolkit for reading/writing `.3dm` files. Foundation of Rhino's data model.
- [rhino3dm (GitHub)](https://github.com/mcneel/rhino3dm)
  .NET/Python/JS libraries based on openNURBS for working with Rhino geometry outside of Rhino.

### Architecture & Patterns

- [Rhino Plugin Architecture Overview](https://developer.rhino3d.com/guides/general/what-is-a-rhino-plugin/)
  How plugins load, register commands, and integrate with Rhino's document model.
- [Display Conduits Guide](https://developer.rhino3d.com/guides/rhinocommon/display-conduits/)
  Custom viewport drawing — useful for advanced UI feedback.

## Wisdom (Communities)

- [McNeel Discourse — Rhino Developer Category](https://discourse.mcneel.com/c/rhino-developer)
  The primary community for plugin developers. High-quality answers from McNeel staff and experienced devs.
- [Food4Rhino](https://www.food4rhino.com)
  Plugin marketplace and community. Good for studying real-world plugin distribution.

## Gaps

- Few resources exist on advanced architectural patterns for multi-command, multi-panel plugins (MVC, DI, logging). Much of this must be derived from the samples and general .NET patterns.
