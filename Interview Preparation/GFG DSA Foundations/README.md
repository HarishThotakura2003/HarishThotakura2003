# GFG DSA Foundations 

# Module 0

## Pointers in C++

1. Every variable has three things - name, value, address.
2. Pointer is a variable that stores a memory address.
3. `&` - when used before a variable name, it gives the memory address of the variable  
4. `*` - when used before an adrress(pointer ), gives the value of the address
5. `*` - is also used to create pointers
6. `&` - is also used to create reference variable
7. If we do not initialize a pointer with a value, it may get a random address, so we cannot dereference a uninitialzed pointer
8. `sizeof()` returns the size of the type.
9. Size of any type of pointer is same

_Program 1:_
```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 10;
    cout << (&x);
    return 0;
}
```

_Program 2:_
```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 10;
    cout << (*(&x));
    return 0;
}
```

_Program 3:_
```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 10;
    int *ptr = &x;
    cout << *ptr << " ";
    cout << ptr << " ";
    return 0;
}
```

_Program 4:_
```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 10;
    int *ptr = &x;
    cout << *ptr << " ";
    x = x + 30;
    cout << *ptr << " ";
    cout << ptr << " ";
    *ptr = *ptr + 40;
    cout << x << " ";
    return 0;
}
```

_Program 5:_ Segmentation Fault
```cpp
#include <iostream>
using namespace std;

int main() {
    int *p1;
    cout << p1 << " ";
    cout << *p1 << " ";
    return 0;
}
```

_Program 6:_
```cpp
#include <iostream>
using namespace std;

int main() {
    int *p1;
    double *p2;
    string *p3;
    cout << (sizeof p1) << " ";
    cout << (sizeof p2) << " ";
    cout << (sizeof p3) << " ";
    return 0;
}
```

__Applications of Pointers__

1. Changing Passed Parameter, This can be done via references primarily
2. Passing Large Objects - Use Reference so that we wont waste memory copying.
3. Dynamic Memory Allocation
4. Implementing Pointer Based Data Structures
5. Return Multiple values , change value at pointers :)
6. System Level Programming 
7. Used for array element access, array name gives the address of the first element of array

_Program 7:_
```cpp
#include <iostream>
using namespace std;

void swap(int *p1, int *p2)
    {
        int temp = *p1;
        *p1 = *p2;
        *p2 = temp;
    }
int main()
    {
        int x = 10, y = 20;
        swap(&x, &y);
        cout << x << " " << y << " ";
        return 0;
    }
```
_Program 8:_
```cpp
#include <iostream>
using namespace std;

void getAddMul(int x, int y, int *mPtr, int *aPtr)
    {
        *mPtr = x * y;
        *aPtr = x + y;
    }
int main()
    {
        int x = 10, y = 20, a, m;
        getAddMul(x, y, &a, &m);
        cout << a << " " << m;
        return 0;
    }
```
_Program 9:_
```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {20, 30, 40, 50};
    int *ptr = arr;
    cout << *(ptr + 2);
}
```

_Program 10:_
```cpp
#include <iostream>
using namespace std;

void fun(int *ptr, int n)
    {
        for (int i= 0; i<n; i++)
            cout << ptr[i] << " ";
    }
int main()
    {
        int arr[] = {10, 20, 30, 40, 50};
        fun(arr, 5);
    }
```

_Program 11:_
```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {1, 2, 3};
    int *ptr = arr;
    cout << sizeof(arr) << " ";//24
    cout << sizeof(ptr) << " ";//8
    return 0;
}
```

_Program 12:_
```cpp
#include <iostream>
using namespace std;

int main() {
    char arr[] = {1, 2, 3};
    char *ptr = arr;
    cout << sizeof(arr) << " ";//3
    cout << sizeof(ptr) << " ";//8
    return 0;
}
```

_Program 13:_
```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20};
    int *p1 = arr;
    ++*p1;
    cout << arr[0] << " " <<
        arr[1] << " " << *p1;
    return 0;
}
```

_Program 14:_
```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20};
    int *p2 = arr;
    *p2++;
    cout << arr[0] << " " <<
        arr[1] << " " << *p2;
    return 0;
}
```

_Program 15:_
```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20};
    int *p2 = arr;
    cout << *p2++ << " ";
    cout << arr[0] << " " <<
        arr[1] << " " << *p2;
    return 0;
}
```

_Program 16:_
```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20};
    int *p3 = arr;
    *++p3;
    cout << arr[0] << " " <<
        arr[1] << " " << *p3;
    return 0;
}
```

_Program 17:_
```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20};
    int *p3 = arr;
    cout << *++p3 << " ";
    cout << arr[0] << " " <<
        arr[1] << " " << *p3;
    return 0;
}
```


## Stl Introduction

Stl is divided into two parts: containers, algorithms

Containers can be divided into three parts:
1. Simple : Pair, Vector. forward_list, list(doubly)
2. Container Adapters : Stack, Queue, Priority Queue
3. Associative : set, map, MultiMap, MultiSet, unordered_set,unordered_map

- Unordered means hash tables, Normal is Self balancing search trees
- Iterators give u address of individual items in container