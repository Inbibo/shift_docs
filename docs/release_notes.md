# Release Notes

## Version 1.0.0

### Added

#### Core

- Shift's workflow execution engine.
- Shift's User Interface : An interface to interact with Shift and create workflows.
- In-built catalogs:
    - Constants catalog.
    - Standard catalog.
    - FileSystem catalog.
    - Workflow catalog.
    - CreativeSoftware catalog.
- In-built plugins:
    - Nodes Outliner plugin.
    - Variables plugin.
- Workflow examples for starters.
    - float_sum.sft
    - analyse_path.sft
    - backup_files_from_dir.sft
    - get_image_sequence_frame_list.sft

#### Integrations & Resources

- Scripts to bind Shift interface to a DCC for:
    - Maya: *mshift.py*.
    - Houdini: *hshift.py*.
    - Nuke: *nshift.py*.
- USD resources:
    - In-built catalogs: sUsd, sUsdTypes, sMayaUsd.
    - In-built plugins: Usd Outliner, Usd Viewer.
    - Workflow examples to replicate for Pixar's USD tutorials.


### Known Limitations

#### Integrations & Resources

- USD Viewer does not currently work in Houdini.