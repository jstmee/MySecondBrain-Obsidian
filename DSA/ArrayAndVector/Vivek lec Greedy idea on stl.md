
https://maang.in/cohorts/AZ-Premium-Cohort-13-64/live-session/Greedy-Ideas-with-STL-1040


Thinking in reverse
And operation decode are common in greedy

Exchange arguments


Ques 
Given two array A,B. find the min value of (A.B) POSITION WAISE MULTIPLY THEN ADD
U can rearrange the in A and B. Elements can be negative
Proof
Let's us assume 
Ai is sorted
Let arrangement of B be bi
Then.....
Let's say we swap bi and bj
Then
aibi+ajbj<aibj+ajbi
This gives
bi>bj means B should in descending order


Ques
Given Si,Di and Ti for codeforces type contest score u have to solve all problems find optimal ordering to solve problems
Let's there are only two problems
S1.   S2.     >.    S2.     S1
D1.   D2.            D1.     D2
T1.   T2.            T1.      T2
s1-d1t1+s2-d2(t1+t2)>s2-d2t2+s1-d1(t1+t2)
This gives
t1/D1<t2/D2.   So we need to sort the element by there ti/di values.


Ques
given ai bi.....
Alice will choose from  ai and Bob will choose bi
What would be optimal
a1 a2
b1 b2
a1-b2>a2-b1
This gives a1+b1>a2+b2


Ques
Given a and b number u have to reach b from a 
U can go to 2x or x-1 now what is min no of moves needed. This is microsoft oa ka question
Think in reverse