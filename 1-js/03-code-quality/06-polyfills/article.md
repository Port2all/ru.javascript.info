
# Полифилы

JavaScript - динамично развивающийся язык программирования. Регулярно появляются новые предложения, они анализируются, и, если предложения одобряются, их переносят в черновик <https://tc39.github.io/ecma262/>, а затем публикуют в [спецификации](http://www.ecma-international.org/publications/standards/Ecma-262.htm).

Разработчики JavaScript-движков сами принимают решение, какие предложения реализовать в первую очередь. Они могут заранее реализовать функции, которые находятся в черновике, и отложить разработку функций, которые уже перенесены в спецификацию, потому что они менее интересны разработчикам, а может, их сложнее реализовать.

Таким образом, довольно часто реализуется только часть стандарта.

Можно проверить текущее состояние поддержки различных возможностей JavaScript на странице <https://kangax.github.io/compat-table/es6/> (нам ещё предстоит изучить многое из этого).

## Babel

Когда мы используем современные возможности JavaScript, некоторые движки могут не поддерживать их. Как и было сказано выше, не везде реализованы все функции.

И тут приходит на помощь Babel.

[Babel](https://babeljs.io) - это [транспилер](https://ru.wikipedia.org/wiki/%D0%A2%D1%80%D0%B0%D0%BD%D1%81%D0%BF%D0%B0%D0%B9%D0%BB%D0%B5%D1%80). Он переписывает современный JavaScript-код в предыдущий стандарт.

На самом деле, есть две части Babel:

1. Во-первых, транспилер, который переписывает код. Разработчик запускает Babel на своём компьютере. Он переписывает код в старый стандарт. И после этого код отправляется на сайт. Современные сборщики проектов, такие как [webpack](http://webpack.github.io/) или [brunch](http://brunch.io/), предоставляют возможность запускать транспилер автоматически после каждого изменения кода, что позволяет экономить время.

2. Во-вторых, полифил.

    Новые возможности языка могут включать встроенные функции и синтаксические конструкции. Транспилер переписывает код, преобразовывая синтаксические конструкции в старые. Но что касается новых встроенных функций, нам нужно их реализовать. JavaScript является высокодинамичным языком, скрипты могут добавлять/изменять любые функции, чтобы они вели себя в соответствии с современным стандартом.

    Термин "полифил" означает, что скрипт "заполняет" пробелы и добавляет современные функции.

    Два интересных полифила:
    - [core js](https://github.com/zloirock/core-js) поддерживает много функций, можно подключать только нужные.
    - [polyfill.io](http://polyfill.io) - сервис, который автоматически создаёт скрипт с полифилом в зависимости от необходимых функций и браузера пользователя.

Таким образом, чтобы современные функции поддерживались в старых движках, нам надо установить транспилер и добавить полифил.

## Примеры в учебнике


````online
Большинство примеров можно запустить "на месте", как этот:

```js run
alert('Нажмите кнопку "Play" в крайнем правом углу, чтобы запустить пример');
```

Примеры, в которых используются современные возможности JS, будут работать, если ваш браузер их поддерживает.
````

```offline
Вы читаете оффлайн-версию, примеры в PDF запустить не получится, в EPUB некоторые работают.
```

Google Chrome обычно поддерживает современные функции, можно запускать новейшие примеры без каких-либо транспилеров, но и другие современные браузеры также хорошо работают.
