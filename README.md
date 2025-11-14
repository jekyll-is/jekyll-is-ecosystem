# Jekyll IS — Экосистема расширений 

> **Модульные плагины для Jekyll.**  
> Один AST. HTML + LaTeX. Без компромиссов.

```mermaid
graph BT
  images[jekyll-is-images] --> ial[is-ial-parser]
  images --> kramdown[is-kramdown-hooked]
  announcer[jekyll-is-announcer] --> meta
  pdf[jekyll-is-pdf] --> images
  meta[jekyll-is-meta] --> images
  feed[jekyll-is-feed] --> meta
  span[jekyll-is-span] --> ial
  index[jekyll-is-index] --> span
  span --> kramdown
  tocs[jekyll-is-tocs] --> kramdown
  robots[jekyll-is-robots]

click ial "https://github.com/jekyll-is/is-ial-parser"
click kramdown "https://github.com/jekyll-is/is-kramdown-hooked"
click announcer "https://github.com/jekyll-is/jekyll-is-announcer"
click images "https://github.com/jekyll-is/jekyll-is-images"
click robots "https://github.com/jekyll-is/jekyll-is-robots"
click meta "https://github.com/jekyll-is/jekyll-is-meta"
click pdf "https://github.com/jekyll-is/jekyll-is-pdf"
click tocs "https://github.com/jekyll-is/jekyll-is-tocs"
click feed "https://github.com/jekyll-is/jekyll-is-feed"
click index "https://github.com/jekyll-is/jekyll-is-index"
click span "https://github.com/jekyll-is/jekyll-is-span"
```

---

## Что уже есть

| Репозиторий | Описание |
|------------|---------|
| [`jekyll-is-ecosystem`](.) | Этот репозиторий — документация, архитектура, примеры |

> Остальные плагины — **в разработке**.

---

## Планы (Roadmap)

| Этап | Репозитории | Статус |
|------|------------|--------|
| 1 | `is-ial-parser` | Планируется |
| 2 | `jekyll-is-span` | Планируется |
| 3 | `jekyll-is-figure` | Планируется |
| 4 | `jekyll-is-pdf-book` | Планируется |

[Подробнее → `ROADMAP.md`](ROADMAP.md)

---

## Архитектура (будущая)

[Подробнее → `ARCHITECTURE.md`](ARCHITECTURE.md)

---

**Автор**: [Ivan Shikhalev](https://github.com/shikhalev)  
**Лицензия**: [MIT](LICENSE)
