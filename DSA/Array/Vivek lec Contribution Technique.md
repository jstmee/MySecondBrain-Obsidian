
https://maang.in/cohorts/AZ-Premium-Cohort-13-64/live-session/Contribution-Technique-1030



Contribution technique

![[Pasted image 20260118014110.png]]

1.atomic item contribution form
[find sum of all subarray of an array](https://www.geeksforgeeks.org/problems/sum-of-subarrays2229/1)

-----


Ques2
![[Pasted image 20260118014449.png]]

Same as sum of all subarrays do column vise
How many times each element is comming in all triplet
So we have.   _  _ _ one we knw other can be anything else apart from others
So n-1C2 × arr[I] for all elements.

-----

Ques3
![[Pasted image 20260118015835.png]]

We have to do this in n^2 
Correlated with previous problems
We choose subarray then sum
Similarly here choose subarray then inversion
So count a inversion for which it is part of.
Here atomic item is each inversion.
So for particular inversion i j what is how many subarray will this inversion  now find try dry
Which is equal to i+1 ×  right lines
We are doing reverse 
Asked for every subarray go and count no of inversion
Let's think reverse
For a inversion count pair in how many subarray it is present.
So overall it will be o(n^2).
![[Pasted image 20260524062559.png]] 

---
