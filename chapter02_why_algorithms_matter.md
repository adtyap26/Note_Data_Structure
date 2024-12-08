---
title: chapter02 note for A common sense guide to data structures and algorithms
author: Aditya Permana
date: 2023-09-13 14:09
urlcolor: 'blue'
---

# Why algorithms Matter

- Choosing the "right" algorithms to use is always matter, because there are maybe a lot of ways of doing something in particular. But in the term of speed or we often say it step, is important.

### Ordered Array

#Step 1: Compare 25 with the first element (5)
| 5 | 10 | 20 | 30 | 50 |

#Step 2: Compare 25 with the second element (10)
| 5 | 10 | 20 | 30 | 50 |

#Step 3: Compare 25 with the third element (20)
| 5 | 10 | 20 | 30 | 50 |

#Step 4: Compare 25 with the fourt element (30), found 30 > 25 !!
| 5 | 10 | 20 | 30 | 50 |

#Step 5: move the final element (50) to the right to make a room
| 5 | 10 | 20 | 30 | | 50 |

#Step 6: move the fourt element (30) to the right to make a room
| 5 | 10 | 20 | | 30 | 50 |

#Step 7: insert our number 25
| 5 | 10 | 20 | _25_ | 30 | 50 |


- Linear Search for ordered array

```go

func linear_search(arr []int, value int) int {
    for i := 0; i < len(arr); i ++ {
        if arr[i] == value {
            return arr[i]
        } else if arr [i] > value {
            break //stop the search
        }
    }
    return -1 // value not found
}
func main() {
    numberArr := []int {5, 10, 20, 30, 50}
    valueTarget := 15

    resutlArr := linear_search(numberArr, valueTarget)

    if resutlArr == -1 {
        fmt.Println("Value not found")
    } else {
        fmt.Println("Found: ", resutlArr)

}

}

```

- Binary Search (Only available for ordered array)

#step 1: We begin the search in the central cell since we already know the length of an array.
we search for number 4.

| ?   | ?   | ?   | ?   | ?   | [6] | ?   | ?   | ?   | ?   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

Since we uncovered value 6, we can conclude that 4 is somewhere to its left. them we automatically eliminated cell to the right of 6 (include the 6 itself)

#step 2: Among the celss to the left of the 6, we inspect the middlemost value. Now we reveal another number, which 3 that lower than our target. So since we know that 4 is always next to 3 to the right, we eliminated 3 and its left cells.

| ?   | ?   | 3   | ?   | ?   |
| --- | --- | --- | --- | --- |

#step 3: There are two more cells where the 4 can be. We arbitrarily choose the left one:

| 4   | ?   |
| --- | --- |

We've found 4 in just 3 step.

```go

func binarySearch(array []int, value int) int {

	lowerBound := 0
	upperBound := len(array) -1 

	for lowerBound <= upperBound {
		midPoint := (lowerBound + upperBound) / 2 
		valueMidPoint := array[midPoint]

		if value < valueMidPoint {
			upperBound = midPoint -1 
		} else if value > valueMidPoint {
			lowerBound = midPoint + 1
		} else if value == valueMidPoint {
			return midPoint 
			
		}
	}
	
		return -1 
}

```

