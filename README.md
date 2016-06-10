## A Pile Of Macros

This is just a list of Laravel's macro found here and there. Feel free to add yours!

Laravel's macroable classes are:


[Collection](#collection)


### Collection

#### Count Recursive
```php
Collection::macro('countRecursive', function () {
    return count($this->items, COUNT_RECURSIVE);
});
```
**author: krzystof**

