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

#### Меняем число в input +1 -1 по нажатию на кнопки. 

```js
module.exports = {
    init: function() {
        this.cache();
        this.events();
    },

    cache: function() {
        this.settings = {
            container: '.js-qty-container',
            input: '.js-qty-input',
            btn: '.js-qty-change'
        };

        this.$document  = $(document);
        this.$container = $(this.settings.container);
        this.$input     = $(this.settings.input);
    },

    events: function() {
        this.$document
            .off('change', this.settings.input)
            .on('change', this.settings.input, this.onChange.bind(this));

        this.$document
            .off('click', this.settings.btn)
            .on('click', this.settings.btn, this.onBtnClick.bind(this));
    },

    onChange: function(ev, additionalValue) {
        var $target = $(ev.currentTarget),
            currentValue,
            value;

        ev.preventDefault();
        
        if (additionalValue) {
            currentValue = parseInt($target.val());
            value        = currentValue + additionalValue;
        }

        value = this.validateValue($target, value);
        
        $target.val(value).trigger('qty:change', [value, $target]);
    },

    onBtnClick: function(ev) {
        var $target = $(ev.currentTarget),
            $input;

        ev.preventDefault();

        this.cache();

        $input = $target.closest(this.$container).find(this.$input);

        if ($target.data('dec')) {
            $input.trigger('change', -1);
        } else if ($target.data('inc')) {
            $input.trigger('change', 1);
        }
    },

    validateValue: function($input, value) {
        var val = typeof value !== 'undefined' ? value : $input.val(),
            min = $input.attr('min'),
            max = $input.attr('max');

        val = parseInt(val);
        min = parseInt(min);
        max = parseInt(max);

        min = isNaN(min) ? 1 : min;
        max = isNaN(max) ? Number.MAX_VALUE : max;

        val = val || min;

        if (val < min) {
            return min;
        } else if (val > max) {
            return max;
        }

        return val;
    }
};
```

Разметка
```html
 <div class="qty js-qty-container">
                            <button type="button"
                                    class="qty__btn qty__btn_minus _disabled js-qty-change"
                                    data-dec="1"
                                    data-gtm="Interactions-remove-cartItemQuantity"
                                    data-gtm-item-id="<?php echo $_item->getId(); ?>"></button>

                            <input type="text"
                                   class="qty__input js-qty-input _disabled"
                                   autocomplete="off"
                                   value="<?php echo $this->getQty() ?>"
                                   readonly="readonly"
                                   min="0"
                                   name="cart[<?php echo $_item->getId() ?>][qty]">

                            <button type="button"
                                    class="qty__btn qty__btn_plus _disabled js-qty-change"
                                    data-inc="1"
                                    data-gtm="Interactions-add-cartItemQuantity"
                                    data-gtm-item-id="<?php echo $_item->getId(); ?>"></button>
                        </div>
```
#### Плавный скролл страницы до якоря по нажатию по ссылке с классом ".scrollto"

```js
$(document).ready(function() {
	$("a.scrollto").click(function() {
		var elementClick = $(this).attr("href")
		var destination = $(elementClick).offset().top;
		jQuery("html:not(:animated),body:not(:animated)").animate({
			scrollTop: destination
		}, 800);
		return false;
	});
});
```
