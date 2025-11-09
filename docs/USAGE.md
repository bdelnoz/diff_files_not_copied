# USAGE for diff_files_not_copied.sh

**Author:** Bruno DELNOZ
**Email:** bruno.delnoz@protonmail.com
**Version:** v2.3.0
**Date:** 2025-11-09
**Time:** 2025-11-09 15:30

## Usage
./diff_files_not_copied.sh [OPTIONS]

## Options

| Option                   |  Alias   |  Description                                              |   Default Value     |   Possible Values                     |
|--------------------------|----------|-----------------------------------------------------------|--------------------|---------------------------------------|
| --help                   |   -h     |  Show complete help with examples                         |    N/A              |    N/A                                |
| --exec                   |  -exe    |  Execute the main copy operations                         |    0                |    0 (no), 1 (yes)                    |
| --prerequis              |   -pr    |  Verify prerequisites before run                          |    0                |    0 (no), 1 (yes)                    |
| --install                |   -i     |  Install missing prerequisites                            |    0                |    0 (no), 1 (yes)                    |
| --simulate               |   -s     |  Dry-run simulation (no actual changes)                   |    0                |    Presence triggers simulation       |
| --changelog              |   -ch    |  Display full changelog                                   |    0                |    0 (no), 1 (yes)                    |
| --source PATH            |          |  Source directory to scan from                            |    /mnt/data1_100g  |    Any valid directory path           |
| --target PATH            |          |  Target directory to copy to                              |    /mnt/TOSHIBA/... |    Any valid directory path           |
| --force                  |          |  Force copy even if file exists                           |    0                |    0 (no), 1 (yes)                    |
| --skip-already-copied    |          |  Skip files matching size and mtime                       |    0                |    0 (no), 1 (yes)                    |
| --listfiles              |          |  Display file lists (to-copy, failed)                     |    0                |    0 (no), 1 (yes)                    |
| --use-inputfile FILE     |          |  Reuse existing missing list file                         |    ""               |    Path to .txt file                  |
| --retries N              |          |  Number of copy retry attempts                            |    3                |    Positive integer                   |
| --checksums              |          |  Use MD5 checksums for comparison (slower)                |    0                |    0 (no), 1 (yes)                    |
| --verbose                |   -v     |  Enable detailed console output                           |    0                |    0 (no), 1 (yes)                    |
| --systemd                |          |  Run in systemd mode (suppress help on no args)           |    0                |    0 (no), 1 (yes) - prompted         |
| --convert                |          |  Convert all .md docs to .docx and .pdf                   |    0                |    0 (no), 1 (yes)                    |

Note: All options use double dashes (Rule 14.8); defaults apply if omitted.

## Examples
- Basic simulate: ./diff_files_not_copied.sh --simulate --listfiles
- Full exec with force: ./diff_files_not_copied.sh --exec --source /my/src --target /my/dst --force --retries 5
- Prereqs check/install: ./diff_files_not_copied.sh --prerequis  or  --install
- Docs only: ./diff_files_not_copied.sh --convert
- Systemd: Answer 'y' to prompt or use --systemd

[DocSync] File 'USAGE.diff_files_not_copied.md' updated automatically (by diff_files_not_copied.sh)
