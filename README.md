# Delete-Nodes-from-Linked-List-Present-in-Array
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def modifiedList(self, nums: List[int], head: Optional[ListNode]) -> Optional[ListNode]:
        if head is None or nums is None:
            return head
        while head and head.val in nums:
            head = head.next
        temp=head
        nums=set(nums)
        while temp and temp.next:
            c=temp.next.val
            if c in nums:
                temp.next=temp.next.next
            else:
                temp=temp.next
        return head
