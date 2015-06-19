# PHP的数组排序组合

创建一个新的空数组，插好要的数据，然后把原来的数组接在后面，用foreach可以，但是弱爆了，不如用＋。

```
<?php
 $original = array('a' => 1, 'b' => 2);
 $new      = array('c' => 3) + $original;
```
这样`$b`的值是
```
var_dump($new);

array('c'=>3,'a'=>1,'b'=>2);
```
