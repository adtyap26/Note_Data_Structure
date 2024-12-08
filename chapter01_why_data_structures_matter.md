---
title: chapter01 note for A common sense guide to data structures and algorithms
author: Aditya Permana
date: 2023-09-13 14:09
urlcolor: 'blue'
---

# Chapter 1

### Why Data Structures Matter

- Data structures refer to how data is organized.

```python
x = "Hello"
y = "How are you"
z = "today?"

print(x + y + z)
```

A data structure can significantly impact the speed at which the code you write executes.

---

### The Array: The Foundational Data Structure

Example of an array:

| "Apple" | Banana  | Cucumber | Dates   | Elderberries |
| ------- | ------- | -------- | ------- | ------------ |
| index 0 | index 1 | index 2  | index 3 | index 4      |

Most data structures perform four basic operations on arrays:

1. **Read**

   - The computer requires only one step to read an array. This is because, when an array is created, the computer allocates contiguous memory blocks for it. These blocks already have their "addresses" stored. Additionally, since arrays start at index 0, the computer can easily locate and read the desired data.

   **One Step**

2. **Search**

   - Unlike humans, who can visually locate an item in an array in one step, computers must search systematically. For example, using a linear search method, the computer checks each element in the array one by one. If the task is to find "Dates" in the array above, the computer would take a total of 4 steps to locate it.

If the array is ["Apple", "Banana", "Cucumber", "Dates", "Elderberries"] and the task is to find "Dates":

    Step 1: Check index 0 ("Apple" - not a match).
    Step 2: Check index 1 ("Banana" - not a match).
    Step 3: Check index 2 ("Cucumber" - not a match).
    Step 4: Check index 3 ("Dates" - match found).

**Linear search will take a maximum of N steps, where N is the number of elements in the array.**

3. **Insert**

   - The efficiency of adding an item to an array depends on where the item is inserted. If it’s added at the end of the array, the computer needs just one step, as it already knows the total number of elements and their addresses.

   - However, inserting an item at the beginning or middle of an array requires shifting other elements to make space.

   **In the worst-case scenario, insertion can take up to N + 1 steps for an array with N elements.**

   - 1 step for inserting the new data.
   - N steps for shifting the elements.

4. **Delete**

   - Deleting an item requires only one step, but an array cannot have empty indices. Therefore, the computer must shift the remaining elements to fill the gap.

   - For example, if an array has 500 elements, deletion requires 1 step to remove the item and 499 steps to shift the remaining elements.

   **For an array with N elements, deletion can take up to N steps.**

---

**Note:** The efficiency of an algorithm is measured not by the time it takes to execute but by the number of steps required to complete the task.

---

### Sets: How a Single Rule Can Affect Efficiency

- A set is a type of data structure that operates like an array but with a strict rule: it does not allow duplicate elements.

1. **Read**

   - The algorithm for reading in a set is the same as in an array. The computer can read directly because it already knows the address of each element.

2. **Search**

   - Similar to search operations in an array.

3. **Delete**

   - Identical to delete operations in an array.

4. **Insert**

   - Insertion in a set differs slightly. Even in the best-case scenario (e.g., inserting at the end), the computer must scan for duplicates before completing the insertion.

   **Best-case scenario:** Insertion takes **N + 1 steps** for a set with N elements.

   - 1 step for the insertion.
   - N steps to check for duplicates.

   - The worst-case scenario is more complex. If an item is to be inserted at the beginning (index 0), the computer must:
     1. Scan for duplicates.
     2. Shift elements to make space.
     3. Insert the new item.

   **Worst-case scenario:** Insertion takes **2N + 1 steps**.
