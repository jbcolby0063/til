# Binary Search 

```Binary Search``` is an algorithm that searches a location of target value within a sorted array. 

It uses starting point, mid point, and end point to set the searching range. 

If the target value is less than the mid point value, then the mid point becomes the end point for the new searching range, and if 
the target value is greater than the mid point value, the the mid point becomes the start point for the new searching range. 

You narrow the range down until you find the target value. 

Since ```binary search``` divides the searching range by 2 on every step, the time complexity of this algorithm is O(logN). 
