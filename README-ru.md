[English](README.md) | **[Русский](README-ru.md)** | *[Add](/CONTRIBUTING.md#localization)* <!-- @l10n:h -->

<!-- @l10n:p
# Markdown Localization - (Micro) Specification

Introducing extension of the original markup format with annotations in comments in the form of `@namespace:annotation`, example: `@l10n:h`.

Example of original and localized files:
* Nested [Example](example/README.md) localization
@l10n:p -->
# Локализация Markdown - (Микро) Спецификация

Добавляется расширение ориганальной разметки в виде аннотацией в комментариях в форме `@namespace:annotation`, например: `@l10n:h`.

Пример исходного и локализованного файлов:
* Вложенный [Пример](example/README.md) локализации

<!-- @l10n:p
## Motivation

Comprehensive documentation is important for distributed projects.
Documentation in multiple languages makes the information available to wider audience.
There are volunteers, who can and want to contribute with localization.

However, Markdown markup does not support localization.
There is no process to chunk doc in pieces to facilitate iterative collaborative document update.
As soon as a original document is updated, all localizations can become outdated.
@l10n:p -->
## Причины создания

Актуальная документация важна для распределенных проектов.
Документация на нескольких языках делает информацию доступной для более широкой аудитории.
Есть волонтеры, которые могут и хотят внести свой вклад в локализацию.

Однако разметка Markdown не поддерживает локализацию.
Нет никакого процесса, чтобы разделить документ на части, чтобы облегчить итеративное совместное обновление документа.
Как только исходный документ обновляется, все локализации могут устареть.

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
## Задача

Расширить формат Markdown:
* ввести заголовок переключения языка
* разбить документ на параграфы на основе заголовков разметки

Создать утилиту для:
* создать заглушки для новой локали
* создать ссылки между оригинальным и локализованным документом
* показать разницу между оригинальным и локализованным документом

<!-- @l10n:p
## Structure
@l10n:p -->
## Структура

<!-- @l10n:p
### Localization Header

`@l10n:h` Header serves as a switcher between all localizations of the file.

Example:

![Localization Header Example](https://raw.githubusercontent.com/markdown-l10n/markdown-l10n-spec/assets/example-header.png)
@l10n:p -->
### Локализационный заголовок

`@l10n:h` Header serves as a switcher between all localizations of the file.

Заголовок `@l10n:h` используется как переключатель между всеми доступными локализациям файла.

Example:

![Пример локализационного заголовка](https://raw.githubusercontent.com/markdown-l10n/markdown-l10n-spec/assets/example-header.png)

<!-- @l10n:p
### Paragraphs

Each original document is logically split into paragraphs delimited by headers. All localized files have a copy of original document split into paragraphs in comments and marked with a `@l10n:p` annotation. This annotation is added to the start and end of the paragraph comment.

Example:

Original document `README.md`:

![Localization Paragraph Example - original document](https://raw.githubusercontent.com/markdown-l10n/markdown-l10n-spec/assets/example-paragraph-original.png)

Localized document version `README-ru.md`:

![Localization Paragraph Example - localized document](https://raw.githubusercontent.com/markdown-l10n/markdown-l10n-spec/assets/example-paragraph-localized.png)
@l10n:p -->
### Параграфы

Each original document is logically split into paragraphs delimited by headers. All localized files have a copy of original document split into paragraphs in comments and marked with a `@l10n:p` annotation. This annotation is added to the start and end of the paragraph comment.

Каждый исходный документ логически разбит на параграфы на основе заголовков. Все локализованные файлы включают в себя копию исходного документа, разбитого на параграфы, заключенные в комментарии и отмеченные `@l10n:p` аннотацией. Эта аннотация добавления в начале и конце комментария.

Пример:

Исходный документ `README.md`:

![Пример локализационного параграфа - исходный документ](https://raw.githubusercontent.com/markdown-l10n/markdown-l10n-spec/assets/example-paragraph-original.png)

Локализованная версия документа `README-ru.md`:

![Пример локализационного параграфа - локализованный документ](https://raw.githubusercontent.com/markdown-l10n/markdown-l10n-spec/assets/example-paragraph-localized.png)

<!-- @l10n:p
# Workflow
@l10n:p -->
# Рабочий процесс

<!-- @l10n:p
## Add new Locale

* List Available Locales
* Add New Locale - add localized version for all files and update headers to have links to these files
* Add translation
@l10n:p -->
## Добавить новую Локалей

* Получить список всех Локалей
* Добавить новую локализацию - добавить локализованные версии для всех файло и обновить заголовки со ссылками на эти файлы
* Добавить перевод

<!-- @l10n:p
## Sync Locale

* Check Sync Status, optionally with list of differences
* Sync commented paragraphs in localized documents with updated paragraphs from original document
* Update translation
@l10n:p -->
## Синхронизировать Локаль

* Получить статус синхронизации, опционально включая список различий
* Синхронизировать закомментированные параграфы в локализованных документых с обновленными параграфами в оригинальном документе
* Обновить перевод

<!-- @l10n:p
## Remove Locale

* Remove Locale - remove all localized files for specific Locale
@l10n:p -->
## Удалить Локаль

* Удалить Локаль - удалить все локализованные файлы для заданной Локали

<!-- @l10n:p
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
@l10n:p -->
# Реализации

| Действие                      | [mdlm (Bash)](https://github.com/markdown-l10n/mdlm-sh) |
| ----------------------------- | :-----------------------------------------------------: |
| Список Локалей                | :heavy_check_mark:                                      |
| Добавить новую Локаль         | :heavy_check_mark:                                      |
| Добавить перевод *            | :x:                                                     |
| Получить статус синхронизации | :heavy_check_mark:                                      |
| Синхронизировать *            | :x:                                                     |
| Обновить перевод *            | :x:                                                     |

\* if this operation is not implemented, it is supposed to be performed manually.

