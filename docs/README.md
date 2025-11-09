# README for diff_files_not_copied.sh

**Author:** Bruno DELNOZ
**Email:** bruno.delnoz@protonmail.com
**Version:** v2.3.0
**Date:** 2025-11-09
**Last Update:** 2025-11-09 15:30

## Description
Advanced differential file copy tool with error recovery. Compares SOURCE and TARGET directories, identifies missing or different files, copies them one-by-one with retry logic, and continues on errors without stopping. Generates detailed reports of successful and failed operations.

## Features
- Scan with size/mtime/checksum comparison
- Retry mechanism with exponential backoff
- Progress indicators and statistics
- Automatic .gitignore and MD documentation
- Systemd mode support
- No external sudo required

## Recent Modifications
- v2.3.0: V110 full compliance; systemd prompt added.

See CHANGELOG.md for complete history.

[DocSync] File 'README.diff_files_not_copied.md' updated automatically (by diff_files_not_copied.sh)
