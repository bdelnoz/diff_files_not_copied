# INSTALL for diff_files_not_copied.sh

**Author:** Bruno DELNOZ
**Email:** bruno.delnoz@protonmail.com
**Version:** v2.3.0
**Date:** 2025-11-09
**Time:** 2025-11-09 15:30

## Prerequisites Table

| Tool       |   Package    |   Description                       |   Optional? |
|------------|--------------|-------------------------------------|-------------|
| rsync      |   rsync      |   File synchronization              |   No        |
| find       |   findutils  |   Directory traversal               |   No        |
| stat       |   coreutils  |   File stats (size/mtime)           |   No        |
| md5sum     |   coreutils  |   Checksums for comparison          |   No        |
| awk        |   gawk       |   Text processing                   |   No        |
| sed        |   sed        |   Stream editing                    |   No        |
| grep       |   grep       |   Pattern search                    |   No        |
| mkdir      |   coreutils  |   Directory creation                |   No        |
| date       |   coreutils  |   Timestamps                        |   No        |
| pandoc     |   pandoc     |   MD to DOCX/PDF conversion         |   Yes       |

## Installation Instructions
1. Make executable: chmod +x diff_files_not_copied.sh
2. Check deps: ./diff_files_not_copied.sh --prerequis
3. Install missing: ./diff_files_not_copied.sh --install  (auto apt/yum/dnf)
4. For pandoc manual: sudo apt update && sudo apt install pandoc  (Debian/Ubuntu)
5. Run: ./diff_files_not_copied.sh --simulate  (first time)

No external sudo for core run; internal handling.

[DocSync] File 'INSTALL.diff_files_not_copied.md' updated automatically (by diff_files_not_copied.sh)
