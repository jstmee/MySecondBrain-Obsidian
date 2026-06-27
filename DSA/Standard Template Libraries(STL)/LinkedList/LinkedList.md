TARGET DECK: DSA::Standard Template Libraries(STL)::Linkedlist


Q: [146. LRU Cache](https://leetcode.com/problems/lru-cache/) first is what is question say it loud very imp
question is basically u have given get jo return karti hai eske corresponding value agar voh present hai ya nhi apne kisi cache me. now put is basically agar key present hai toh uski value toh update kardega nhi hai toh es key value ko add karna hai agar kisi bhi tym capacity se jada hua toh hume jo sbse km use hua hai usko nikalna hai
A: do the dry run we need at ds where we have to move element from the first to last and remove the last element which is best vector let first try which vector.
now for fresh pairs and least pair we will use front part of vector and back of the vector. this gives tle https://leetcode.com/problems/lru-cache/submissions/2047263026/
optimal approach what cost operation finding the key takes o(n) maybe use map and also erasing the key we have to maintain the least recent used so linkedlist doubly so map+linkedlist
we wil maintain as linkedlist for the key and store each keys adrress in the map with its value
link - https://leetcode.com/problems/lru-cache/submissions/2047273939/
<!--ID: 1782514948504-->


Q: [460. LFU Cache](https://leetcode.com/problems/lfu-cache/)
A: what does question asked read the question
what kind of dsa should be used map for key finding eficiently just like lru nad another ordered map for counter.
link - https://leetcode.com/problems/lfu-cache/submissions/2047845405/ 
<!--ID: 1782571475758-->
