# The Gilded Rose

The Gilded Rose is a shop which sells a variety of fantastical items. As such, it needs an equally fantastic inventory management system. Our current system has a variety of rules:

* All items have a `sell_in` value which denotes the number of days we have to sell the item.
* All items have a `quality` value which denotes how valuable the item is.
* At the end of each day our system runs the `update_quality` method on each item, which lowers both values for every item by 1.
* Once the `sell_in` date has passed, quality degrades twice as fast.
* The quality of an item is never negative.
* The quality of an item is never more than 50.

Certain items have special exceptions:

* "Aged Brie" actually increases in quality the older it gets.
* "Sulfuras, Hand of Ragnaros", being a legendary item, never has to be sold or decreases in quality.
* "Backstage passes to a TAFKAL80ETC concert" are very time-sensitive:
  * Like "Aged Brie", they increase in `quality` as their `sell_in` value approaches
  * Its quality increases by 2 when there are 10 days or less
  * Its quality increases by 3 when there are 5 days or less
  * Its quality drops to 0 after the concert, once the sell_in date is past

## The challenge

We have recently signed a supplier of conjured items, which requires an
update to our system. We'd like you to add a "Conjured Mana Cake" item
which degrades in quality twice as fast as normal items.

Failing specs have been added to help describe this behaviour. You may
assume that the test coverage is 100%. In other words, if the tests pass,
the code is perfectly functional. You may make any changes you'd like to
the specs, but keep in mind that you shouldn't reduce coverage.
