# qlik-timeline-grid

Qlik Sense extension project for timeline and Gantt-style visualizations.

## Current status

This repository currently contains a modernized version of the original `sense-d3-gantt` extension, with compatibility fixes for newer Qlik environments:

- removed broken `moment` runtime dependency;
- fixed extension package manifest for current Qlik upload validation;
- updated package file list (`wbfolder.wbl`) to include required assets.

## Extension included today

Path: `build/sense-d3-gantt`

Current data model (existing chart):

- `Dimension 1`: task label / item id;
- `Dimension 2`: start date (must be flagged as **Bar Start Date**);
- `Measure 1`: duration in days.

`End Date` is calculated as `Start Date + Duration`.

## Visual reference

![Reference - not grouped timeline](https://github.com/plzaart/multicolored_timeline/raw/master/notgruped.PNG)

## Upload/installation

Use a ZIP generated from `build/sense-d3-gantt` only (do not upload the full project ZIP).

Example:

```bash
cd build
zip -r sense-d3-gantt-upload.zip sense-d3-gantt -x "*.DS_Store" "*.zip"
```

Then upload `sense-d3-gantt-upload.zip` in Qlik Management Console.

## Roadmap (planned)

- timeline-grid layout (left table + right timeline);
- support for 2+ dimensions in rows;
- support for text measures in table columns;
- explicit start and end date fields;
- configurable "Today" vertical line.

## Attribution and sources

This work is based on and inspired by the following open-source projects:

- [mcgovey/qlik-sense-timebased-gantt](https://github.com/mcgovey/qlik-sense-timebased-gantt)
- [plzaart/multicolored_timeline](https://github.com/plzaart/multicolored_timeline)
- [SimoneSilini/Reboot-Timeline](https://github.com/SimoneSilini/Reboot-Timeline)
- [brianwmunz/QlikSenseD3Utils](https://github.com/brianwmunz/QlikSenseD3Utils)

## License

MIT. See `LICENSE.md`.
