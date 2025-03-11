### String Paranthesis Validation:
```
def validation(string):
    stack=[]
    maps={"}":"{","]":"[",")":"("}
    for char in string:
        if char in maps:
            top=stack.pop() if stack else "0"
            if maps[char]!=top:
                return False
        else:
            stack.append(char)
            
    return not stack
    
print(validation("((({{[[([{}]{})]]}}})))"))
```

### Linear Search:

```
def linear_search(array,search):
    for i, element in enumerate(array):
        if element == search:
            return i
    return -1 
array=[1,3,4,5,6]
print(linear_search(array,3))
```

### Binary Search:
```
def binary_search(array,search,l,h):
    if l > h:
        return -1
    mid=(l+h)//2
    if search == array[mid]:
        return mid
    elif search>array[mid]:
        return binary_search(array,search,mid+1,h)
    else:
        return binary_search(array,search,l,mid-1)
    
array=[1,3,4,5,6]
print(binary_search(array,5,0,len(array)-1))
```

### Quick Sort:
```
public class Main {
    public static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            int partitionIndex = partition(arr, low, high);
            quickSort(arr, low, partitionIndex - 1);  
            quickSort(arr, partitionIndex + 1, high); 
        }
    }

    private static int partition(int[] arr, int low, int high) {
        int pivot = arr[high];  
        int i = low - 1;  

        for (int j = low; j < high; j++) {
            if (arr[j] < pivot) {  
                i++;
                swap(arr, i, j);
            }
        }
        swap(arr, i + 1, high);  
        return i + 1; 
    }

    private static void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    public static void main(String[] args) {
        int[] arr = {10, 7, 8, 9, 1, 5};
        System.out.println("Original array:");
        printArray(arr);

        quickSort(arr, 0, arr.length - 1);

        System.out.println("Sorted array:");
        printArray(arr);
    }

    private static void printArray(int[] arr) {
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();
    }
}
```

### Merge Sort:
```
public class Main {
    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            int mid = left + (right - left) / 2;

            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);

            merge(arr, left, mid, right);
        }
    }

    private static void merge(int[] arr, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;

        int[] leftArr = new int[n1];
        int[] rightArr = new int[n2];

        for (int i = 0; i < n1; i++) {
            leftArr[i] = arr[left + i];
        }
        for (int j = 0; j < n2; j++) {
            rightArr[j] = arr[mid + 1 + j];
        }

        int i = 0, j = 0, k = left;

        while (i < n1 && j < n2) {
            if (leftArr[i] <= rightArr[j]) {
                arr[k] = leftArr[i];
                i++;
            } else {
                arr[k] = rightArr[j];
                j++;
            }
            k++;
        }

        while (i < n1) {
            arr[k] = leftArr[i];
            i++;
            k++;
        }

        while (j < n2) {
            arr[k] = rightArr[j];
            j++;
            k++;
        }
    }

    public static void main(String[] args) {
        int[] arr = {10, 7, 8, 9, 1, 5};
        System.out.println("Original Array:");
        printArray(arr);

        mergeSort(arr, 0, arr.length - 1);

        System.out.println("\nSorted Array:");
        printArray(arr);
    }

    private static void printArray(int[] arr) {
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();
    }
}
```
