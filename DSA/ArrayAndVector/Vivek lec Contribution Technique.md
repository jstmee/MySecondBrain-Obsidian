
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
How many times each element is coming in all triplet
So we have.   _  _ _ one we knw other can be anything else apart from others
we know one element say mid now we have to select any two element from the rest of the elements
So n-1C2 × arr[I] for all elements.

-----


Ques3
![[Pasted image 20260118015835.png]]

We have to do this in n^2 
Correlated with previous problems
We choose subarray then sum
Similarly here choose inversion then subarray
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
It can be solved by two pointer but need to solve using contribution technique many other possible way to solve
codingmohan video:https://www.youtube.com/watch?v=uuBBafS9rgU his solution and code is simple
his code 
```c++
long long appealSum(string s) {
        int n = s.size();
        long long ans = 0;
        vector<char> v;
        for (int i = 0; i < 26; i++) {
            char vowel = 'a' + i;
            int last = -1;
            for (int i = 0; i < n; i++) {
                if (s[i] == vowel) {
                    ans += (i + 1);
                    last = i;
                } else {
                    if (last != -1) {
                        ans += last+1;
                    }
                }
            }
        }
        return ans;
    }
```
What is atomic item?
a to z present or not
For no of distinct in subarray give value why because it has a b c etc whether a is present b is present.....or not it is atomic item.
So no of subarray having a will +1
link - https://www.youtube.com/watch?v=jdSRCHUFUDc
example for a string aba
              apresent     bpresent
a                         +1               +0
b                                             +1
a                          +1
ab                        +1               +1
ba                         +1              +1
aba                        +1                +1
 now instead of doing horizontally we do vertically
a _ _ _ a it will have   6C2-4C2 TOTAL - DO NOT HAVE
__ __ b b __ __ 
6C2-2C2-3C2 NO OF SUBARRAY WHICH CONTAINS b.
Now the problem is reduced to find how many time a character is present in all subarray
It also contains find no of subarray that does not contains x this can be solved using map and without map
How to code it.
```c++
long long n=s.length();
long long ans=0;
for(char ch='a;ch<='z;ch++){
	int last=-1;
	long long contrib=n*(n+1)/2;
	for(int i=0;i<n;i++){
		if(s[i]==ch){
			long long len=i-last-1;
			if(len>0){
				contrib-=(len+1)*len/2;
			}
			last=i;
		}
	}
	long long len=n-last-1;
	if(len>0){
		contrib-=(len+1)*len/2;
	}
	ans+=contrib;
}
return ans;
```




-----



Using stl 

Given array of size n and integer X. Find no of pair i,j i<j and arri+ arr[j]=X. Two sum problem leetcode
Fox one point ending easy ...... That is for every end we are maintaining a data structure maybe stl.

-----


Ques
Given array of sz n and integer k. Find smallest value of arri+arri I<j and arri+arri>=k
Solve
Fix j
So arri>=k-arrj     
So we can use set lower bound function stl for find  
![[Pasted image 20260524070914.png]]            

----

Some more problems on Contribution Technique if in case anyone wants to practice,

  

1) https://leetcode.com/problems/vowels-of-all-substrings/description/

2) https://leetcode.com/problems/total-appeal-of-a-string/

3) https://leetcode.com/problems/count-vowel-substrings-of-a-string/

4) https://leetcode.com/problems/number-of-substrings-containing-all-three-characters/description/

5) https://leetcode.com/problems/count-unique-characters-of-all-substrings-of-a-given-string/description/

6) https://leetcode.com/problems/vowels-of-all-substrings/

7) https://leetcode.com/problems/find-the-median-of-the-uniqueness-array/

  

LC Weekly Problems:

1) https://leetcode.com/contest/weekly-contest-433/problems/maximum-and-minimum-sums-of-at-most-size-k-subsequences/description/

2) https://leetcode.com/contest/weekly-contest-433/problems/maximum-and-minimum-sums-of-at-most-size-k-subarrays/description/
https://leetcode.com/problems/sum-of-total-strength-of-wizards/solutions/2062017/c-prefix-monotonic-stack-o-n-solution-with-thought-process/