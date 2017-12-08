
1. Для включения устаревших версий Internet Explorer в список поддержки, заставляющий их понимать весь CSS-код,
применяемый к HTML5-элементам. Перед закрывающим тегом </head> поместить код 
```
<!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/html5shiv/3.7.3/html5shiv.min.js"></script>
<![endif]-->
```
