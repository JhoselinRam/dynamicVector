# dynamicVector (Template)
This is an Arduino library that allows you to create a array like structure similar to the C++ vector template.
The memory is dynamically allocated and deallocated when needed.
___
Its useful when you need  to store a collection of data, of the same data type, without knowing the total number of elements in the collection at compile time.

But beware that if you dynamically allocate too much memory, due to the limited amount of memory in the Arduino platform, may lead to catastrophic failure at run time without warning.
___
### Usage
After install, import the library at the top of the sketch
>`#include<dynamicVector.h>`

And create an object by providing a data type
>`dynamicVector<´type´> myVector;`

Where `'type'` can be any of the native data types (`int, char, float, unit8_t, etc`) or a custom type, like a class.

Add elements by using the `pushIn` method
>`myVector.pushIn(newElement);`

Access exiting elements bay using the `[]` operator.
>`myVector[index]`  

Elements can by eliminated from the vector using the `remove` method. This method will remove the last element in the vector.
>`myVector.remove();`

The `getSize` method return the number of elements in the vector.
>`myVector.getSize();`

The vector can be resize.
If the new size is less than the current size, all excess elements at the end of the vector will be drop. If the new size is bigger thar the current size, new memory will be allocated.

Opcionally, a second parameter can be passed to the method, and any new allocated memory will be set to that value.
>`myVector.resize(newSize);`
>`myVector.resize(newSize, newValue);`