

Previous version [link](https://docs.google.com/document/d/1yds3hykKy5AiQ5G7EzDJIEKSxilVZUHBdBfCrRMslYQ/edit?tab=t.0#heading=h.wjbykxaf8qu7)

Topics to cover

Basic cs fundamentals  
1.DBMS \+sql (MIMP)

**MY doc for DBMS [Link](https://docs.google.com/document/d/1-i9da5nHYfUewFhcyAOJ2znrjjkTMAh7D4jfGtXgubs/edit) dbms**

1.this playlist [Codehelpplaylist](https://www.youtube.com/watch?v=eYpXCdvKwEQ&list=PLDzeHZWIZsTpukecmA2p5rhHM14bl2dHU&ab_channel=CodeHelp-byBabbar)  
2.SQL  [link](https://www.youtube.com/watch?v=KS3wwOD3vDQ&list=PLtfxzVLWb-B-aQ1U1AaOA8LBrCoE-3TX2&ab_channel=EverydayDataScience) daily 30 min  
3.this playlist [link](https://www.youtube.com/watch?v=nYmI1C9r3gc&list=PLZ2k-po0Y7s28FUZGDaiMkZYPtPDhOD42&ab_channel=GuruprasadVeerannavaru) optional have in very depth

3.OS [link codehelp](https://www.youtube.com/watch?v=_TpOHMCODXo&list=PLDzeHZWIZsTr3nwuTegHLa2qlI81QweYG&ab_channel=CodeHelp-byBabbar)

4.CN  
First is sanket singh in webdev  
Next is [kunal video](https://www.youtube.com/watch?v=IPvYjXCsTg8&list=PL9gnSGHSqcnoqBXdMwUTRod4Gi3eac2Ak&index=3&ab_channel=KunalKushwaha) 

Web Development

[Linkkkk](https://docs.google.com/document/d/1IaiNU9g1qD2izdaVDfCQxBvKmJTvIxIBCGh3KmlSAi0/edit) api and rest api interview questions vimp  
1.HTML and CSS(both basic)  
2.Javascript  
4.react tailwind css

Other

Oops in java and c++.

 Dsa resources

1.strive a2z dsa codebeyond  
2.codestorywithmik  
3.codingmohan  
\=kunal kushwaha  
4.aryan mittal  
4.1 love babbar dsa  
5.luv playlist and his videos  
5.prepcoding  
6\.[https://csforall.graphy.com/s/courses/650ae311e4b072ebbc49bca1/take](https://csforall.graphy.com/s/courses/650ae311e4b072ebbc49bca1/take)  
7.kumar k docs  
8.gfg sections  
9.coding ninja sections all  
10.coderarmy  
11.sanket singh  
12.tle  
13.bharat khanna  
14.interviewbit  
[https://docs.google.com/spreadsheets/d/18rl3crCqSSvqnBcieMKKVwNEyE4kTKtF75OBcx3KXJA/edit\#gid=0](https://docs.google.com/spreadsheets/d/18rl3crCqSSvqnBcieMKKVwNEyE4kTKtF75OBcx3KXJA/edit#gid=0)

[https://learnyard.com/practice/dsa/](https://learnyard.com/practice/dsa/)

#                  **Data structure and Algorithm**

# 

# 0.STL

1.tle level 2 stl video  
2.striver has two videos  
[https://www.youtube.com/watch?v=iOOzYwBeXIM\&list=PLN4aKSfpk8TQ6CqzMRDVUr-jEpObLiYdq\&ab\_channel=CodeBeyond](https://www.youtube.com/watch?v=iOOzYwBeXIM&list=PLN4aKSfpk8TQ6CqzMRDVUr-jEpObLiYdq&ab_channel=CodeBeyond)

3\.

Theory and detail learning

[https://ideone.com/XQcg14](https://ideone.com/XQcg14)

\-**remember in c++ if we declare anything globally it default value is 0 if not initialized if main then it has garbage value**.

\-About BASIC C++ NAMESPACE

1. Why bits/stdc++.h it includes all the libraries but it takes some time so in an interview don't use it.  
2. Using namespace std it is kind of a scope thing in c++ all the functions are in std namespace therefore to access we use std namespace or std::function name.  
   To reduce std:: again and again we use std namespace  
   code//  
     
   \#include\<bits/stdc++.h\>  
     
   namespace vis{  
       Int val=50;  
       Int gerval(){  
           Return val\*5;  
       }  
   }    
     
   Int main(){  
       double val=30.0;  
      // int val  if declare it will through error  
       std::cout\<\<val\<\<endl;//print 30.0  
       std:: cout\<\<vis::val\<\<endl;//print 50  
     
     
   }  
   

\-STRUCTURE in C++.

    1.To create your own data type we can use struct it combine data types into one.It is a user      defined data type  
    Exp:  
   //self datatype  
    Struct node{  
          Int val;  
          String s;  
          Double x;  
          node(){//constructor type thing  
            //initialize all the variables  
          }  
    };

\-Container in c++ stl

    1.ARRAY IN C++  
      
    **\# array\<int,5\> arr={5,3,2};//whats the array it will be {5,3,2,0,0};**  
     **That's Why we create 0 array as {0}; vimp**  
     **Ex int arr\[100\]={0}//only initialize 0th to 0 and by default everything is 0 rest**

    
  **Iterator**  
     
   **\# begin(),end(),rbegin(),r.end()**  
    **\-begin() points to first el**  
    **\-end() points to next of last element always**  
    **\-rbegin() points to last ele**  
   **\- rend() points to just before first ele**  
   

## 

# **1.ARRAY AND VECTOR**

### **Ques1.** find the largest second largest and third largest element in array vector

[https://www.codingninjas.com/studio/problems/ninja-and-the-second-order-elements\_6581960](https://www.codingninjas.com/studio/problems/ninja-and-the-second-order-elements_6581960)  
[https://www.geeksforgeeks.org/find-the-largest-three-elements-in-an-array/](https://www.geeksforgeeks.org/find-the-largest-three-elements-in-an-array/)  
[Leetcode 1913](https://leetcode.com/problems/maximum-product-difference-between-two-pairs/description/)  
[Leetcode 1464](https://leetcode.com/problems/maximum-product-of-two-elements-in-an-array/description/)  
Sol?? Use of two variables ,for the third largest use of 3 variables.

## 

## 

## 

## \-**Maths/Prime No/divisibility/number theory**

### Ques 

[Leetcode 1952](https://leetcode.com/problems/three-divisors/description/)

### Ques

[Leetcode 1979](https://leetcode.com/problems/find-greatest-common-divisor-of-array/description/)

### Ques 

[Leetcode 2652](https://leetcode.com/problems/sum-multiples/description/)  
Sol brute is simple most optimize is use of inclusion exclusion principle  
sum all the factor of 3 \+ sum of all the factors of 5 \+ sum of all the factors of 7 \- sum of all the factor of 3 \* 5 \- sum of all the factors of 5 \* 7 \- sum of all the factors of 3 \* 7 \+ sum of all the factors of 3 \* 5 \* 7\.

## 

# Stack

Notes–  
Operation are push ,pop,top  
[**https://leetcode.com/discuss/study-guide/2347639/A-comprehensive-guide-and-template-for-monotonic-stack-based-problems**](https://leetcode.com/discuss/study-guide/2347639/A-comprehensive-guide-and-template-for-monotonic-stack-based-problems)  
[**https://leetcode.com/discuss/study-guide/3168516/A-general-approach-to-stack-problems-in-C%2B%2B-or-Generic-Template**](https://leetcode.com/discuss/study-guide/3168516/A-general-approach-to-stack-problems-in-C%2B%2B-or-Generic-Template)

**0.IMplementation of stack using array and linked list**  
**1.copy stack from one to another using another stack and using recursion imp**  
**2.insert at bottom/any ind of the stack using another stack and using recursion**  
**3.remove at bottom/ind of stack using another and recursion**  
**4.reverse stack using recursion**  
**5.balance bracket sequence check whether given bracket sequence are balanced or not?**  
[**https://www.geeksforgeeks.org/problems/parenthesis-checker2744/1**](https://www.geeksforgeeks.org/problems/parenthesis-checker2744/1)

[**https://leetcode.com/problems/valid-parentheses/description/**](https://leetcode.com/problems/valid-parentheses/description/)

**Ques1 nearest greater right,left,nearest lesser right ,left Mimp**  
[**https://www.codingninjas.com/studio/problems/next-greater-element\_799354**](https://www.codingninjas.com/studio/problems/next-greater-element_799354)  
[**https://www.codingninjas.com/studio/problems/next-smaller-element\_1112581**](https://www.codingninjas.com/studio/problems/next-smaller-element_1112581)  
[**https://leetcode.com/problems/daily-temperatures/description/**](https://leetcode.com/problems/daily-temperatures/description/)  
[**https://leetcode.com/problems/next-greater-element-i/description/**](https://leetcode.com/problems/next-greater-element-i/description/)  
[**https://leetcode.com/problems/next-greater-element-ii/description/**](https://leetcode.com/problems/next-greater-element-ii/description/)  
**o(1) space optimization possible**  
**Follow up problems on this**  
**Stock span problem.**  
[**https://www.codingninjas.com/studio/problems/stock-span\_5243295**](https://www.codingninjas.com/studio/problems/stock-span_5243295)  
**Maximum area of histogram.**  
[**https://leetcode.com/problems/largest-rectangle-in-histogram/description/**](https://leetcode.com/problems/largest-rectangle-in-histogram/description/)  
**Most optimize is using stack but there is one pass also using stack without find lgr and rgr also source coderarmy**

**Maximum area of binary matrix.**  
[**https://www.geeksforgeeks.org/problems/max-rectangle/1**](https://www.geeksforgeeks.org/problems/max-rectangle/1)

**More follow ups on this**  
[**https://leetcode.com/problems/sum-of-subarray-minimums/**](https://leetcode.com/problems/sum-of-subarray-minimums/)  
[**https://leetcode.com/problems/sum-of-subarray-ranges/**](https://leetcode.com/problems/sum-of-subarray-ranges/)  
[**https://leetcode.com/problems/maximum-subarray-min-product/description/**](https://leetcode.com/problems/maximum-subarray-min-product/description/)  
[**https://leetcode.com/problems/number-of-valid-subarrays/**](https://leetcode.com/problems/number-of-valid-subarrays/)  
**Rain water tapping.**  
[**https://leetcode.com/problems/trapping-rain-water/solutions/**](https://leetcode.com/problems/trapping-rain-water/solutions/)  
**Method 1 is monotonic stack**  
**Method 2 is using two pointer  both method take o(n) and o(n) time and space**  
**Method 3 is using a one pass two pointer approach that takes o(1) space.**  
