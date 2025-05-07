# Личный проект «Barbershop»

---

_Не удаляйте и не обращайте внимание на файлы:_<br>
_`.editorconfig`, `.gitattributes`, `.gitignore`, `Contributing.md`, `Readme.md`._

---

## 00.Вводная информация

### Как сделать скриншот

Для копирования информации вам могут пригодиться следующие сочетания клавиш:

- `Ctrl + C` — скопировать выделенный участок текста, файл, картинку;
- `Ctrl + V` — вставить то, что скопировали из буфера обмена, в файл или в папку;
- `Ctrl + A` — выделить всё. Это может быть весь текст или все файлы в папке;
- `Ctrl + X` — вырезать. Работает как сочетание Ctrl + C, только файл или текст пропадут из того места, откуда его вырезали

#### Windows 10

Откройте нужное изображение и нажмите кнопку PrtSc (или PrintScreen). Изображение сохранится в буфер обмена.
Откройте графический редактор. Простейший редактор в Windows — это программа Paint. Нажмите кнопку Вставить или комбинацию клавиш `Ctrl + V`.
Сохраните файл в нужную папку.

В Windows 10 также есть возможность сохранять скриншоты сразу, без буфера обмена и манипуляций с графическим редактором. Для этого нужно нажать сочетание клавиш Windows + PrtSc. Скриншот в формате png сохранится в папку Изображения/Снимки экрана. Каждому файлу автоматически присваивается имя с индексом, например: «Снимок экрана (20)», так что найти нужный файл не составит труда.

#### Менеджер буфера обмена

Если вы активно копируете и вставляете тексты, картинки и прочее, особенно это легко делать с помощью сочетаний `Ctrl + C` - `Ctrl + V`, то, возможно, замечали, как хочется вернуться к предыдущему копированию. Такая возможность есть, для этого нужно вызвать системный менеджер буфера обмена с помощью `Windows + V`. В выпадающем списке посмотреть список копирований и выбрать нужное копирование.

#### Linux

Снимок всего экрана в Linux можно сделать точно так же, как в Windows: кнопкой `PrintScreen`.

Снимок части экрана можно сделать с помощью комбинации клавиш `Shift + PrtScr`. Курсор превратится в крестик, и им можно будет выделить область скриншота.

Все скриншоты автоматически сохранятся в папке «Изображения» в формате `png`. Найти нужные файлы очень легко: название начинается со слов «Снимок экрана от» и содержит дату и время снимка.

#### macOS

Чтобы в macOS сделать снимок всего экрана целиком, нажмите кнопки `Command + Shift + 3`. Файл со снимком экрана сохранится на рабочий стол.

В macOS очень легко сделать снимок части экрана. Для этого нужно нажать сочетание кнопок `Command + Shift + 4` и выделить курсором часть экрана.

`a[href*="css"]`       /* Применится к ссылкам, в URL которых есть сочетание букв css */
`a[href^="https://"]`  /* Применится к ссылкам, которые начинаются с https:// */
`a[href$=".jpeg"]`     /* Применится к ссылкам, которые заканчиваются на .jpeg */
`a[type="image/jpeg"]` /* Применится к ссылкам, которые помечены атрибутом type как jpeg или jpg */


Верстка сносок:

```html
<article>
  <h2>Полезное</h2>
  <p>Нумеровать сноски при разметке <a href="#html" class="footnote-label" id="html-ref">HTML</a> страницы  нет необходимости.</p>
  <p>Добавить нумерацию можно с помощью упорядоченного списка и <a href="#css" class="footnote-label" id="css-ref">CSS</a> <a href="#css-counters" class="footnote-label" id="css-counters-ref"> счётчика</a>.</p>
  <footer>
    <h3 class="visually-hidden" id="footnote-label">Сноски</h3>
    <ol>
      <li id="html">HTML (от англ. HyperText Markup Language — «язык гипертекстовой разметки») — стандартизированный язык разметки документов во Всемирной паутине. Большинство веб-страниц содержат описание разметки на языке HTML. Язык HTML интерпретируется браузерами; полученный в результате интерпретации форматированный текст отображается на экране монитора компьютера или мобильного устройства. <a href="#html-ref" class="back">↩</a></li>
      <li id="css">CSS (англ. Cascading Style Sheets — каскадные таблицы стилей) — формальный язык описания внешнего вида документа, написанного с использованием языка разметки.<a href="#css-ref" class="back">↩</a></li>
      <li id="css-counters">CSS счётчики — переменные CSS, значения которых могут быть инкрементированы при помощи CSS для отслеживания количества их использования. Они позволяют регулировать внешний вид контента, основываясь на его местоположении в документе.<a href="#css-counters-ref" class="back">↩</a></li>
    </ol>
  </footer>
</article>

```
```css
body {
  margin: 20px;
  font-size: 125%;
  line-height: 1.4;
  max-width: 600px;
  margin: 0 auto;
}

footer {
  margin-top: 50px;
  border-top: 1px solid silver;
  font-size: 0.8em;
}

footer ol {
  padding-left: 20px;
}

article {
  counter-reset: footnotes;            /* сбрасываем счётчик */
}

.footnote-label {
  counter-increment: footnotes;        /* увеличиваем счётчик для каждой подписи */
  text-decoration: none;               /* убираем подчёркивание для ссылки */
  color: inherit;
  cursor: default;
  outline: none;
}

.footnote-label::after {
  content: '[' counter(footnotes) ']'; /* формируем номер для сноски как `[1]` */
  vertical-align: super;               /* отображаем как верхний индекс */
  font-size: 0.5em;                    /* уменьшаем размер сноски */
  margin-left: 2px;                    /* добавляем внешний отступ */
  color: blue;
  text-decoration: underline;
  cursor: pointer;
}

.footnote-label:focus::after {
  outline: thin dotted;
  outline-offset: 2px;
}

.back {
  font-size: 0.8em;
}

footer :target {
  background: yellow;
}

.visually-hidden {
  position: absolute;
  clip: rect(0 0 0 0);
  visibility: hidden;
  opacity: 0;
}

.p {
  text-align: center;
  font-size: .75em;
  padding-top: 150px;
}

```

Сердце на css:
```css
.heart {
  position: relative;
  width: 100px; 
  height: 80px;
}

.heart:before, 
.heart:after {
  content: "";
  position: absolute; 
  left: 50px; 
  top: 0;
  width: 50px; 
  height: 80px;
  background: red;
  border-radius: 50px 50px 0 0;
  transform: rotate(-45deg); 
  transform-origin: 0 100%;
}

.heart:after {
  left: 0;
  transform: rotate(45deg); 
  transform-origin: 100% 100%;
}

```

Треугольник на css:

```css
.heart {
  position: relative;
  width: 100px; 
  height: 80px;
}

.heart:before, 
.heart:after {
  content: "";
  position: absolute; 
  left: 50px; 
  top: 0;
  width: 50px; 
  height: 80px;
  background: red;
  border-radius: 50px 50px 0 0;
  transform: rotate(-45deg); 
  transform-origin: 0 100%;
}

.heart:after {
  left: 0;
  transform: rotate(45deg); 
  transform-origin: 100% 100%;
}
```

В разных браузерах и в разных операционных системах поведения могут отличаться, поэтому предложенный код может не работать идеально. Лучше всего полностью разделять состояния и каждому давать свою стилизацию.

```css
.selector:hover {}
.selector:focus {}
.selector:active {}
```

Псевдокласс placeholder-shown используется у тегов <input> и <textarea> для отображения стилей в момент, когда в поле отображается плейсхолдер.

```html
<input name="name" type="email" placeholder="example@example.com">

```

```css
input:placeholder-shown {
    background-color: #FFEB3B;
    border: 2px solid #D28100;
    border-radius: 5px;
}
```

А мы можем найти элементы, в которых введён текст?
Да, можем. Попробуем использовать псевдокласс :not(), который меняет логику работы селекторов на противоположную. И если его совместить с псевдоклассом :placeholder-shown, то мы можем найти <input> с текстом. Вот пример:

```html
<input name="name" type="email" placeholder="example@example.com">
```
```css
input:placeholder-shown {
    background-color: #F1E946;
}

input:not(:placeholder-shown) {
    background-color: #F2E1F5;
} 
```
