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
#### Pipe
Apply any given function to the collection
```php
Collection::macro('pipe', function ($callback) {
    return $callback($this);
});
```
** Source [adamwathan's book](http://adamwathan.me/refactoring-to-collections/)

#### toAssoc
Given a collection of pairs, turn it into a key => value collection
```php
Collection::macro('toAssoc', function () {
    return $this->reduce(function ($items, $pair) {
        list($key, $value) = $pair;
        return $items->put($key, $value);
    }, new static);
});
```
**Source: [adamwathan](https://gist.github.com/adamwathan/a04873b44a1dcd0f2b4257168499162c)**

#### Transpose
```php
Collection::macro('transpose', function () {
    $items = array_map(function (...$items) {
        return $items;
    }, ...$this->values());

    return new static($items);
});
```
**Source: [adamwathan](http://adamwathan.me/2016/04/06/cleaning-up-form-input-with-transpose/)**
