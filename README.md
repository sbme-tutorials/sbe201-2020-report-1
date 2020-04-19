## [SBE201] Report 1: Linked Lists

| Name | Section | BN |
|---|---|---|
|            |        |      |


##### 1. Linked List Size

```c++
struct IntegerNode
{
  int data;
  IntegerNode *next;
};

int size( IntegerNode *front )
{

}
```

- A) Implement the function `size` that returns the size of a given linked list (count of elements).
- B) Provide a time complexity estimate using the Big-O notation.
- C) Can you provide a recursive version of the `size` function?

###### Solution


##### 2. Linked List Operations


- A) What does the following function do?

```c++
#include <iostream>
struct IntegerNode
{
  int data;
  IntegerNode *next;
};

void fun1(node* front)
{
  if(front == nullptr)
    return;
  
  fun1(front->next);
  std::cout << front->data << " ";
}
```

- B) What is the output would be if the input linked list is represented in order as: **5->90->300->7->55**
- C) What is the time complexity of such a function.

###### Solution


##### 3. Doubly-Linked List

```c++
struct IntegerNode
{
  int data;
  IntegerNode *next;
  IntegerNode *back;
};

struct IntegersLL
{
  IntegerNode *front;
};
```

- A) Implement a function to insert an element at arbitrary `index` in a **double linked list**.

```c++
void insertAt( IntegersLL &list , int index, int data )
{
  
}
```
- B) Provide a visual illustratoin to the steps in order to support that operation.

###### Solution


##### 4. Circular Linked List

```c++
struct IntegerNode
{
  int data;
  IntegerNode *next;
};

struct IntegersLL
{
  IntegerNode *front;
};
```

The following functions are a implemented earlier for a regular linked list:

```c++
void pushFront( IntegerLL &list, int data )
{
    list.front = new node{ data , list.front };
}

node *backNode( IntegerLL &list )
{
    node *temp = list.front;
    while( temp->next != nullptr )
        temp = temp->next;
    return temp;
}

void *pushBack( IntegerLL &list, double data )
{
    if( list.front == nullptr )
        return pushFront( list , data );
    else
    {
        node *back = backNode( list );
        back->next = new node{ data , nullptr };
    }
}

void removeBack( IntegerLL &list )
{ 
    if( isEmpty( list ))
        return;
    else if( list.front->next == nullptr )
        removeFront( list );
    else
    {
        IntegerNode *prev = list.front;
        while( prev->next->next != nullptr )
            prev = prev->next;
        delete prev->next;
        prev->next = nullptr;
    }
}

void printLL( IntegerLL &list )
{
    node *current = list.front;
    while( current != nullptr )
    {
        std::cout << current->data;
        current = current->next;
    }
}
```

- A) How would you change each function to work properly for a circular linked list that uses only a `front` pointer.

###### Solution
