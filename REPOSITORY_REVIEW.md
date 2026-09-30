# Repository review

Repository: https://github.com/PADF-DETR/PADF-DETR

Initial settings check performed on 2026-09-29 using the public API and authenticated General settings page. The table below records that historical check, not a fresh audit of every setting.

| Item | Observed state | Interpretation |
| --- | --- | --- |
| Visibility | Public | Public reader access is enabled. |
| Default branch | main | Suitable; no journal-specific branch name is required. |
| Preserve this repository | Enabled | Useful preservation; not a registered DOI. |
| Issues | Enabled; all users may create issues | Public support route is available. |
| Wiki editing | Collaborators only | Public readability is retained. |
| Release immutability | Disabled | A fixed archival version is still needed. |
| Include Git LFS objects in archives | Disabled | Prepared uploads use ordinary ZIP files, not LFS pointers. |
| License | None detected in initial repository | Upstream headers cite AGPL-3.0; dataset licensing is unresolved. |
| Releases | None at initial inspection | Connecting Zenodo alone does not establish a deposit. |
| Repository name | Same as account | README also appears on the account profile. |

No permissions or security settings were changed during the initial check. This is a review of relevant observed settings, not all account settings. Public visibility alone does not demonstrate PLOS compliance. Current material gaps are documented in `README.md` and `REPRODUCIBILITY_NOTES.md`.

## Follow-up (2026-09-30)

- GitHub confirms public release [v1.0.0](https://github.com/PADF-DETR/PADF-DETR/releases/tag/v1.0.0) was published on 2026-09-30.
- The repository owner provided the associated Zenodo DOI: [10.5281/zenodo.23050051](https://doi.org/10.5281/zenodo.23050051).
- Zenodo automatic preservation is enabled for this repository, as confirmed in the authenticated settings page.
- The v1.0.1 version DOI is `10.5281/zenodo.23050439`; the all-versions concept DOI is `10.5281/zenodo.23050050`. The v1.0.0 version DOI remains `10.5281/zenodo.23050051`.
- README and `CITATION.cff` identify the current version, concept DOI, and previous version. The Zenodo record does not resolve the outstanding source-code completeness, data-rights, or data-split issues.

## Manifest scope

`MANIFEST.csv` inventories the expanded preparation snapshot, not the current repository root. Some listed preparation files are not distributed at the root, and the manifest's README entry predates the current root README. `PACKAGE_CHECKSUMS.json` is the checksum list for the five ZIP downloads currently distributed at the root.
