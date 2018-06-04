#PHP 7

# Better  performance

- Optimizations and lower memory usage
- Roughty twice as fast
- Handle twice as many requests with a single server
- Could need half as many servers in data centers
- Faster than HipHop Virtual Machine (HHVM)

## http://www.zend.com/en/resources/php7_infographic

# Scalar Type Declarations

- Specify the type of function arguments
- 'Type hinting'
- Three techniques: none, coercive, and strict

---------------------------------------

## None
 uses value as passed in
 
 ```PHP
 function sum($a, $b) {
     $result = $a + $b;
     echo $a ." ".gettype($a) ." + ". $b . " ". gettype($b) ." = ".$result ." ". gettype($result);
 }
 ```

 sum(2,3);
 // 2 integer + 3 integer =  5 integer

 sum("2", "3");
 // 2 string + 3 string = 5 integer

 sum(2.0, 3.0);
 // 2 double + 3 double = 5 double

----------------------------------------

### Scalar Type
## Coercive
 immediately coerces value

 ```PHP
 function sum(int $a, int $b) {
     $result = $a + $b;
     echo $a ." ".gettype($a) ." + ". $b . " ". gettype($b) ." = ".$result ." ". gettype($result);
 }
 ```
 
 sum(2,3);
 // 2 integer + 3 integer =  5 integer

 sum("2", "3");
 //  2 integer + 3 integer =  5 integer

 sum(2.0, 3.0);
 //  2 integer + 3 integer =  5 integer

---------------------------------------

## Strict
 raises error if type does not match

 ```PHP
 declare(strict_types=1)
 function sum(int $a, int $b) {
     $result = $a + $b;
     echo $a ." ".gettype($a) ." + ". $b . " ". gettype($b) ." = ".$result ." ". gettype($result);
 }

 sum(2,3);
 // 2 integer + 3 integer =  5 integer

 sum("2", "3");
 //  TypeError: Argument must be of the type integer, string given

 sum(2.0, 3.0);
 // TypeError: Argument must be of the type integer, float given
 ```

Other types : array, bool, float, int and string


