---
title: Bubble sort
tags: utility
expertise: beginner
cover: https://miro.medium.com/max/720/0*lq-ZpDYjvYGmS7PO
---

Bubble Sort

- Make a nested loop of boundations len-1 and len-i-1.
- Compare two consecutive elements if first > second swap the elements.
- After len - 1 iterations it is sorted.
- len = length of array
- time complexity: O(n^2) space complexity: O(1)

```cpp
void swap(int* a, int* b){
    *a=*a-*b;
    *b=*a+*b;
    *a=*b-*a;
}
void bubbleSort(int arr[], int len){
    for(int i=0; i<len-1; i++){
        for(int j=0;j< len-i-1;j++){
            if(arr[j]>arr[j+1]) swap(&arr[j],&arr[j+1]);
        }

    }
}
```

```cpp
int main(){
    int a[]= {5,3,4,1,2,7,6};
    bubbleSort(a,7);
    for(int k=0;k<7;k++) {cout<<a[k]<<" ";}

}
```
