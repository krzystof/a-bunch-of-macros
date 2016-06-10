# A Pile Of Macros
This is just a list of Laravel's macro found here and there. Feel free to add yours!

Laravel's macroable classes are:
* [Collection](#collection)

## Collection

#### Count Recursive
```php
Collection::macro('countRecursive', function () {
    return count($this->items, COUNT_RECURSIVE);
});
```
*by krzystof*

#### Transpose
```php
Collection::macro('transpose', function () {
    $items = array_map(function (...$items) {
        return $items;
    }, ...$this->values());

    return new static($items);
});
```
*by [adamwathan](https://github.com/adamwathan)*

**Source: [Adam Wathan's blog](http://adamwathan.me/2016/04/06/cleaning-up-form-input-with-transpose/)**

