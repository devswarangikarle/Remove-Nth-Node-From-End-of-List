# Remove-Nth-Node-From-End-of-List
Given the head of a linked list, remove the nth node from the end of the list and return its head.

class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

class Solution:
    def removeNthFromEnd(self, head, n):
        
        dummy = ListNode(0)
        dummy.next = head
        fast = slow = dummy

    
        for _ in range(n + 1):
            fast = fast.next

        
        while fast:
            fast = fast.next
            slow = slow.next

       
        slow.next = slow.next.next

        return dummy.next  


head = ListNode(1, ListNode(2, ListNode(3, ListNode(4, ListNode(5)))))
solution = Solution()
result = solution.removeNthFromEnd(head, 2)
