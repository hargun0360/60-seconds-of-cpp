---
title: Function to check if a singly linked list is palindrome
tags: Linkedlist
expertise: easy
---

The idea is to first reverse the second half part of the linked list and then check whether the list is palindrome or not.

- Get the middle of the linked list. 
- Reverse the second half of the linked list. 
- Check if the first half and second half are identical. 

```cpp
bool isPalindrome(LinkedListNode<int> *head) {
    // Write your code here.
    if(!head)
        return true;
    LinkedListNode<int>* f=head,*s=head,*temp=NULL;
    while(f&&f->next){
        s=s->next;
        f=f->next->next;
    }
    //reverse the list from slow ptr
    LinkedListNode<int>* prev=s;
    s=s->next;
    //to stop backward iteration at middle(for odd /even)
    prev->next=NULL;
    while(s!=NULL){
        temp=s->next;
        s->next=prev;
        prev=s;
        s=temp;        
    }
    f=head,s=prev;
    while(s){
        if(f->data!=s->data)
            return false;
        f=f->next;
        s=s->next;
    }
    
    return true;
}
```
