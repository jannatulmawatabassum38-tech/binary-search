#include <stdio.h>

int main() {
    int arr[100], n, key;
    
    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter sorted elements:\n");
    for(int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    printf("Enter value to search: ");
    scanf("%d", &key);

    int low = 0, high = n - 1, mid;
    int found = -1;

    while(low <= high) {
        mid = (low + high) / 2;

        if(arr[mid] == key) {
            found = mid;
            break;
        }
        else if(arr[mid] < key) {
            low = mid + 1;
        }
        else {
            high = mid - 1;
        }
    }

    if(found != -1)
        printf("Element found at position %d", found + 1);
    else
        printf("Element not found");

    return 0;
}
