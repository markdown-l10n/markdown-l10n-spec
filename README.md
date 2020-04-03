**[English](README.md)** | [Русский](README-ru.md) | *[Add](https://github.com/markdown-localization/markdown-localization-spec#workflow)* <!-- l10n:select -->

# Markdown Localization - (Micro) Specification

## Objective

Enhance Markdown format:
* introduce language switching header
* split document into paragraphs based on markup headers

Create utility to:
* generate stubs for a new locale
* create references between original and localized document
* show the difference between original and localized document

# Workflow

## Add new locale

1. **Create new file.** 
* Use the same name, as original file has.
* Add a suffix for the supported locale.
* Example: Original - `README.md`, Localized - `README-it.md`.

2. **Copy original file content.**
* Copy the contents of the original file to a localized file.
* Put all paragrapgs, delimited by headers into comments with `l10n:p` annotations.

3. **Update headers.**
* Update the header of the original file and other localization files to include a link to a new localization file.

4. **Translate.**
* Add translations as separate paragraphs to match the structure of original file.

## Update localized files

1. **Check sync status**
* Check which paragraphs were added or updated in original file.

2. **Update translation.**
* Update original paragraphs in the commented section of localized files.
* Update translations in localized files to match original paragraphs

## Workflow automation with MDLM

Workflow can be partially automated with [mdlm-sh](https://github.com/markdown-localization/mdlm-sh).

### Add new locale

```sh
$ mdlm ls # find locale name
$ mdlm add fr # create new files, copy original file content, update headers.
```
Now files are created and ready for translation.

### Update localized files

```sh
$ mdlm diff # check sync differences between original and localized files.
```
Based on the differences, for each localized file update orignal sections in comments and translation paragraphs.

## Example
Example of original file with multiple locization:
* [example/README.md](example/README.md)

# Structure

- [Select Language Header](#select-language-header)
- [Paragraphs](#paragraphs)
- [Ignore](#ignore)

## Select Language Header

`l10n:select` Header serves as a switcher between all localizations of the file.

Example from [example/README.md](example/README-es.md):

![Localization Header Example](https://raw.githubusercontent.com/markdown-localization/markdown-localization-spec/assets/example-header.png)

## Paragraphs

Each original document is logically split into paragraphs delimited by headers. All localized files have a copy of original document split into paragraphs in comments and marked with a `l10n:p` annotation. This annotation is added to the start and end of the paragraph comment.

Example of original document [example/README.md](example/README.md):

![Localization Paragraph Example - original document](https://raw.githubusercontent.com/markdown-localization/markdown-localization-spec/assets/example-paragraph-original.png)

Localized document version [example/README-fr.md](example/README-fr.md):

![Localization Paragraph Example - localized document](https://raw.githubusercontent.com/markdown-localization/markdown-localization-spec/assets/example-paragraph-localized.png)

## Ignore

Use `l10n:ignore` annotation to exclude content of original and localized documents from synchronization status check. Mark the beginning with `l10n:ignore start` and the end with `l10n:ignore end`. Example from [example/README-ru.md](example/README-ru.md):

![Localization Ingore Example](https://raw.githubusercontent.com/markdown-localization/markdown-localization-spec/assets/example-ignore.png)

# Operations

## Add new Locale

* List Available Locales
* Add New Locale - add localized version for all files and update headers to have links to these files
* Add translation

## Sync Locale

* Check Sync Status
* Get list of Sync differences
* Sync commented paragraphs in localized documents with updated paragraphs from original document
* Update translation

## Remove Locale

* Remove Locale - remove all localized files for specific Locale and links from headers of other files

# Implementations

| Operation            | [mdlm (Bash)](https://github.com/markdown-localization/mdlm-sh) |
| -------------------- | :-----------------------------------------------------: |
| List Locales         | :heavy_check_mark:                                      |
| Add New Locale       | :heavy_check_mark:                                      |
| Add translation *    | :x:                                                     |
| Check Sync status    | :heavy_check_mark:                                      |
| Get Sync diff        | :heavy_check_mark:                                      |
| Sync *               | :x:                                                     |
| Update translation * | :x:                                                     |
| Remove Locale        | :heavy_check_mark:                                      |

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
* Creating new automations (Python, JavaScript, etc.)