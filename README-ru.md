[English](README.md) | **[Русский](README-ru.md)** | *[Add](/CONTRIBUTING.md#localization)* <!-- @l10n:h -->

<!-- @l10n:p
# Markdown Localization - (Micro) Specification

Introducing extension of the original markup format with annotations in comments in the form of `@namespace:annotation`, example: `@l10n:h`.
@l10n:p -->
TBD

<!-- @l10n:p
## Motivation

Comprehensive documentation is important for distributed projects.
Documentation in multiple languages makes the information available to wider audience.
There are volunteers, who can and want to contribute with localization.
However:
Markdown markaup does not support localization.
There is no process to chunk doc in pieces to facilitate iterative collaborative document update.
As soon as a original document is updated, all localizations can become outdated.
@l10n:p -->
TBD

<!-- @l10n:p
## Objective

Enhance Markdown format:
* introduce language switching header
* split document into paragraphs based on markup headers

Create utility to:
* generate stubs for a new locale
* create references between original and localized document
* show the difference between original and localized document
@l10n:p -->
TBD

<!-- @l10n:p
## Structure
@l10n:p -->
TBD

<!-- @l10n:p
### Localization Header

Header serves as a switcher between all localizations of the file.
`@l10n:h` in the same line as the header, has links to all localizations.
Example:
@l10n:p -->
TBD

<!-- @l10n:p
### Paragraphs

Each original document is logically split into paragraphs delimited by headers. All localized files have a copy of original document split into paragraphs in comments and marked with a `@l10n:p` annotation. This annotation is added to the start and end of the paragraph comment.
Example:
Original document `README.md`:

Localized document version `README-ru.md`:
@l10n:p -->
TBD

<!-- @l10n:p
# Workflow
@l10n:p -->
TBD

<!-- @l10n:p
## Add new Locale

* List Available Locales
* Add New Locale - add localized version for all file and update headers to have links to these files
* Add translation
@l10n:p -->
TBD

<!-- @l10n:p
## Sync Locale

* Sync Status, optionally with list of differences
* Sync commented paragraphs in localized documents with updated paragraphs from original document.
* Update translation
@l10n:p -->
TBD

<!-- @l10n:p
## Remove Locale

* Remove Locale - remove all localized files for specific Locale
@l10n:p -->
TBD

<!-- @l10n:p
# Implementations

| Operation            | [mdlm (Bash)](https://github.com/markdown-l10n/mdlm-sh) |
| -------------------- | :-----------------------------------------------------: |
| List Locales         | :heavy_check_mark:                                      |
| Add New Locale       | :heavy_check_mark:                                      |
| Add translation *    | :x:                                                     |
| Sync Status          | :heavy_check_mark:                                      |
| Sync                 | :heavy_check_mark:                                      |
| Update translation * | :x:                                                     |

\* if this operation is not implemented, it is supposed to be performed manually.
@l10n:p -->
TBD

<!-- @l10n:p
# Examples

* Nested [Example](example/README.md) localization
@l10n:p -->
TBD

