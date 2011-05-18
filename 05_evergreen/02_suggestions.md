!SLIDE purple

# Suggestions

!SLIDE purple

# Write testable code

!SLIDE

## Structure your JS code
## into functions or objects

!SLIDE

## No jQuery DOM spaghetti
## create abstractions

!SLIDE code small

    @@@javascript
    $('#whiskies li').each(function() {
      var li = $(this);
      var price = li.attr('data-price');
      var addLink = $('<a class="add-to-cart" href="#">Add to cart</a>');
      addLink.appendTo(li);

      addLink.click(function() {
        var item = $('<li>' + li.attr('data-name') + '</li>');
        item.appendTo('#cart .list');
        item.append('<span class="price">' + price + '</span>');
        var currentAmount = parseInt($('#cart .total .amount').text());
        var newAmount = currentAmount + parseInt(price);
        $('#cart .total .amount').text(newAmount);
        return false;
      });
    });

!SLIDE code small

    @@@javascript
    var Cart = function(element) {
      this.element = $(element);
      this.list = this.element.find('.list');
      this.total = this.element.find('.total .amount');
      this.items = [];
    };

    Cart.prototype.addItem = function(item) {
      element = $('<li>' + item.name + '<span class="price">' +
        item.price + '</span></li>').appendTo(this.list);
      this.items.push({ name: item.name, price: item.price, });
      this.updateTotal();
    };

    Cart.prototype.updateTotal = function() {
      sum = 0;
      $(this.items).each(function() { sum += this.price });
      this.total.text(sum);
    };

!SLIDE code small

    @@@ruby
    class Cart
      constructor: (element) ->
        @element = $(element)
        @list = @element.find('.list')
        @total = @element.find('.total .amount')
        @items = []

      addItem: (item) ->
        element = $("<li>#{item.name}<span class='price'>" +
          "#{item.price}</span></li>")
        element.appendTo(@list)
        @items.push(name: item.name, price: item.price)
        @updateTotal()

      updateTotal: ->
        sum = 0
        sum += item.price for item in @items
        @total.text(sum)

!SLIDE

## OO makes it familiar,
## Closer to Ruby

!SLIDE

## Try to maintain
## a consistent feel
## to all JS code

!SLIDE

## Separate into files

!SLIDE purple

# Write good tests

!SLIDE

## Always test methods

!SLIDE

## Mostly test event bindings

!SLIDE

## Write custom matchers

!SLIDE

## Isolate AJAX
## to avoid brittle tests

!SLIDE

## Mock AJAX
## if necessary

!SLIDE

## Treat templates as fixtures
## Update them manually

!SLIDE

## Use integration tests
## to validate templates

!SLIDE

## Simplify your DOM
## Simplify your templates

!SLIDE capy6
