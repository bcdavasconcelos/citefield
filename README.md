# Citeproc - Citefield

[![GitHub build status][CI badge]][CI workflow]

[CI badge]: https://img.shields.io/github/actions/workflow/status/pandoc-ext/citefield/ci.yaml?logo=github&branch=main
[CI workflow]: https://github.com/pandoc-ext/citefield/actions/workflows/ci.yaml

## Background

[BibLaTeX](https://mirrors.ibiblio.org/CTAN/macros/latex/contrib/biblatex/doc/biblatex.pdf) has a command called *citefield* (*e.g.* `\citefield{citekey}{field}`) that allows printing the value of any field of a bibliographic entry. This Lua filter provides a similar functionality for [Citeproc](https://github.com/jgm/citeproc) using [Pandoc Markdown](https://pandoc.org/MANUAL.html#pandocs-markdown) syntax: `[@Citekey]{.field}`.

## Syntax

The first argument is the `citekey`, the second argument is the CSL field / variable name.

``` markdown
[@DA]{.title} <!-- Only one at a time -->
[@DA]{.author}
[@DA]{.publisher}
[@Trott2014]{.publisher}
[@Trott2014]{.issued}
[@DA]{.page}
[@Trott2014]{.URL}
```

Possible CSL variables include:

```
abstract, accessed, annote, archive, archive_collection, archive_location, archive-place, author, authority, available-date, call-number, chair, chapter-number, citation-key, citation-label, citation-number, collection-editor, collection-number, collection-title, compiler, composer, container-author, container-title, container-title-short, contributor, curator, dimensions, director, division, DOI, edition, editor, editor-translator, editorial-director, event, event-date, event-place, event-title, executive-producer, first-reference-note-number, genre, guest, host, illustrator, interviewer, ISBN, ISSN, issue, issued, jurisdiction, keyword, language, license, locator, medium, narrator, note, number, number-of-pages, number-of-volumes, organizer, original-author, original-date, original-publisher, original-publisher-place, original-title, page, page-first, part-number, part-title, performer, PMCID, PMID, printing-number, producer, publisher, publisher-place, recipient, references, reviewed-author, reviewed-genre, reviewed-title, scale, script-writer, section, series-creator, source, status, submitted, supplement-number, title, title-short, translator, URL, version, volume, volume-title, year-suffix
```

Most entries will contain only a small subset of these. If an invalid field is specified, or if the value of the field is empty, the filter will return an empty string. It is compatible with other Lua Filters such as [citation-backlinks](https://github.com/tarleb/citation-backlinks), which must come AFTER `citefield` in the filter list, [and other great Lua filters](https://github.com/pandoc-ext?type=source).

The filter modifies the internal document representation; it can be used with many publishing systems that are based on Pandoc.

### Plain pandoc

Pass the filter to pandoc via the `--lua-filter` (or `-L`) command
line option.

    pandoc --lua-filter citefield.lua ...

### Quarto

Users of Quarto can install this filter as an extension with

    quarto install extension bcdav/citefield

and use it by adding `citefield` to the `filters` entry
in their YAML header.

``` yaml
---
filters:
  - citefield
---
```

### R Markdown

Use `pandoc_args` to invoke the filter. See the [R Markdown
Cookbook](https://bookdown.org/yihui/rmarkdown-cookbook/lua-filters.html)
for details.

``` yaml
---
output:
  word_document:
    pandoc_args: ['--lua-filter=citefield.lua']
---
```

License
------------------------------------------------------------------

This pandoc Lua filter is published under the MIT license, see
file `LICENSE` for details.
