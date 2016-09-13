# Примеры кода

## JavaScript ( jQuery )

#### Изменяем каждое второе слово в строке взятой из HTML тега по классу ".slider-title"

```js
$(".slider-title").html(function (index, value) {
    return strEven = value.replace(/\b(\w+)\b/g, function (i) {
        return function () {
            if (i++ % 2) {
                return '<span class="' + 'slider-title_red' + '">' + arguments[1] + '</span>';
            }
            return arguments[1]
        };
    }(0));
});
```


#### Изменяем класс элемента по клику на другой элемент

```js
$(".menu-button").click(function () {
    $(".menu").toggleClass("menuOpen");
});
```


#### Меняем класс всей колонки в таблице по наведению, кроме первой. #deliveryCost - айдишник таблицы. accentuated - класс, который добавляется к ячейки. 

```js
var $deliveryCost = $('#deliveryCost');

$deliveryCost.find('td').mouseover(function() {
    var tds = $( this ).parent().find('td'),
        index = $.inArray( this, tds );
    if (index !== 0) {
        $deliveryCost.find('td:nth-child('+( index + 1 )+')').addClass( 'accentuated' );
        $deliveryCost.find('th:nth-child('+( index + 1 )+')').addClass( 'accentuated' );
    }
}).mouseout(function() {
    var tds = $( this ).parent().find('td'),
        index = $.inArray( this, tds );

    $deliveryCost.find('td:nth-child('+( index + 1 )+')').removeClass( 'accentuated' );
    $deliveryCost.find('th:nth-child('+( index + 1 )+')').removeClass( 'accentuated' );
});
```
