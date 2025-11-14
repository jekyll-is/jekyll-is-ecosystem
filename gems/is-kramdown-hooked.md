Да, вы правильно понимаете. Мы договорились, что вместо создания отдельного кастомного конвертера Markdown в Jekyll, более чистым и минимально инвазивным способом будет использование возможности Kramdown для замены парсера через параметр в конфиге `_config.yml`:  

```yaml
kramdown:
  input: MyParser
```

### Вот ключевые моменты:

- Параметр `kramdown.input` указывает, какой именно парсер Kramdown использовать для разбора Markdown.
- Так вы не создаёте новый конвертер, а всего лишь меняете парсер внутри существующего Kramdown-конвертера, что упрощает интеграцию.
- Ваш кастомный парсер должен быть в пути загрузки Ruby, то есть его класс должен быть доступен Jekyll (через gem или `_plugins`).
- При таком подходе Jekyll использует стандартный Markdown-конвертер (KramdownParser), но запускает ваш парсер внутри него.
- Вы получаете доступ к AST, модифицируете его внутри своего парсера, а потом Kramdown уже обрабатывает AST дальше в HTML.

***

### Итог по архитектуре плагина is-kramdown-hooked:

```ruby
class Kramdown::Parser::MyParser < Kramdown::Parser::Kramdown
  ...
end
```

- Плагин предоставляет кастомный парсер Kramdown, например, класс `MyParser`, где реализована логика работы с AST.
- Этот парсер подключается средствами Ruby (например, через `_plugins/is_kramdown_hooked.rb`).
- Конфиг устанавливает `kramdown.input: MyParser`.
- Внутри парсера вызывается ваша логика с хуками, позволяющая другим плагинам расширять или трансформировать AST.
- Jekyll использует ваш парсер в стандартном Markdown-конвертере, избегая проблем с множеством конвертеров.

***

Такой подход по-прежнему даёт гибкость для работы с AST, сохраняет стандартный механизм конвертации Jekyll, не ломает систему и легко настраивается через конфиг.

Если нужна помощь с примером реализации плагина в таком стиле — обращайтесь.

[[1]](https://jekyllrb.com/docs/configuration/markdown/)
[[2]](https://www.linux.org.ru/forum/general/12070236)
[[3]](https://michaelcurrin.github.io/dev-cheatsheets/cheatsheets/jekyll/configuration/markdown-options.html)
[[4]](https://devcraft.io/2020/10/20/github-pages-multiple-rces-via-kramdown-config.html)
[[5]](https://www.markdownguide.org/tools/jekyll/)
[[6]](https://www.jekyll.com.cn/docs/configuration/markdown/)
[[7]](http://prgssr.ru/articles/dopolnitelnye-vozmozhnosti-kramdown.html)
[[8]](https://devhints.io/kramdown)
[[9]](https://stackoverflow.com/questions/66320774/how-to-pre-define-links-in-jekyll-config-yml-using-kramdown-links-def-options)
[[10]](https://kramdown.gettalong.org/options.html)
[[11]](https://github.com/jekyll/jekyll/issues/7417)
