# Number Sorter Algorithms JS

simple number sorter implemneted with js and varius sorting algorithms

lesson part of the Javascript Data Structures and Algorithms course from freeCodeCamp 

## Algorithms Used

### Bubble Sort

--> **Compares two adjacent elements and swaps them until they are in the intended order.**

code:

``` javascript
const bubbleSort = (array) => {
  for (let i = 0; i < array.length; i++) {
    for (let j = 0; j < array.length - 1; j++) {
      if (array[j] > array[j + 1]) {
        const temp = array[j];
        array[j] = array[j + 1];
        array[j + 1] = temp;
      }
    }
  }

  return array;
}
```

### Selection Sort

--> **Repeatedly finds the minimum element in the unsorted portion of an array and swaps it with the element at the beginning of the unsorted section.**

``` javascript
const selectionSort = (array) => {
  for (let i = 0; i < array.length; i++) {
    let minIndex = i;

    for (let j = i + 1; j < array.length; j++) {
      if (array[j] < array[minIndex]) {
        minIndex = j;
      }
    }

    const temp = array[i];
    array[i] = array[minIndex];
    array[minIndex] = temp;
  }

  return array;
}
```

### Insertion Sort

--> **Insertion sort is a simple sorting algorithm that builds the final sorted array (or list) one item at a time by comparisons. It is much less efficient on large lists than more advanced algorithms such as quicksort, heapsort, or merge sort.**

``` javascript
const insertionSort = (array) => {
  for (let i = 1; i < array.length; i++) {
    const currValue = array[i];
    let j = i - 1;

    while (j >= 0 && array[j] > currValue) {
      array[j + 1] = array[j];
      j--;
    }
    array[j + 1] = currValue;
  }
  return array;
}
```

### Default JS sort

--> **Javascript has a built in sort method.**

- can be used wuithout parameter (will convert to string and then sort)
- can take in (a,b) paramenter
- returns an int:
    - sorts a before b if value is negative 
    - sorts a after b if value is positive
    - remains same if value is 0 or NaN  
- (a,b) => a-b; will sort in ascending order

```javascript
  const sortedValues = inputValues.sort((a, b) => {
    return a - b;
  });
```