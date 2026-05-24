
TARGET DECK: DSA::Array::Contribution Technique


https://srinivastechblog.hashnode.dev/contribution-technique-the-secret-trick-to-faster-dsa-solutions?t=1770904730168

https://medium.com/@alok.g.v/data-structures-and-algorithms-dsa-concept-subarrays-part-2-cb7f4432aba6

https://youkn0wwho.academy/topic-list/contribution_technique


Contribution tech
1. Atomic item technique
2. Extended contribution sum of product can be solved by this quest sum of products of all subarray


Q: Given array find sum of all subarrays
Link-https://www.geeksforgeeks.org/problems/sum-of-subarrays2229/1
A: Method 1 contribution technique
Do not watch algoprep video.
Think contribution of each element of array in which which subarray it can comes
What can be it's start index and what can be it's end index
Egg
1 2 3
1 
 2 
  3
1 2
   2 3
1 2 3
 We can get sum int wo ways first horizontally and 2nd is vertically horizontally take n^2 vertically take n.
 Now how many times a particular value is coming.
 If we start from nay element how many start can be possible and how many end is possible
 Then multiply them to get.
 xC1xyC1 IS ANSWER.
If we at i the then I+1 line left left
Is total - I+1 total is n+1 lines.
<!--ID: 1779507707035-->

