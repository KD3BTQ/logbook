# Club Logbook
This repository hosts the club's historical contact log information and tools to edit said log files. This information is stored via ADIF file format, and the addition (or modification) of ADIF log files are handled via Github Pull Requests (PR's) that are approved by repository maintainers. If you are are here to add logs to the club log file, instructions on how to do so can be found below at [Contributing to the Club Logbook](##Contributing-to-the-Club-Logbook)

## What is an ADIF file?
ADIF (Amateur Data Interchange Format) is a plain-text file format used by amateur radio operators to store and exchange logbook contact records (QSOs) between different logging programs. Each field is written as `<FIELDNAME:LENGTH>VALUE`, where `LENGTH` is the character count of `VALUE` (e.g., `<CALL:5>W1AW `). A record (one contact) ends with the tag `<EOR>`, and an optional header section — free-form text followed by `<EOH>` — can appear at the top of the file to store metadata like the program name and ADIF version. Common fields include `CALL` (callsign), `QSO_DATE` (YYYYMMDD), `TIME_ON` (HHMM or HHMMSS), `BAND`, `MODE`, and `FREQ`. Since it's just text, you can open an `.adi`/`.adif` file in any text editor and add or fix a record by hand as long as you keep the field-length counts accurate and terminate each record with `<EOR>`.

## Contributing to the Club Logbook
To contribute to the club logbook, you must submit either
1. Submit an ADIF file with required fields
2. Submit a GitHub Issue with contact information with required fields

Either submission route will notify club logbook maintainers that a change to the club logbook has been requested. They will review the request via GitHub, and respond with their approval or a request for any required changes. 

### 1. Submit an ADIF file with required fields
todo

### 2. Submit a GitHub Issue with contact information with required fields
todo

## Using the Club Logbook ADIF Editor
This repository contains a tool to create or edit an existing ADIF file. This HTML page is [deployed to a GitHub pages site](https://kd3btq.github.io/logbook/) for easy access, but can also be downloaded to your machine for offline use. _**NOTE**: If you are not using the website version of the ADIF editor, then the tool will not have its callsign lookup information capability._ To download and use the tool offline, simply download the `index.html` page from this repo. 

**To create a new ADIF file**, simply visit the [deployed HTML page](https://kd3btq.github.io/logbook/) to get started. At this page, you can set both the callsign used for the contact (the club callsign W3APL), and your callsign or name as the 'Operator', and then the grid location of your current operations. (These three fields will then auto-populate into every 'New QSO' form that you create). Next, click 'Add New QSO', and fill in all of the details of your QSO. If a field is required, it the page will not let you save your QSO until it is populated. 

**To edit an existing ADIF**. Many programs will create an ADIF file for you, and you will want to use this ADIF as a starting point for your log file submission. You can load the existing ADIF file that you have into the ADIF editor, and the editor will notify you of any missing fields in the existing ADIF. You can edit the existing entries, and then save a new file with your edits. 
