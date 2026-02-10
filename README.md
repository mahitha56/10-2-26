# 10-2-26
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def mergeTwoLists(self, list1, list2):

        dummy = ListNode(0)   # starting node
        tail = dummy          # pointer to build result

        while list1 and list2:
            if list1.val < list2.val:
                tail.next = list1
                list1 = list1.next
            else:
                tail.next = list2
                list2 = list2.next
            
            tail = tail.next

        # add remaining nodes
        tail.next = list1 or list2

        return dummy.next


#today claass

<html>
    <head>
        <title>Day-7</title>
        <style>
            table,th,td{
                border: 2px solid black;
                border-collapse:collapse;
                padding: 5px;
            }
        </style>
    </head>
    <body>
        <h1>Day-7</h1>
        <h2>Row span</h1>
        <table>
            <tr>
                <th>Name</th>
                <th>College</th>
                <th>Class</th>

            </tr>
            <tr>
                <td>Mahitha</td>
                <td>Spmvv</td>
                <td rowspan="3">3rd Year</td>
               
            </tr>
            <tr>
                <td>Kalyani</td>
                <td>Svu</td>
               
            </tr>
            <tr>
                <td>Mahi</td>
                <td>Spmvv</td>
                

            </tr>
        </table>
        <br>
<h1>Column span</h1>
      <table >
    <tr>
        <th colspan="2">Student Details</th>
    </tr>

    <tr>
        <td>Name</td>
        <td>Mahitha</td>
    </tr>

    <tr>
        <td>Course</td>
        <td>Full Stack</td>
    </tr>
</table>
<br>
<h1>Forms</h1>
<form class="hlo">
    <h2> choose Branch</h2>
    <br>
    <label>CSE</label>
    <input type="radio" name="hlo">
    <br>
    <br>
    <label>ECE</label>
    <input type="radio" name="hlo"><br><br>
    <label>EEE</label>
    <input type="radio" name="hlo"><br><br>
    <label>Mech</label>
    <input type="radio" name="hlo"><br><br>

</form>

<h2>Checkpoint</h2>
<form class="hlo">
    <h3>Skills</h3>

    <label>
        <input type="checkbox"> Python
    </label><br><br>

    <label>
        <input type="checkbox"> HTML
    </label><br><br>

    <label>
        <input type="checkbox"> JavaScript
    </label><br><br>

    <label>
        <input type="checkbox"> Django
    </label><br><br>
</form>

    </body>
</html>


structure of table
forms in html
name="ts

You are given two sorted lists.
Merge them into one sorted list.

Example
list1 = [1,3,5]
list2 = [2,4,6]

Output = [1,2,3,4,5,6]

🔹 Method 1 — Two Pointer Technique (Best & Optimal)
💡 Idea

Since both lists are already sorted:

Compare first elements

Add smaller element

Move that pointer

Repeat until both lists finish

✅ Python Code (Array/List version)
def mergeSortedLists(list1, list2):
    i = j = 0
    merged = []

    while i < len(list1) and j < len(list2):
        if list1[i] <= list2[j]:
            merged.append(list1[i])
            i += 1
        else:
            merged.append(list2[j])
            j += 1

    # add remaining elements
    merged.extend(list1[i:])
    merged.extend(list2[j:])

    return merged


# Example
print(mergeSortedLists([1,3,5], [2,4,6]))

⏱ Complexity
Time  = O(n + m)
Space = O(n + m)
hii
🔹 Method 2 — Linked List version (Very important for interviews)

If lists are linked lists, we use a dummy node.
