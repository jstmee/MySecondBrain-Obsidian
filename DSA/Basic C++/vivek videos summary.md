



Foundations of Problem Solving lec 2 lec 1 was intro nothing imp
https://maang.in/cohorts/AZ-Premium-Cohort-13-64/live-session/Foundations-of-Problem-Solving-982

Code then compile them run
Time limit given for problem like 1 sec is for??
It is for test file

FastIO

DISK
INPUT BUFFER 
CODE
OUTPUT BUFFER
OUTPUT FILE

ios_base::sync_with_stio(0); use only cin cout because we dont want stdio library to call stdio stuff which we dont want and not needed
Simply ek ek karke ram me mat karo phle sb ram me le ao fir Jo karna hai voh karo ram me cheeze fast hai esliye in simple terms.

Use signed inplace of int main()
Then # define int long long

------


Quest
Given array all distinct elements.find no of possible subsequence
7 if array is 1 2 3 
2^n -1 empty not allowed
pow() function give floating answer do not use always use looping.

-------


Given array find no of subarray
n*(n+1)/2
For subarray we need to choose 2 line from n+1 line tomake subarray so n+1C2.

-----

Skills to train
1.visuization
2.brain storming
3.implementation
4.debugging

------


Things to do in every problems
Concept theory
Framework
Forms
Tactics optimize
Debug

-----


Make sheet for problems
Like
1.status coded but wa,got ac,got tle stuff
2.time taken to solve it
3.concept topic
4.framework if u had to think of solution from scratch how will I proceed
5.form each topic has finite set of forms classic ideas forms which one relates to
6.tactics tricks that can be applied to solve it quickly
7.debug log mistake in coding which I have made
8.solution summary 
9.notes


----

Given array find sum of all subarrays
Method 1 contribution technique
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
 Now how many times a particular value is comming.
Contribution tech
1. Atomic item technique
2. Extended contribution sum of product can be solved by this quest sum of products of all subarray