[English](README.md) | **[Русский](README-ru.md)** | *[Add](https://github.com/markdown-localization/mdlm-spec#workflow)* <!-- l10n:select -->

<!-- l10n:ignore start -->
![l10n-sync-ru](https://github.com/markdown-localization/markdown-localization-spec/workflows/l10n-sync-ru/badge.svg)
<!-- l10n:ignore end -->

<!-- l10n:p
# Markdown Localization (Micro) Specification

Provides a structure and workflow to localize Markdown files.
l10n:p -->

# Локализация Markdown (Микро) Спецификация

Данная спецификация описывает структуру и подход для локализации Markdown файлов.

<!-- l10n:p
# Structure

All elements are in HTML comments.
* `l10n:select` - a switcher between all localizations of the file.
* `l10n:p` - splits document into localizable paragraphs. All localized files have a copy of original document split into paragraphs in comments and marked with a `l10n:p` annotation.
* `l10n:ignore` - excludes elements of content from original and localized documents from synchronization status check. Mark the beginning with `l10n:ignore start` and the end with `l10n:ignore end`.

Example that includes all of these sections: [README-ru.md](https://raw.githubusercontent.com/markdown-localization/markdown-localization-spec/master/README-ru.md)
l10n:p -->

# Структура

Все элементы помещаются внутрь HTML комментариев.
* `l10n:select` - переключатель между всеми доступными локализациям файла.
* `l10n:p` - разбивает файл на параграфы на основе заголовков. Все локализованные файлы включают в себя копию исходного документа, разбитого на параграфы, заключенные в комментарии и отмеченные `l10n:p` аннотацией.
* `l10n:ignore` - исключает локализацию элементов содержимого исходных и локализовынных документов. Используйте аннотацию `l10n:ignore start` в начале и `l10n:ignore end` в конце.

Пример со использованием всех элементов: [README-ru.md](https://raw.githubusercontent.com/markdown-localization/markdown-localization-spec/master/README-ru.md)

<!-- l10n:p
# Workflow
l10n:p -->

# Рабочий процесс

<!-- l10n:p
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
l10n:p -->

## Создание новых локализационных файлов

1. **Создайте новый файл.**
* Используйте имя файла такое же, как у исходного файла.
* В конце имени добавьте суффикс локали.
* Пример: Исходный файл - `README.md`, локализованный - `README-it.md`.

2. **Скопируйте содержимое исходного файла.**
* Скопируйте содержимое исходного файла в локализованный файл.
* Все параграфы исходного файла комментируются отдельно и помечаются аннотацией `l10n:p`.

3. **Обновите заголовки.**
* В исходном файле и других локализованных файлах добавьте ссылку на созданный локализованный файл.

4. **Сделайте перевод.**
* Добавьте перевод как отдельные параграфы в соответствии со структурой исходного файла.

<!-- l10n:p
## Update localized files

1. **Check sync status**
* Check which paragraphs were added or updated in original file.

2. **Update translation.**
* Update original paragraphs in the commented section of localized files.
* Update translations in localized files to match original paragraphs
l10n:p -->

## Обновление локализованных файлов

1. **Проверить состояние синхронизиции.**
*  Проверьте параграфы, которые были добавлены или изменены в исходном файле.

2. **Обновить перевод.**
* Обновите исходные параграфы в комментариях локализованых файлов.
* Обновите перевод в локализованных файлах согласно структуре исходных параграфов.

<!-- l10n:p
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
l10n:p -->

## Автоматизация рабочего процесса с помощью MDLM

Рабочий процесс может быть частично автоматизирован с помощью [mdlm-sh](https://github.com/markdown-localization/mdlm-sh).

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

Теперь файлы созданы и готовы к переводу.

После того, как исходные файлы будут обновлены, проверьте состояние синхронизации между исходным и локализованных файлами:

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

<!-- l10n:p
## Example
Example of original file with multiple locization:
* [example/README.md](example/README.md)
l10n:p -->

## Пример
Пример исходного файла с несколькими локализациями:
* [example/README.md](example/README.md)

<!-- l10n:p
# Credits

Sources for [languages](languages.txt) and their native translations:
* https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry
* https://meta.wikimedia.org/wiki/Template:List_of_language_names_ordered_by_code
l10n:p -->

# Благодарность

Источники названия [языков](languages.txt) и их переводов на родной язык:
* https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry
* https://meta.wikimedia.org/wiki/Template:List_of_language_names_ordered_by_code

<!-- l10n:p
# Contributing

All contributions are welcome:
* Specification - proposals for updates and additions
* Language tags and names - add language, update native name of the language
* Localization of this document. Guidelines and status in [LOCALIZATION.md](LOCALIZATION.md)
* Creating new automations (Python, JavaScript, etc.)
l10n:p -->

# Содействие

Приветствуется любое содействие:

* Спецификация - предложения по обновлению и добавлению новых элементов
* Тэги и названия языков - добавить язык, обновить название языка на этом языке
* Локализация этого документа. Инструкции и статус локализации в  [LOCALIZATION.md](LOCALIZATION.md)
* Создание новый автоматизаци (Python, JavaScript, etc.)
