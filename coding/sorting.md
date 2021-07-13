# Sorting

## Stability

Stable sorting means that order of elements in array is preserved.

## Bubble

Iteration over a list and swappig numbers out of order, worst case O(n^2).

## Insertion

Inserting numbers at the correct places in the array. Best case is O(n) (sorted array or for nearly sorted array), worst case O(n^2).

## Merge

Recursive, stable sorting algorithm. Takes a big list and breaks it down into smaller list until it goes to a list of one. O(nlogn) for all cases. Spacial complexity is O(n).

## Quick sort

Recursive, unstable sorting algorithm. Chooses a pivot constructs two lists - one list with numbers smaller than pivot, one with numbers bigger than pivot.

### Pivot problem

Usual quick sort does not bode well with sorted list. Can reach O(n^2) time complexity. There is a lot of variation of quick sorts.

- Random Quick Sort
- Quick Sort 3 - takes first element, last element and middle element and picks the medium value
