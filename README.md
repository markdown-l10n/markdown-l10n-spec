# Markdown Localization - (Micro) Specification
Introducing extension of the origina markup format with annotations in comments in the form of `@namespace:annotation`, example: `@l10n:h`.

## Motivation
Comprehensive documentation is important for distributed projects.
Documentation in multiple languages makes the information available to wider audience.
There are volunteers, who can and want to contribute with localization.
However:
Markdown markaup does not support localization.
There is no process to chunk doc in pieces to facilitate iterative collaborative document update.
As soon as a original document is updated, all localizations can become outdated.

## Objective
Enhance Markdown format:
* introduce language switching header
* split document into paragraphs based on markup headers

Create utility to:
* generate stubs for a new locale
* create references between original and localized document
* show the difference between original and localized document

## Structure
# Localization Header
`@l10n:h` in the same line as the header, has links to all localizations.
Example:
```
**[English](README.md)** | [Deutsch](README-de.md) | [Русский](README-ru.md) | *[Add](/CONTRIBUTING.md#localization)* <!-- @l10n:h -->
```

# Paragraphs
`@l10n:p` added to the start and and of the paragraph comment.
Example:
Original document `README.md`:
```
## Situation
Documentation in multiple languages makes the information available to wider audience.
```

Localized document version `README-ru.md`:
```
<!-- @l10n:p
## Situation
Documentation in multiple languages makes the information available to wider audience.
@l10n:p -->
## Ситуация
Документация на разных языках делает информацию доступной для более широкой аудитории.
```

## Methods
* List Available Locales
* Add New Locale
* Sync Status, optionally with list of differences