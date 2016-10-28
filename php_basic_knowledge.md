#PHP

##Important functions

1. isset() Determine if a variable is set and is not NULL
2.  empty() Determine is a variable is empty
3. print\_r() and var_dump() will both generate variable information even if it is an array
4. var_dump(var) : display the details of a var

##String

1. strlen() Get string length
2. $str{index} is the same as charAt(index) as java
3. substr($str, start, length)
4. strval() -You can convert to a string with the (string) cast or the strval function Booleans are converted to strings as "1" or "" (empty string).
5. split string: 

```
Same effect, note the difference
$strArr = preg_split("/\s+/", trim($str));
$strArr = explode(" ", trim($str));
```

##Array
1. is_array() Finds whether a variable is an array
2. array\_key\_exists("key", $array): To check whether a key exists or not in php array
3. bool in\_array("value", $array)
4. array_flip(array input):  swaps the keys and values of the array input. All values from input must be valid keys (integer or string).If a value occurs more than once, the latest key will be used as its value and all others will be thrown away.
5. array_pop($arr) will delete the last array element from the array and return it. Will **return null** when the array becomes empty
6. array_slice($array, startIndex, length)-- from start and last length
7. array_slice($array, startIndex) ---from start to the end
8. array_merge($arr1, $arr2) remember to assign return value to a new $arr
9. array_fill(startIndex, number of elements, value); just like fill 10 0s into empty array $arr = array_fill(0, 10, 0);
10. count() Counts all elements in an array, or something in an object.
11. unset($array[index]) - remove an array element

##Array Sort
1. asort($arr) sort array by value in asending order.
   ***This is associateive sort,which means the index will not change accordingly, and it will become a problem when you want to loop it***

2. arsort($arr) sorts an associative array in descending order, according to the value.
3. sort($ARR) **This is the general array sorting method you are looking for**
4. krsort($arr) sorts an associative array in descending order by key.

##Comparing Objects
 Objects can, like arrays, be compared using the ==, !=, === (identical), and !== (not identical) operators. Two objects are equal if they have the same attributes and values and are instances of the same class.