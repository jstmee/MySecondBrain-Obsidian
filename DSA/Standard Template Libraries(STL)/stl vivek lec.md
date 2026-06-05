
https://maang.in/playlists/STL-Introduction-3394?resourceUrl=cs87-cp504-pl3394-rs7919&returnUrl=%5B%22%2Fcourses%2FSTL-in-C-87%3Ftab%3Dchapters%22%5D from stl intro


Pointers(int*) and reference(int&)

(int*) defining a variable which stores address of another variable of type int.
& means address of any variable when define RHS of =
arr[3]=\*(arr+3)


algo stl it has various inbuilt function to use.
and data containers it has various data structures to use for storing data.


next_permutation and prev_permutation give next and previous permutation
https://maang.in/problems/Generating-Permutations-AZ101-366

-----

Standard template library(stl)

1. Algorithm.  
      Sort
      Reverse
      Upper bound lower bound
      nth element
      Next_permutation
      Random shuffle



2. Data structure containers
     Vector
     Stack
     Pair
     Set
     Queue
     Map
     Multiset
     Priority_queue
     Bitset
     Deque
     List
     Unordered


Sort   nlogn
sort(arr,arr+5) here arr+5 is not included 
arr[2]=\*(arr+2) same for 2[arr]
Global variable has 0 by default.
Internally it uses intro sort hybrid sorting


Vector []
v.clear() removes all element o1 we can use stack using vector in place of stack but for interview try to use stack.

Stack
First in last out or last in first out all o1

Queue
Use when we have to insert from back and pop from front
First in first out or last in last out

Dqueue
Use when we have to insert from both end
Deque can give element in using index it is close to vector but it is slower that y try not to use it. 


List is doubly linked list
list<int> li
Only use when need to delete on o1 from any mid part


Set like vector always sorted, all distinct, no random access
{} All in log n
Internally used red black tree type of  balance binary search tree 

Multiset - set+ allowed duplicates 
Unordered set - set + no sorted 

Priority queue give max element min element insert in  logn rest  o1 like multiset it handle duplicate element like multiset