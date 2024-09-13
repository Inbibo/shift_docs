# Release Notes

## Version 1.0.0

### Added

#### Core

- Shift's workflow execution engine.
- Shift's User Interface : An interface to interact with Shift and create workflows.
- In-build catalogs:
    - Constants catalog.
    - Standard catalog.
    - FileSystem catalog.
    - Workflow catalog.
    - CreativeSoftware catalog.
- In-build plugins:
    - Nodes Outliner plugin.
    - Variables plugin.

#### Integrations & Resources

- Scripts to bind Shift interface to a DCC for:
    - Maya: *mshift.py*.
    - Houdini: *hshift.py*.
    - Nuke: *nshift.py*.
- USD resources:
    - In-build catalogs: sUsd, sUsdTypes, sMayaUsd.
    - In-build plugins: Usd Outliner, Usd Viewer.


### Known Limitations

#### Integrations & Resources

- USD Viewer does not currently work in Houdini.