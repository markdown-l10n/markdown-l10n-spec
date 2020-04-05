**[English](README.md)** | [Русский](README-ru.md) | *[Add](https://github.com/markdown-localization/mdlm-spec#workflow)* <!-- l10n:select -->

# Markdown Localization (Micro) Specification

Provides a structure and workflow to localize Markdown files.

# Structure

All elements are in HTML comments.

* `l10n:select` - a switcher between all localizations of the file.
* `l10n:p` - splits document into localizable paragraphs. All localized files have a copy of original document split into paragraphs in comments and marked with a `l10n:p` annotation.
* `l10n:ignore` - excludes elements of content from original and localized documents from synchronization status check. Mark the beginning with `l10n:ignore start` and the end with `l10n:ignore end`.

Example that includes all of these sections: [README-ru.md](https://raw.githubusercontent.com/markdown-localization/markdown-localization-spec/master/README-ru.md)

# Workflow

## Localize new files

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

# Workflow automation with MDLM

Workflow can be partially automated with [mdlm-sh](https://github.com/markdown-localization/mdlm-sh).

```console
$ mdlm search eo
eo (Esperanto) - Esperanto
ka (ქართული) - Georgian
ty (Reo Mā`ohi) - Tahitian

$ mdlm add eo
Creating new localization files for locale - "eo (Esperanto) - Esperanto":
Creating example/README-eo.md. Confirm? [Y/n]
- Created.
Creating README-eo.md. Confirm? [Y/n]
- Created.
Finished. Total files created: 2
```

Now files are created and ready for translation.

Once original files are updated, check the synchronization difference between original file and localization files:

```console
$ mdlm diff es
Localization status for - es (Español) - Spanish:
- example/README-es.md (Español) - outdated.
4c4,5
< Here is an outdated text of example.
---
> Here is a text of example.
>
```

## Example

Example of original file with multiple locization:
* [example/README.md](example/README.md)

# Credits

Sources for [languages](languages.txt) and their native translations:
* https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry
* https://meta.wikimedia.org/wiki/Template:List_of_language_names_ordered_by_code

# Contributing

All contributions are welcome:

* Specification - proposals for updates and additions
* Language tags and names - add language, update native name of the language
* Localization of this document. Guidelines and status in [LOCALIZATION.md](LOCALIZATION.md)
* Creating new automations (Python, JavaScript, etc.)