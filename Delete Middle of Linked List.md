## Delete Middle of Linked List

### Question
Given a singly linked list, delete middle of the linked list. For example, if given linked list is 1->2->3->4->5 then linked list should be modified to 1->2->4->5.
If there are even nodes, then there would be two middle nodes, we need to delete the second middle element. For example, if given linked list is 1->2->3->4->5->6 then it should be modified to 1->2->3->5->6.
If the input linked list is NULL or has 1 node, then it should return NULL
```
Example 1:

Input:
LinkedList: 1->2->3->4->5
Output: 1 2 4 5

Example 2:

Input:
LinkedList: 2->4->6->7->5->1
Output: 2 4 6 5 1
```
### Solution:
    ``` Python
        '''
        class Node:
            def __init__(self, data):
                self.data = data
                self.next = None
        '''
        def deleteMid(head):
            '''
            head:  head of given linkedList
            return: head of resultant llist
            '''
            if not head or not head.next:
                return None
    
            slow = head
            fast = head
            prev = None
    
            while(fast is not None and fast.next is not None):
                fast = fast.next.next
                prev = slow
                slow = slow.next
        
            prev.next = slow.next
    
            return head
    
        
        class Node:
            def __init__(self, data):
                self.data = data
                self.next = None


        class Llist:
            def __init__(self):
                self.head = None

            def insert(self, data, tail):
                node = Node(data)

                if not self.head:
                    self.head = node
                    return node

                tail.next = node
                return node


        def printList(head):
            while head:
                print(head.data, end=' ')
                head = head.next
            print()

        if __name__ == '__main__':
            t = int(input())

            for tcs in range(t):
                n=int(input())
                arr1 = [int(x) for x in input().split()]
                ll = Llist()
                tail = None
                for nodeData in arr1:
                    tail = ll.insert(nodeData, tail)

                res=deleteMid(ll.head)
                printList(res)
    ``` 
  