

|title  | tags | expertise |
| -------- | -------- | -------- |
| Sorting     | Counting Sort     | Intermediate     |

```cpp
#include <bits/stdc++.h>
#define RANGE 100

using namespace std;
void countingSort(int arr[], int n)
{
    int count[RANGE] = {0};
    int i;
    int out[n];

    for (i = 0; i < n; i++)
        ++count[arr[i]];

    for (i = 1; i < RANGE; i++)
        count[i] += count[i - 1];

    for (i = n - 1; i >= 0; i--)
    {
        out[count[arr[i]] - 1] = arr[i];
        --count[arr[i]];
    }

    for (i = 0; i < n; i++)
        arr[i] = out[i];
}
void print(int arr[], int n)
{
    cout << "Sorted array : ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << ' ';
    cout << endl;
}

int main()
{

    int n;
    cout << "Enter size of array(max. 100): ";
    cin >> n;

    int nums[n];
    for (int i = 0; i < n; i++)
    {
        cin >> nums[i];
    }

    countingSort(nums, n);
    print(nums, n);

    return 0;
}
```
