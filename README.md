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
 Uses value as passed in
 
 ```PHP
 function sum($a, $b) {
     $result = $a + $b;
     echo $a ." ".gettype($a) ." + ". $b . " ". gettype($b) ." = ".$result ." ". gettype($result);
 }


 sum(2,3);
 // 2 integer + 3 integer =  5 integer

 sum("2", "3");
 // 2 string + 3 string = 5 integer

 sum(2.0, 3.0);
 // 2 double + 3 double = 5 double
  ```
  
----------------------------------------

### Scalar Type
## Coercive
 Immediately coerces value

 ```PHP
 function sum(int $a, int $b) {
     $result = $a + $b;
     echo $a ." ".gettype($a) ." + ". $b . " ". gettype($b) ." = ".$result ." ". gettype($result);
 }
 
 
 sum(2,3);
 // 2 integer + 3 integer =  5 integer

 sum("2", "3");
 //  2 integer + 3 integer =  5 integer

 sum(2.0, 3.0);
 //  2 integer + 3 integer =  5 integer
 ```
---------------------------------------

## Strict
 Raises error if type does not match

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

---

# Return type declarations 
- Specify the type of function return values
- Three techniques: none, coercive, and strict
- Identifiers as scalar type declarations
   Array, int , bool, float and string
   
## None
```PHP
     function sum($a,$b){
       return $a + $b;
    }
```

## Coercive
```PHP
    function sum($a, $b) : int {
      return $a + $b;
    }
 ```
 
 ## Strict
 ```PHP
    declare(strict_types=1);
    function sum($a,$b): String {
      return $a + $b;
    }
 ```   
-------

# Combined Comparison Operator
   #### Comparison Operator
  
   
     ==, ===
     !=, !==
     <, <=
     
    
    
    #### Spaceship Operator <=>
    Used to compare two values
    
    ```
       $swatch_price <=> $rolex_price
       
       Returns -1 when left side is less than right side
       Returns 0 when both sides are equal
       Return 1 when left side is greater than right side
    
    ```
    [Referance](https://tutorials.kode-blog.com/php-7-new-operators).
   
