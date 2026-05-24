
https://maang.in/cohorts/AZ-Premium-Cohort-13-64/live-session/Contribution-Technique-1030



Contribution technique

![[Pasted image 20260118014110.png]]

**1.atomic item contribution form**

Double summation type problem go through all subarray and do sum of something can be solved


[find sum of all subarray of an array](https://www.geeksforgeeks.org/problems/sum-of-subarrays2229/1)
Here atomic item contribution is index

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
So overall it will be o(n^2). We can do on nlogn using advance data struct
![[Pasted image 20260524062559.png]] 

---


#### contribution at pivot end

Ques
Find the sum of products of all possible subarray
Here previous method won't work atomic item won't work why??? It's rowvise sum and column vise product
Idea is extending at end or beginning 
Which is ending at i. Like kadane medium blog
Suppose dpi is prod summation ending at i then what would be for i+1?? Which is numi+numi×dpi-1.
This technique can be applied to sum of all subarray one also.

----


Find product of sum of all subarray
Product of product of all subarray

----

Quest
Leetcode 2262
It can be solved by two pointer but need to solve using contribution technique
What is atomic item?
a to z present or not
For no of distinct in subarray give value why because it has a b c etc whether a is present b is present.....or not it is atomic item.
So no of subarray having a will +1

a _ _ _ a it will have   6C2-4C2 TOTAL - DO NOT HAVE
__ __ b b __ __ 
6C2-2C2-3C2 NO OF SUBARRAY WHICH CONTAINS b.
It also contains find no of subarray that does not contains x
How to code it.



-----



Using stl 

Given array of size n and integer X. Find no of pair i,j i<j and arri+ arr[j]=X. Two sum problem leetcode
Fox one point ending easy ...... That is for every end weare maintaining a data structure maybe stl.



Ques
Given array of sz n and integer k. Find smallest value of arri+arri I<j and arri+arri>=k
Solve
Fix j
So arri>=k-arrj     
So we can use set lower bound function stl for find  
![[Pasted image 20260524070914.png]]            

