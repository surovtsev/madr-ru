# Markdown Architectural Decision Records [![part of ADR](https://img.shields.io/badge/part_of-ADR-blue.svg)](https://adr.github.io)

> "Markdown Architectural Decision Records" (MADR) `[ˈmæɾɚ]` – architectural decisions that [matter `[ˈmæɾɚ]`](https://en.wiktionary.org/wiki/matter#Pronunciation).

## News

- 2021-04-25: MADR examples featured in Medium stories ["From Architectural Decisions to Design Decisions"](https://medium.com/olzzio/from-architectural-decisions-to-design-decisions-f05f6d57032b) and ["ADR = Any Decision Record?"](https://medium.com/olzzio/adr-any-decision-record-916d1b64b28d) <!-- and blog post ["ADR = Any Decision Record? Architecture, Design and Beyond"](https://ozimmer.ch/practices/2021/04/23/AnyDecisionRecords.html) -->
- 2021-04-08: MADR recommended as an ADR format in "Design Practice Repository". This ebook is available on [Leanpub](https://leanpub.com/dpr). The decision capturing activity is also described [online](https://socadk.github.io/design-practice-repository/activities/DPR-ArchitecturalDecisionCapturing.html).
- 2020-09-29: MADR presented in the keynote "Markdown Architectural Decision Records: Capturing Decisions Where the Developer is Working" at the workshop "[Second Software Documentation Generation Challenge (DocGen2)](https://dysdoc.github.io/docgen2/index.html)". Slides available at [Speaker Deck](https://speakerdeck.com/koppor/markdown-architecturaldecisionrecords-capturing-decisions-where-the-developer-is-working).
- 2019-07-08: MADR referenced in [Architectural Decisions — The Making Of](https://ozimmer.ch/practices/2020/04/27/ArchitectureDecisionMaking.html), a post in the new blog "The Concerned Architect" by Olaf Zimmermann (shorter version available on [Medium](https://medium.com/@docsoc/y-statements-10eb07b5a177)).
- 2018-04-13: Mentioned in [@vanto](https://github.com/vanto)'s presentation about ADRs: <https://speakerdeck.com/vanto/a-brief-introduction-to-architectural-decision-records>.
- 2018-04-03: Scientific publication: [Markdown Architectural Decision Records: Format and Tool Support](http://ceur-ws.org/Vol-2072/paper9.pdf).

## Overview

An [Architectural Decision (AD)](https://en.wikipedia.org/wiki/Architectural_decision) is a software design choice that addresses a functional or non-functional requirement that is architecturally significant. 
This might, for instance, be a technology choice (e.g., Java vs. JavaScript), a choice of the IDE (e.g., IntelliJ vs. Eclipse IDE), a choice between a library (e.g., [SLF4J](https://www.slf4j.org/) vs [java.util.logging](https://docs.oracle.com/javase/8/docs/api/java/util/logging/package-summary.html)), or a decision on features (e.g., infinite undo vs. limited undo).
Do not take the term "architecture" too seriously or interpret it too strongly.
As the examples illustrate, any decisions that might have an impact on the architecture somehow are architectural decisions.

It should be as easy as possible to
a) write down the decisions and
b) to version the decisions.

This repository offers a solution to record architectural decisions.
It provides files to document Architectural Decisions using **M**arkdown and **A**rchitectural **D**ecision **R**ecords.

The decisions are placed in the folder `docs/adr` to
1) Enable [GitHub pages](https://pages.github.com/) to render it using the web.
   See <https://help.github.com/articles/configuring-a-publishing-source-for-github-pages/> for more information.
2) Separate the architectural decisions from other documentation.

The filenames are following the pattern `NNNN-title-with-dashes.md` ([ADR-0005](docs/adr/0005-use-dashes-in-filenames.md)), where

- `NNNN` is a consecutive number and we assume that there won't be more than 9,999 ADRs in one repository.
- the title is stored using dashes and lowercase, because [adr-tools] also does that.
- the suffix is `.md`, because it is a [Markdown](https://github.github.com/gfm/) file.

## Table of Contents

<!-- toc -->

- [The Template](#the-template)
- [Example](#example)
- [Apply It To Your Project](#apply-it-to-your-project)
- [Development](#development)
- [License](#license)

<!-- tocstop -->

## The Template

The template reads as follows:

```markdown
# [короткий заголовок проблемы и решения]

* Статус: [предложение | отвергнуто | принято | устарело | … | поглощено [ADR-0005](0005-example.md)] <!-- опционально -->
* Принявшие решение: [список всех кто был вовлечен в принятие решения] <!-- опционально -->
* Дата: [YYYY-MM-DD когда решение было обновлено] <!-- опционально -->
* Использованный шаблон: [MADR 3.0.0](https://adr.github.io/madr/) <!-- опционально -->

Техническая история: [описание | ссылка на запрос/задачу ] <!-- опционально -->

## Контекст и описание проблемы

[Описание контекста и описания проблемы, например, в простой форме, двумя или тремя предложениями. Вы можете выразить проблему в форме вопроса.]

## Факторы принятия решения <!-- опционально -->

* [ограничение 1, например, фактор, проблема с которой столкнулись, …]
* [ограничение 2, например, фактор, проблема с которой столкнулись, …]
* … <!-- количество факторов при принятии решения может быть разным -->

## Рассмотренные варианты

* [вариант 1]
* [вариант 2]
* [вариант 3]
* … <!-- количество вариантов может быть разным -->

## Итоговое решение

Выбран вариант: "[вариант 1]", потому что [обоснование. например, только один вариант, который удовлетворяет ограничениям | который решает проблему | … | подходит лучше всего].

### Положительные последствия <!-- опционально -->

* [например., улучшение качественных показателей, следует принять решения, …]
* …

### Отрицательные последствия <!-- опционально -->

* [например., ущерб для качественных показателей, следует принять решения, …]
* …

## Плюсы и минусы вариантов <!-- опционально -->

### [Вариант 1]

[пример | описание | ссылка по теме | …] <!-- опционально -->

* хорошо, потому что [аргумент a]
* хорошо, потому что [аргумент b]
* плохо, потому что [аргумент c]
* … <!-- количество за и против могут быть разным -->

### [Вариант 2]

[пример | описание | ссылка по теме | …] <!-- опционально -->

* хорошо, потому что [аргумент a]
* хорошо, потому что [аргумент b]
* плохо, потому что [аргумент c]
* … <!-- количество за и против могут быть разным -->

### [Вариант 3]

[пример | описание | ссылка по теме | …] <!-- опционально -->

* хорошо, потому что [аргумент a]
* хорошо, потому что [аргумент b]
* плохо, потому что [аргумент c]
* … <!-- количество за и против могут быть разным -->

## Ссылки <!-- опционально -->

* [Вид ссылки] [Ссылка на ADR] <!-- например: Предложение [ADR-0005](0005-example.md) -->
* … <!-- количество ссылок может быть разным -->
```

The template is available at [template/template.md](https://github.com/surovtsev/madr-ru/master/template/template.md).

## Example

```markdown
# Use Markdown Architectural Decision Records

## Context and Problem Statement

We want to record architectural decisions made in this project.
Which format and structure should these records follow?

## Considered Options

* [MADR](https://adr.github.io/madr/) 2.1.0 - The Markdown Architectural Decision Records
* [Michael Nygard's template](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions) - The first incarnation of the term "ADR"
* [Sustainable Architectural Decisions](https://www.infoq.com/articles/sustainable-architectural-design-decisions) - The Y-Statements
* Other templates listed at <https://github.com/joelparkerhenderson/architecture_decision_record>
* Formless - No conventions for file format and structure

## Decision Outcome

Chosen option: "MADR 2.1.0", because

* Implicit assumptions should be made explicit.
  Design documentation is important to enable people understanding the decisions later on.
  See also [A rational design process: How and why to fake it](https://doi.org/10.1109/TSE.1986.6312940).
* The MADR format is lean and fits our development style.
* The MADR structure is comprehensible and facilitates usage & maintenance.
* The MADR project is vivid.
* Version 2.1.0 is the latest one available when starting to document ADRs.
```

The example is rendered at [template/0000-use-markdown-architectural-decision-records.md](template/0000-use-markdown-architectural-decision-records.md)

For the MADR project itself, all ADRs exist at [docs/adr/](docs/adr/).

## Apply it to your project

### Initialization

Create folder `docs/adr` in your project.
Copy all files in `template` from the MADR project to the folder `docs/adr` in your project.

For instance, using `npm`, this can be done using the following command:

```sh
npm install madr && mkdir -p docs/adr && cp node_modules/madr/template/* docs/adr/
```

### Create a new ADR

Manual approach:

1. Copy `template.md` to `NNNN-title-with-dashes.md`, where `NNNN` indicates the next number in sequence.
2. Edit `NNNN-title-with-dashes.md`.
3. Update `index.md`, e.g., by executing `adr-log -d .`
   You can get [adr-log](https://github.com/adr/adr-log) by executing `npm install -g adr-log`.

Note you can also use [other patterns for the directory format](https://github.com/joelparkerhenderson/architecture_decision_record#adr-file-name-conventions), but then the tools cannot be applied.

Automatic approach:

Use [our fork](https://github.com/adr/adr-tools/tree/patch-1) of [adr-tools].
See <https://github.com/npryce/adr-tools/pull/43> for the current status of integration.

### Development

* MADR follows [Semantic Versioning 2.0.0](https://semver.org/) and documents changes in a `CHANGELOG.md` following [keep a changelog 1.0.0](http://keepachangelog.com/en/1.0.0/).
* Issues can be reported at <https://github.com/adr/madr/issues>.
* Use the [Markdown Style Guide](http://www.cirosantilli.com/markdown-style-guide/) space-sentence:1, wrap:sentence, header:atx, list-marker:asterisk, list-space:1, code:fenced

**Releasing a new version:**

1. Update `CHANGELOG.md`.
1. Update `README.md` with the new template and the example.
1. Adapt the version reference in `template/0000-use-markdown-architectural-decision-records.md`.
1. Copy `template/0000-use-markdown-architectural-decision-records.md` to `docs/adr/0000-use-markdown-architectural-decision-records.md`.
1. Update `package.json`, publish to [npmjs](https://www.npmjs.com/package/madr), create GitHub release.  
   Use [release-it](https://www.npmjs.com/package/release-it) (do not create a release on GitHub) and [github-release-from-changelog](https://www.npmjs.com/package/github-release-from-changelog).

## License

License: [CC0](https://creativecommons.org/share-your-work/public-domain/cc0)

  [adr-tools]: https://github.com/npryce/adr-tools
