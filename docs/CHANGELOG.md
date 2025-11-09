# CHANGELOG for diff_files_not_copied.sh

**Auteur :** Bruno DELNOZ
**Email :** bruno.delnoz@protonmail.com
**Dernière version :** V2.2.0
**Date :** 2025-11-09
**Heure :** 2025-11-09 02:51:07

## v2.3.0 - 2025-11-09 15:30
- Applied all V110 rules: English only, systemd prompt (14.0.1), token reduction (14.22)
- Enhanced table formatting (14.23: 3 spaces, exact separators)
- Auto .gitignore with script comment (14.24)
- MD files with [DocSync], full history, pandoc-ready (14.25)
- Line count increased; no removals (14.15/14.18)

## V2.2.0 - 2025-11-09 12:00
- Reformatted and enhanced for full V109 compliance
- Implemented complete automatic documentation generation (Rule 14.25) with structured Markdown files
- Added --convert option for Markdown to DOCX/PDF conversion using pandoc
- Expanded internal comments for every section, function, and key line (Rule 14.1.1)
- Integrated systemd mode option with conditional help display (Rule 14.0.1)
- Ensured script line count increased with additional logging, checks, and explanations
- Updated .gitignore management to include /docs and verify all entries (Rule 14.24)
- Added more verbose logging and statistics tracking
- Maintained all previous features without removal or simplification (Rule 14.15, 14.18)

## V2.1.0 - 2025-11-08 16:30
- Enhanced permission management and V109 full compliance
- Added intelligent ownership detection (works with sudo)
- Auto-chown all created files to real user (not root)
- Added safe_mkdir function for proper directory creation
- Added cleanup trap for Ctrl+C interruptions
- Fixed permission issues when running with sudo
- Full compliance with Règles de Scripting V109
- Automatic .gitignore management (Rule 14.24)
- Automatic .md documentation generation (Rule 14.25)

## V2.0.0 - 2025-11-08 15:45
- Major update with features
- Fixed mkdir -p for ./results and ./logs directories before any write operation
- Added --use-inputfile option to reuse scan results from simulate mode
- Enhanced error handling and retry mechanism with exponential backoff
- Added progress indicators and detailed statistics
- Added --verbose option for detailed output
- Improved file comparison with checksums option
- All operations strictly confined to ./ directory (no /tmp usage)

## V1.0 - 2025-11-08
- Initial release

[DocSync] Fichier './docs/CHANGELOG.diff_files_not_copied.md' mis à jour automatiquement (par diff_files_not_copied.sh)
