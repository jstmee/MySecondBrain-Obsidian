



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

ios_base::sync_with_stio(0); use only cin cout because we don't want stdio library to call stdio stuff which we don't want and not needed
Simply ek ek karke ram me mat karo phle sb ram me le aao fir Jo karna hai voh karo ram me cheeze fast hai esliye in simple terms.

Use signed in place of int main()
Then # define int long long

---


Skills to train
1.visuization
2.brain storming
3.implementation
4.debugging

----


Things to do in every problems
1.Concept theory
2.Framework
3.Forms
4.Tactics optimize
5.Debug

----


Make sheet for problems
Like
1.status coded but wa, got ac, got tle stuff
2.time taken to solve it
3.concept topic
4.framework if u had to think of solution from scratch how will I proceed
5.form each topic has finite set of forms classic ideas forms which one relates to
6.tactics tricks that can be applied to solve it quickly
7.debug log mistake in coding which I have made
8.solution summary 
9.notes

----


For any problem

1.Read question 5 min
Solve observe 20min observe think topic forms etc
2.Formulate think how code would look
Pass tle check
3.coding 15 to 20min implementation
4.debug
5.see others code.

------


Quest
Given array all distinct elements. find no of possible subsequence
7 if array is 1 2 3 
2^n -1 empty not allowed
pow() function give floating answer do not use always use looping.

-------


Given array find no of subarray
n*(n+1)/2
For subarray we need to choose 2 line from n+1 line to make subarray so n+1C2.


----

Given array find sum of all subarrays
Link-https://www.geeksforgeeks.org/problems/sum-of-subarrays2229/1
Method 1 contribution technique
Contribution tech
1. Atomic item technique
2. Extended contribution sum of product can be solved by this quest sum of products of all subarray
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
 Now how many times a particular value is comming.
 If we start from nay element how many start can be possible and how many end is possible
 Then multiply them to get.
 xC1*yC1 IS ANSWER.
If we at i the then I+1 line left left

Is total - I+1 total is n+1 lines.


-----
