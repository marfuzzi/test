
## 1. 
Для включения устаревших версий Internet Explorer в список поддержки, заставляющий их понимать весь CSS-код,
применяемый к HTML5-элементам. Перед закрывающим тегом </head> поместить код 
```
<!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/html5shiv/3.7.3/html5shiv.min.js"></script>
<![endif]-->
```
Подключение шрифтов
```
<link href='http://fonts.googleapis.com/css?family=Kurale' rel='stylesheet'>
```
---
## 2. Ссылки
*__a:link__* - обозначает любую ссылку, по которой посетитель веб-страницы еще не переходил и на которую не наведен указатель мыши.  
   *__a:visited__* - обозначает любую ссылку, по которой посетитель веб-страницы уже переходил.  
   *__a:hover__* - позволяет изменять вид ссылки, на которую посетитель навел указатель мыши.  
   *__a:active__* - позволяет определить, как будет выглядеть ссылка во время выбора ее посетителем веб-страницы. Другими словами, это стиль во время кратковременного щелчка кнопкой мыши.  
   
## 3. Фрагменты абзаца  
Псевдоэлемент **:first-letter** позволяет создавать буквицу(начальный символ абзаца, который выделяется из остального текста, как в начале книжной главы).
Форматирование первой строки с помощью псевдоэлемента **:first-line** отличным от основного абзаца цветом притягивает посетителей веб-страницы изяществом оформления и простотой визуального восприятия содержимого сайта.
В версии CSS3(новые браузеры могут использовать) ::first-letter и ::first-line.

## 4. Псевдоэлементы и псевдоклассы  
**Псевдоэлементы** позволяют задать стиль элементов не определённых в дереве элементов документа, а также генерировать содержимое, которого нет в исходном коде текста.
Генерация контента на лету: 

   * .tip:before {content: "ПОДСКАЗКА!" }
   * .tip:after {content: "ПОДСКАЗКА!" }      
   * ::selection. Этот селектор, появившийся в CSS3, ссылается на элементы, которые посетитель
выбрал на странице. Например, когда посетитель, нажав и удерживая кнопку мыши
над текстом, перетаскивает указатель мыши, браузер выделяет этот текст и посетитель сможет скопировать выделенный фрагмент.
```
::selection {
color: #FFFFFF;
background-color: #993366;
}
```
С помощью данного селектора можно установить лишь свойства color и  background-
color , поэтому вы не cможете изменить кегль, шрифт, поля и внести другие визуальные
изменения. Этот селектор работает в браузерах Internet Explorer 9, Opera, Chrome и Safari,
но не поддерживается в Internet Explorer 8 или Firefox. Однако вы можете добавить
поддержку для Firefox, дополнив имя селектора так называемым вендорным пре­
фиксом:
```
::-moz-selection {
color: #FFFFFF;
background-color: #993366;
}
```

## 5. Селекторы атрибутов  
* img[title]
* a[href="http://www.cafesoylentgreen.com"]
* a[href^="http://"] - начинается на.
Этот селектор не будет работать при использовании защищенного SSL-соединения, то есть когда
ссылка начинается со значения https://. Чтобы создать стиль, учитывающий данную проблему, вам
понадобится группа селекторов:
a[href^="http://"], a[href^="https://"]
* a[href$=".pdf"] -  заканчивается на
* img[src*="photo"] - выберите все изображения повсюду, атрибут src
которых содержит слово photo

## 6. Дочерние селекторы, псевдоклассы
div h2 - выбор потомка
div>h2 - выбор дочернего элемента
* :first-child
* :last-child
* :only-child
* :nth-child(even, odd, 3n, 3n+3, -n+6)
* first-of-type
* last-of-type
* :nth-of-type(odd, even)

## 7. :target 
Трюки http://prgssr.ru/development/tryuki-s-psevdoklassom-target.html#heading-section
```
<button>
<a href="#signupForm">Подпишитесь на нашу рассылку</a>
</button>
<form id="signupForm">
<label for="email">Укажите свой адрес электронной почты</label>
<input type="email" id="email">
<input class="btn" type="submit" value="Подписаться">
</form>
```
Когда посетитель сайта щелкнет кнопкой мыши на ссылке (элемент a ), форма
станет целевой.
```
#signupForm {
display: none;
}
#signupForm:target {
display: block;
}
```
## 8. Приоритет
!important->style->class->tag  
Переопределить стили можно подключением другого файла со стилями
```
.hit+.miss( если miss сразу после hit)
ul>li (если li-дочка)
ul li (если потомок)
```
---
