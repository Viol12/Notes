# Примеры кода

## JavaScript ( jQuery )

#### Изменяем каждое второе слово в строке взятой из HTML тега по классу ".slider-title"

```js
  $(".slider-title").html(function(index, value) {
    return strEven = value.replace(/\b(\w+)\b/g, function(i) {
      return function() {
        if (i++ % 2) {
          return '<span class="' + 'slider-title_red' + '">' + arguments[1] + '</span>';
        } return arguments[1]
      };
    }(0));
  });
```


#### Изменяем класс элемента по клику на другой элемент

```js
  $(".menu-button").click(function() {
    $(".menu").toggleClass("menuOpen");
  });
```
