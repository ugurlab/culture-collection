# Culture Collection

An offline culture and stock-vial inventory tool by Ugur Comlekcioglu.

- [Description and download](https://ugurlab.github.io/culture-collection/)
- [Desk & Bench catalogue](https://ugurlab.github.io/desk-and-bench/)

## Use
Download `culture-collection.zip`, extract it and open `culture-collection.html` in Chrome, Edge or Firefox. No installation, account or internet connection is needed. The ZIP contains the full application source and instructions. The full MIT and Instrument Sans SIL Open Font License texts are embedded in a comment at the top of culture-collection.html. The app is in English only.

Define your own groups (clinical, wastewater, textile factory, etc.), add cultures and attach multiple stock vials. Record freezer/device, shelf, rack, box, position, dates and status. Search, filter, archive, restore or move records to recoverable Trash, and export JSON backups and CSV reports.

Search ignores accents and dotted/dotless i, so `izmir` finds `İzmir`. Stock search also covers temperature, quantity, preparation date and notes.

Reminders: choose 1–120 calendar months in Settings (default six). Record a vial’s last viability check or use “Mark checked today”, then save. Due dates use the later of preparation and last check; month-end dates are clamped to the last day. Due vials appear on Overview. After every change, a bar at the top shows how many changes have been made since the last JSON backup, with a button to download a new one. Storing a vial in a position already used by another vial asks for confirmation.

Records stay in the browser's IndexedDB database, not in the HTML. Keep the same browser and file location. Export JSON before moving, renaming or updating the app or clearing browser data. Copying the HTML alone does not transfer records. JSON restoration replaces the whole collection. CSV is report-only. Avoid private browsing and keep regular backups.

Version 1.3 has no Firebase or cloud synchronization. DNA, sequence, plasmid and gene modules are not included. Do not enter patient identifiers.

## Site
The Pages site contains the description and download page only, with screenshots using sample data. The app itself is distributed inside the ZIP and is not served as an online tool. Site styling is shared from `/desk-and-bench/style.css`; read the catalogue's [DESIGN.md](https://github.com/ugurlab/desk-and-bench/blob/main/DESIGN.md) before changing the site. No analytics or tracking.

## Data model
JSON schemaVersion 2: groups, cultures, stocks, history, settings. Optional deletedAt timestamps retain records in Trash; stock checkedAt stores the last check date. Stable IDs link cultures to groups and stocks to cultures. Local writes check the collection revision in one IndexedDB transaction to reject conflicting edits from another window. Import validates schema, references, dates, statuses and unique culture/vial codes before replacing data. Version 1.3 migrates schema 1 from versions 1.0–1.2 without deleting records. New backups require 1.3 or newer; older apps reject schema 2 instead of silently losing Trash and settings. This structure can support a later, separate Firebase edition; no migration is implemented yet.

## Trash
Move cultures and vials to Trash and restore them there. A culture retains its linked vials; separately trashed vials remain in Trash after their culture is restored. Records are never purged automatically. Codes remain reserved while trashed. JSON backups include Trash, settings and check dates. CSV reports exclude trashed records. Groups used by trashed cultures cannot be deleted. Restoring vials to occupied positions asks for confirmation.

## Changes
- 1.3 packaging update: full MIT and Instrument Sans SIL Open Font License texts moved into the HTML; separate licence files removed from the ZIP. Application behavior is unchanged.
- 1.3: recoverable Trash; configurable viability check interval and last-check dates; schema 1 migration to schema 2; future-release workflow documented in the catalogue DESIGN.md.
- 1.2: backup bar after every change (replaces the six-month backup reminder); MIT License.
- 1.1: English only; accent-insensitive search; wider stock search; delete cultures and vials; occupied-position warning; six-month reminders for old vials and backups.
- 1.0: First release.

## Credits
Culture Collection was designed by Ugur Comlekcioglu. The first version was built with ChatGPT (OpenAI) and it was further developed with Claude (Anthropic).

## Licence
Culture Collection is open source under the [MIT License](LICENSE). You are welcome to use, change and share it, including in your own projects, as long as you keep the copyright notice and the licence text, which credit the original author. The embedded Instrument Sans font is under the SIL Open Font License (full text in the comment at the top of culture-collection.html).

## Contributing
Issues and pull requests are welcome. If you build on Culture Collection, a link back to this repository is appreciated.

## Feedback
Report issues at https://github.com/ugurlab/culture-collection/issues
