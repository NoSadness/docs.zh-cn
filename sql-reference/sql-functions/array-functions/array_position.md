# array_position

## description

### Syntax

```Haskell
array_position(any_array, any_element)
```

获取数组中某个元素位置，是的话返回位置，否则返回0.

## example

```plain text
mysql> select array_position(["apple","orange","pear"], "orange");
+-----------------------------------------------------+
| array_position(['apple','orange','pear'], 'orange') |
+-----------------------------------------------------+
|                                                   2 |
+-----------------------------------------------------+
1 row in set (0.01 sec)
```

也可以获取数组NULL的位置

```plain text
mysql> select array_position([1, NULL], NULL);
+--------------------------------+
| array_position([1,NULL], NULL) |
+--------------------------------+
|                              2 |
+--------------------------------+
1 row in set (0.00 sec)
```

也可以应用在多维数组中, 获取某个子数组的位置，此时要求子数组元素完全匹配，包括元素排列顺序

```plain text
mysql> select array_position([[1,2,3], [4,5,6]], [4,5,6]);
+--------------------------------------------+
| array_position([[1,2,3],[4,5,6]], [4,5,6]) |
+--------------------------------------------+
|                                          2 |
+--------------------------------------------+
1 row in set (0.00 sec)

mysql> select array_position([[1,2,3], [4,5,6]], [4,6,5]);
+--------------------------------------------+
| array_position([[1,2,3],[4,5,6]], [4,6,5]) |
+--------------------------------------------+
|                                          0 |
+--------------------------------------------+
1 row in set (0.00 sec)
```

## keyword

ARRAY_POSITION,ARRAY
