# 1st-2nd-third-largest
```
#include <stdio.h>
#include <limits.h> // For INT_MIN

void findThreeLargest(int arr[], int size) {
    if (size < 3) {
        printf("Array size should be at least 3\n");
        return;
    }

    int first, second, third;
    first = second = third = INT_MIN;

    for (int i = 0; i < size; i++) {
        if (arr[i] > first) {
            third = second;
            second = first;
            first = arr[i];
        } else if (arr[i] > second && arr[i] != first) {
            third = second;
            second = arr[i];
        } else if (arr[i] > third && arr[i] != second && arr[i] != first) {
            third = arr[i];
        }
    }

    printf("1st largest: %d\n", first);
    printf("2nd largest: %d\n", second);
    printf("3rd largest: %d\n", third);
}

int main() {
    int arr[100], size;

    printf("Enter the size of the array (max 100): ");
    scanf("%d", &size);

    printf("Enter %d elements:\n", size);
    for (int i = 0; i < size; i++) {
        scanf("%d", &arr[i]);
    }

    findThreeLargest(arr, size);

    return 0;
}
```
//
// Created by Suprakash Ghosh on 12-08-2025.
//
