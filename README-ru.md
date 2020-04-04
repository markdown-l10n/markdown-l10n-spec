[English](README.md) | **[Русский](README-ru.md)** | *[Add](https://github.com/markdown-localization/markdown-localization-spec#workflow)* <!-- l10n:select -->

<!-- l10n:ignore start -->
![l10n-sync-ru](https://github.com/markdown-localization/markdown-localization-spec/workflows/l10n-sync-ru/badge.svg)
<!-- l10n:ignore end -->

<!-- l10n:p
# Markdown Localization - (Micro) Specification

Provides a structure and approach to localize Markdown files.
l10n:p -->
# Локализация Markdown - (Микро) Спецификация

Данная спецификация описывает структуру и подход для локализации Markdown файлов.

<!-- l10n:p
# Structure

* `l10n:select` - a switcher between all localizations of the file.
* `l10n:p` - splits document into localizable paragraphs. All localized files have a copy of original document split into paragraphs in comments and marked with a `l10n:p` annotation.
* `l10n:ignore` - excludes elements of content from original and localized documents from synchronization status check. Mark the beginning with `l10n:ignore start` and the end with `l10n:ignore end`.

Example that includes all of these sections: [README-ru.md](https://raw.githubusercontent.com/markdown-localization/markdown-localization-spec/master/README-ru.md)
l10n:p -->
# Структура

* `l10n:select` - переключатель между всеми доступными локализациям файла.
* `l10n:p` - разбивает файл на параграфы на основе заголовков. Все локализованные файлы включают в себя копию исходного документа, разбитого на параграфы, заключенные в комментарии и отмеченные `l10n:p` аннотацией.
* `l10n:ignore` - исключает локализацию элементов содержимого исходных и локализовынных документов. Используйте аннотацию `l10n:ignore start` в начале и `l10n:ignore end` в конце.

Пример со использованием всех элементов: [README-ru.md](https://raw.githubusercontent.com/markdown-localization/markdown-localization-spec/master/README-ru.md)

<!-- l10n:p
# Workflow
l10n:p -->
# Рабочий процесс

<!-- l10n:p
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
l10n:p -->
## Добавление новой локали

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
## Workflow automation with MDLM

Workflow can be partially automated with [mdlm-sh](https://github.com/markdown-localization/mdlm-sh).
l10n:p -->
## Автоматизация рабочего процесса с помощью MDLM

Рабочий процесс может быть частично автоматизирован с помощью [mdlm-sh](https://github.com/markdown-localization/mdlm-sh).

<!-- l10n:p
### Add new locale

```sh
$ mdlm ls # find locale name
$ mdlm add fr # create new files, copy original file content, update headers.
```
Now files are created and ready for translation.
l10n:p -->
### Добавить новую локаль

```sh
$ mdlm ls # найти имя локали
$ mdlm add fr # создать новые файлы, скопириовать содержимое исходных файлов, обновить заголовки.
```
Теперь файлы созданы и готовы к переводу.

<!-- l10n:p
### Update localized files

```sh
$ mdlm diff # check sync differences between original and localized files.
```
Based on the differences, for each localized file update orignal sections in comments and translation paragraphs.
l10n:p -->
### Обновить локализованные файлы

```sh
$ mdlm diff # проверить состояние синхронизации и увидеть различия между исходным и локализованными файлами.
```
На основании различий, для каждого локализованного файла обновите исходные параграфы в комментариях и их переводы.

<!-- l10n:p
## Example
Example of original file with multiple locization:
* [example/README.md](example/README.md)
l10n:p -->
## Пример
Пример исходного файла с несколькими локализациями:
* [example/README.md](example/README.md)

<!-- l10n:p
# Operations
l10n:p -->
# Команды

<!-- l10n:p
## Add new Locale

* List Available Locales
* Add New Locale - add localized version for all files and update headers to have links to these files
* Add translation
l10n:p -->
## Добавить новую Локалей

* Получить список всех Локалей
* Добавить новую локализацию - добавить локализованные версии для всех файло и обновить заголовки со ссылками на эти файлы
* Добавить перевод

<!-- l10n:p
## Sync Locale

* Check Sync Status
* Get list of Sync differences
* Sync commented paragraphs in localized documents with updated paragraphs from original document
* Update translation
l10n:p -->
## Синхронизировать Локаль

* Получить статус синхронизации
* Получить список различий синхронизации
* Синхронизировать закомментированные параграфы в локализованных документых с обновленными параграфами в оригинальном документе
* Обновить перевод

<!-- l10n:p
## Remove Locale

* Remove Locale - remove all localized files for specific Locale and links from headers of other files
l10n:p -->
## Удалить Локаль

* Удалить Локаль - удалить все локализованные файлы для заданной Локали и ссылки из заголовков других файлов.

<!-- l10n:p
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
l10n:p -->
# Реализации

| Действие                        | [mdlm (Bash)](https://github.com/markdown-localization/mdlm-sh) |
| ------------------------------- | :-----------------------------------------------------: |
| Список Локалей                  | :heavy_check_mark:                                      |
| Добавить новую Локаль           | :heavy_check_mark:                                      |
| Добавить перевод *              | :x:                                                     |
| Получить статус синхронизации   | :heavy_check_mark:                                      |
| Получить различия синхронизации | :heavy_check_mark:                                      |
| Синхронизировать *              | :x:                                                     |
| Обновить перевод *              | :x:                                                     |

\* if this operation is not implemented, it is supposed to be performed manually.

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
