
# SQL - order of execution

1. FROM
2. JOIN
3. WHERE
4. GROUP BY
5. Aggregate Functions (SUM, COUNT, AVG...)
6. HAVING
7. WINDOW FUNCTIONS
8. SELECT
9. DISTINCT
10. UNION / INTERSECT / EXCEPT
11. ORDER BY
12. LIMIT / OFFSET


# Space Complexity
* Space complexity measures the total amount of extra memory or storage algorithm needs to run to completion relative to the input size.
  
1.  O(1) - Constant Space:
* If you modify data in place or only use a few variables, the memory footprint stays the same regardless of input size.

```js
function sumArray(arr){
   let total 0; // Uses exactly one memory slot for 'total'
    for(let i =0; i< arr.length; i++){
       total += arr[i];
      }
   return total; // No extra arrays or structures created
}
```
2. O(n) - Linear Space:
* If you create a duplicate copy of the incoming data, your memory usage grows hand in hand with the input size.

```js

function cloneArray(arr){
   let newArr = [];
   for(let i = 0 i < arr.length; i++){
     newArr.push(arr[i]);
 }
  return newArr;
}
```

