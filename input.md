---
title: Lorem ipsum
author: Nullus
mainfont: Alegreya
link-citations: true
citeproc: false
filters:
  - citeproc.lua
  - citefield.lua
---

# Citefield Example

## Heading

[@DA; @Trott2014]


author: [@Trott2014]{.author}  
title: [@Trott2014]{.title}  
publisher: [@Trott2014]{.publisher}  
place: [@Trott2014]{.issued}  
page: [@Trott2014]{.page}  
url: [@Trott2014]{.URL}  

author: [@DA]{.author}  
abbreviation: [@DA]{.title-short}  
title: [@DA]{.title}  
origtitle: [@DA]{.original-title}  
pages: [@DA]{.page}  
container: [@DA]{.container-title}  
tlg-code: [@DA]{.call-number}  
publisher: [@DA]{.publisher}  
place: [@DA]{.publisher-place}  
keywords: [@DA]{.keyword}  
date: [@DA]{.issued}  
notes: [@DA]{.notes}

# Bibliography

---
references:
- author:
  - family: Trott
    given: Adriel M.
  id: Trott2014
  issued: 2014
  page: xiii-239
  publisher: CUP
  title: Aristotle on the nature of community
  type: book
  url: "www.google.com"
- author:
  - family: Aristotle
  call-number: "0086.002"
  container-title: Aristotelis opera
  editor:
  - family: Bekker
    given: Immanuel
  id: DA
  issued: 1831
  keyword: primary sources, ancient philosophy, ancient greek
  original-title: Περὶ ψυχῆς
  page: 402a01-435b25
  publisher: Reimer
  publisher-place: Berlim
  title: De anima
  title-short: DA
  type: chapter
  url: "www.google.com"
  notes: |
    On the Soul (Greek: Περὶ Ψυχῆς, Peri Psychēs; Latin: De Anima) is a major treatise written by Aristotle c. 350 BC. His discussion centres on the kinds of souls possessed by different kinds of living things, distinguished by their different operations. Thus plants have the capacity for nourishment and reproduction, the minimum that must be possessed by any kind of living organism. Lower animals have, in addition, the powers of sense-perception and self-motion (action). Humans have all these as well as intellect.
---
