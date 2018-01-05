# Numphp

Numphp - designed to be as convenient as [numpy](http://www.numpy.org/).

Contributions as highly appreciated.

## Available features


* get item by index
* get items by array of indexes
* get items by condition
  * eq - equals
  * gt - greater than
  * gte - greater than or equals
  * lt - less than
  * lte - less than or equals
  * neq - not equals
* get items by conditions
  * b_and - logical AND
  * b_or - logical OR

np_array is also has classical array behaviour. So you are able to iterate through it as usual.

## Usage examples

**create new array**
```
$list = new np_array([18, 25, 26, 30, 34]);
```

**get items by their indexes**

```
$result = $list[[2,3]];

// result
Array
(
    [0] => 26
    [1] => 29
)
```

To get item as single value - pass index as single value as well

```
$result = $list[1];

// result
25
```

**get items by condition**

```
$result = $list[$list->gt(25)];

// result
Array
(
    [0] => 26
    [1] => 29
    [2] => 30
    [3] => 34
)
```


**get items by conditions**

*b_and* - "bitwise" and

```
$resuilt = $list[operator::b_and($list->gt(25), $list->lt(30))];

// result
Array
(
    [0] => 26
    [1] => 29
)
```

**array-like behaviour**

You may also iterate your np_array object as usual

```
foreach ($list as $item) {
    echo $item . " ";
}

// output
18 25 26 29 30 34
```

