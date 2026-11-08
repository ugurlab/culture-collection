# Culture Collection

An offline culture and stock-vial inventory tool by Ugur Comlekcioglu.

- [Description and download](https://ugurlab.github.io/culture-collection/)
- [Desk & Bench catalogue](https://ugurlab.github.io/desk-and-bench/)

## Use
Download `culture-collection.zip`, extract it and open `culture-collection.html` in Chrome, Edge or Firefox. No installation, account or internet connection is needed. The ZIP contains the full application source, instructions and the embedded font licence. The app is in English only.

Define your own groups (clinical, wastewater, textile factory, etc.), add cultures and attach multiple stock vials. Record freezer/device, shelf, rack, box, position, dates and status. Search, filter, archive, restore or delete records, and export JSON backups and CSV reports.

Search ignores accents and dotted/dotless i, so `izmir` finds `İzmir`. Stock search also covers temperature, quantity, preparation date and notes.

Reminders: vials prepared more than six months ago are marked and listed on the Overview tab for a viability check. After every change, a bar at the top shows how many changes have been made since the last JSON backup, with a button to download a new one. Storing a vial in a position already used by another vial asks for confirmation.

Records stay in the browser's IndexedDB database, not in the HTML. Keep the same browser and file location. Export JSON before moving, renaming or updating the app or clearing browser data. Copying the HTML alone does not transfer records. JSON restoration replaces the whole collection. CSV is report-only. Avoid private browsing and keep regular backups.

Version 1.2 has no Firebase or cloud synchronization. DNA, sequence, plasmid and gene modules are not included. Do not enter patient identifiers.

## Site
The Pages site contains the description and download page only, with screenshots using sample data. The app itself is distributed inside the ZIP and is not served as an online tool. Site styling is shared from `/desk-and-bench/style.css`; read the catalogue's [DESIGN.md](https://github.com/ugurlab/desk-and-bench/blob/main/DESIGN.md) before changing the site. No analytics or tracking.

## Data model
JSON schemaVersion 1: groups, cultures, stocks, history. Stable IDs link cultures to groups and stocks to cultures. Local writes check the collection revision in one IndexedDB transaction to reject conflicting edits from another window. Import validates schema, references, dates, statuses and unique culture/vial codes before replacing data. Versions 1.1 and 1.2 use the same data format as 1.0, so existing records open unchanged. This structure can support a later, separate Firebase edition; no migration is implemented yet.

## Changes
- 1.2: backup bar after every change (replaces the six-month backup reminder); MIT License.
- 1.1: English only; accent-insensitive search; wider stock search; delete cultures and vials; occupied-position warning; six-month reminders for old vials and backups.
- 1.0: First release.

## Licence
Culture Collection is open source under the [MIT License](LICENSE). You are welcome to use, change and share it, including in your own projects, as long as you keep the copyright notice and the licence text, which credit the original author. The embedded Instrument Sans font is under the SIL Open Font License (FONT-LICENSE.txt in the ZIP).

## Contributing
Issues and pull requests are welcome. If you build on Culture Collection, a link back to this repository is appreciated.

## Feedback
Report issues at https://github.com/ugurlab/culture-collection/issues
