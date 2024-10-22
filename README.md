# Experiment 21
# Aim:
To study and implement Searching.

# Theory:
Searching is a process of finding the location of a given element or value within a collection of data. We will be understanding 2 types of searching which are:
→ Linear Search
→ Binary Search


Linear Search: In a linear search, the elements of the collection are examined one after another until the sought element is discovered or the search is over. This algorithm does not consider the arrangement of the data. It has a time complexity of O(n), where n is the total number of elements in the set.
Linear Search Steps:

Start at the first element of the array.
Compare the target element with the current element.
If they match, return the index of the current element.
If not, move to the next element.
Continue this process until the element is found or the end of the array is reached.

Binary Search: Although binary search is a much better algorithm, it is restricted to only working on collections which are sorted in some order. Basically, the idea is to split the given array into two halves and figure out whether the required element lies in the left half or the right half, and so on.It has a time complexity of O(log n), where n is the size of the data available.
Binary Search Steps:

Start by comparing the target element with the middle element of the array.
If the target element matches the middle element, return the index.
If the target element is smaller, repeat the search on the left half of the array.
If the target element is larger, repeat the search on the right half of the array.
Continue this process until the target element is found or the sub-array is reduced to size zero.


# Code:

a.
```
#include <iostream>
using namespace std;

int linsearch(int a[], int n, int x)
{
    for (int i = 0; i < n; i++)
        if (a[i] == x)
            return i;
    return -1;
}

int main(void)
{
    int a[] = { 21, 36, 44, 10, 57 };
    int x = 10;
    int n = sizeof(a) / sizeof(a[0]);


    int res = linsearch(a, n, x);
    (res == -1)
        ? cout << "Element is not present in aay"
        : cout << "Element is present at index " << res;
    return 0;
}
```

b.
```
#include <iostream>
using namespace std;

int binsearch(int a[], int low, int high, int x)
{
    while (low <= high) 
    {
        int mid = low + (high - low) / 2;

        if (a[mid] == x)
            return mid;

        if (a[mid] < x)
            low = mid + 1;

        else
            high = mid - 1;
    }

    return -1;
}

int main(void)
{
    int a[] = { 32, 87, 14, 92, 45 };
    int x = 14;
    int n = sizeof(a) / sizeof(a[0]);
    int res = binsearch(a, 0, n - 1, x);
    if(res == -1) cout << "Element is not present in array";
    else cout << "Element is present at index " << res;
    return 0;
}
```

# Conclusion:

→ We learnt about searching in C++.

→ We learnt the use case of the types of searching in C++.

