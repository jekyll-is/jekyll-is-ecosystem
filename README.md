# Jekyll IS — Экосистема расширений 

> **Модульные плагины для Jekyll.**  
> Один AST. HTML + LaTeX. Без компромиссов.

## Схема зависимостей и состояние

```mermaid
graph RL
  ial["is-ial-parser<br>v0.8.0"]
  kramdown["is-kramdown-hooked<br>v0.8.0"]
  statics["is-static-files<br>v0.8.0"]
  span["jekyll-is-span<br>(0%)"] --> ial
  span --> kramdown
  index["jekyll-is-index<br>(0%)"] --> span
  abbr["jekyll-is-terms<br>(0%)"] --> index
  images["jekyll-is-images<br>(0%)"] --> ial
  images --> kramdown
  images --> statics
  tocs["jekyll-is-tocs<br>(0%)"] --> images
  tocs --> index
  meta["jekyll-is-meta<br>(0%)"] --> images
  feed["jekyll-is-feed<br>(0%)"] --> meta
  robots["jekyll-is-robots<br>(0%)"]
  announcer["jekyll-is-announcer<br>(0%)"] --> statics
  act-announce["action-announce<br>(0%)"] --> announcer
  publish["action-jekyll-publish<br>(0%)"] --> act-announce
  pdf["jekyll-is-pdf<br>(0%)"] --> images

click ial "https://github.com/jekyll-is/is-ial-parser"
click kramdown "https://github.com/jekyll-is/is-kramdown-hooked"
click announcer "https://github.com/jekyll-is/jekyll-is-announcer"
click act-announce "https://github.com/jekyll-is/action-announce"
click publish "https://github.com/jekyll-is/action-jekyll-publish"
click images "https://github.com/jekyll-is/jekyll-is-images"
click robots "https://github.com/jekyll-is/jekyll-is-robots"
click meta "https://github.com/jekyll-is/jekyll-is-meta"
click pdf "https://github.com/jekyll-is/jekyll-is-pdf"
click tocs "https://github.com/jekyll-is/jekyll-is-tocs"
click feed "https://github.com/jekyll-is/jekyll-is-feed"
click index "https://github.com/jekyll-is/jekyll-is-index"
click span "https://github.com/jekyll-is/jekyll-is-span"
click abbr "https://github.com/jekyll-is/jekyll-is-terms"
click statics "https://github.com/jekyll-is/is-static-files"

classDef green fill:#DFD
classDef gray fill:#EEE
classDef blue fill:#DDF

class ial blue
class kramdown blue
class images gray
class announcer green
class act-announce green
class publish gray
class pdf gray
class span gray
class index gray
class feed gray
class meta gray
class robots gray
class tocs gray
class abbr gray
class statics blue
```

---

**Автор**: [Ivan Shikhalev](https://github.com/shikhalev)  
