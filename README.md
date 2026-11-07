# Culture Collection / Kültür Koleksiyonu

An offline culture and stock-vial inventory tool by Ugur Comlekcioglu / Uğur Çömlekcioğlu.

- [English description and download](https://ugurlab.github.io/culture-collection/)
- [Türkçe açıklama ve indirme](https://ugurlab.github.io/culture-collection/tr.html)
- [Desk & Bench catalogue](https://ugurlab.github.io/desk-and-bench/)

## Use
Download culture-collection.zip, extract it, and open culture-collection.html in Chrome, Edge or Firefox. Use the language button for English/Türkçe. No installation, account or internet connection is needed. The ZIP contains the full application source, bilingual instructions and the embedded font license.

Define your own groups (clinical, wastewater, textile factory, etc.), add cultures and attach multiple stock vials. Record freezer/device, shelf, rack, box, position, dates and status. Search, filter, archive/restore, export JSON backups and CSV reports.

Records stay in the browser’s IndexedDB database, not in the HTML. Keep the same browser and file location. Export JSON before moving, renaming or updating the app or clearing browser data. Copying the HTML alone does not transfer records. JSON restoration replaces the whole collection. CSV is report-only. Avoid private browsing and keep regular backups.

Version 1.0 has no Firebase or cloud synchronization. DNA, sequence, plasmid and gene modules are not included. Do not enter patient identifiers.

## Site
The Pages site contains description/download pages only, with screenshots using sample data. The app itself is distributed inside the ZIP and is not served as an online tool. Site styling is shared from /desk-and-bench/style.css; read the catalogue’s DESIGN.md before changing the site. No analytics or tracking.

## Data model
JSON schemaVersion 1: groups, cultures, stocks, history. Stable IDs link cultures to groups and stocks to cultures. Local writes check the collection revision in one IndexedDB transaction to reject conflicting edits from another window. Import validates schema, references, dates, statuses and unique culture/vial codes before replacing data. This structure can support a later, separate Firebase edition; no migration is implemented yet.

## Feedback
Report issues at https://github.com/ugurlab/culture-collection/issues
