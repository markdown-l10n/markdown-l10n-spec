**[English](README.md)** | [Русский](README-ru.md) | *[Add](/CONTRIBUTING.md#localization)* <!-- @l10n:h -->
# Markdown Localization - (Micro) Specification

Introducing extension of the original markup format with annotations in comments in the form of `@namespace:annotation`, example: `@l10n:h`.

## Example
Example of original file with multiple locization:
* [example/README.md](example/README.md)

## Motivation

Comprehensive documentation is important for distributed projects.
Documentation in multiple languages makes the information available to wider audience.
There are volunteers, who can and want to contribute with localization.

However, Markdown markup does not support localization.
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

### Localization Header

`@l10n:h` Header serves as a switcher between all localizations of the file.

Example:

![Localization Header Example](https://raw.githubusercontent.com/markdown-l10n/markdown-l10n-spec/assets/example-header.png)

### Paragraphs

Each original document is logically split into paragraphs delimited by headers. All localized files have a copy of original document split into paragraphs in comments and marked with a `@l10n:p` annotation. This annotation is added to the start and end of the paragraph comment.

Example:

Original document `README.md`:

![Localization Paragraph Example - original document](https://raw.githubusercontent.com/markdown-l10n/markdown-l10n-spec/assets/example-paragraph-original.png)

Localized document version `README-ru.md`:

![Localization Paragraph Example - localized document](https://raw.githubusercontent.com/markdown-l10n/markdown-l10n-spec/assets/example-paragraph-localized.png)

# Workflow

## Add new Locale

* List Available Locales
* Add New Locale - add localized version for all files and update headers to have links to these files
* Add translation

## Sync Locale

* Check Sync Status, optionally with list of differences
* Sync commented paragraphs in localized documents with updated paragraphs from original document
* Update translation

## Remove Locale

* Remove Locale - remove all localized files for specific Locale

# Implementations

| Operation            | [mdlm (Bash)](https://github.com/markdown-l10n/mdlm-sh) |
| -------------------- | :-----------------------------------------------------: |
| List Locales         | :heavy_check_mark:                                      |
| Add New Locale       | :heavy_check_mark:                                      |
| Add translation *    | :x:                                                     |
| Check Sync Status    | :heavy_check_mark:                                      |
| Sync *               | :x:                                                     |
| Update translation * | :x:                                                     |

\* if this operation is not implemented, it is supposed to be performed manually.

# Credits

Sources for [languages](languages.txt) and their native translations:
* https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry
* https://meta.wikimedia.org/wiki/Template:List_of_language_names_ordered_by_code

# Contributing

All contributions are welcome:
* Specification - proposals for updates and additions
* Language tags and names - add language, update native name of the language
* Localization of this document