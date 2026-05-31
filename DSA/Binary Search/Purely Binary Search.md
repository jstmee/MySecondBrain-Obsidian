
TARGET DECK: DSA::Binary Search::Purely Binary Search




#PurelyBinarySearch


Q: what is stl for num>=x
A: lower_bound(arr.begin(),arr.end(),x) it will return iterator if need index substract arr.begin()
<!--ID: 1779234698678-->


Q: what is stl for num>x
A: upper_bound(arr.begin(),arr.end(),x)
<!--ID: 1779234698685-->



Q: [852. Peak Index in a Mountain Array](https://leetcode.com/problems/peak-index-in-a-mountain-array/) do it own no solution for vivek method what is condition think there is a condition
follow up is this [162. Find Peak Element](https://leetcode.com/problems/find-peak-element/) try vivek method remember default ans kya set karna hai in vivek method when all are 0 then answer wont update think two valid condition for 0000111
try vivek gupta method 
A: https://leetcode.com/problems/find-peak-element/submissions/2004955259/
https://leetcode.com/problems/find-peak-element/submissions/2007659889/
how to divide and how to handle it think do it own
vivek gupta kind of solution
condition arr[mid]>arr[mid+1]
 https://leetcode.com/problems/peak-index-in-a-mountain-array/
 another cases binary search https://leetcode.com/problems/peak-index-in-a-mountain-array/submissions/2007600344/
<!--ID: 1779221769372-->




Q: [Leetcode 33 Search in Rotated Sorted Array I](https://leetcode.com/problems/search-in-rotated-sorted-array/description/) 
What are two different region jiske basis pe divide ho rha hai
?
A: [Leetcode 81 Search in Rotated Sorted Array II](https://leetcode.com/problems/search-in-rotated-sorted-array-ii/) 
source [takeuforward](https://www.youtube.com/watch?v=w2G2W8l__pc&list=PLgUwDviBIf0pMFMWuuvDNMAkoQFi-h0ZF&index=6)
why without duplicate code not work
failed test case 3 1 2 3 3 3 3 3 3
here mid, left and right all equal hence it needed to shrink by one on both side.
just need to discard write a condition if mid left and right are equal then right++ and left++
how to proceed the original problem
it will work for maybe duplicate problem.
source: sanket singh yt video algocamp [link](https://www.youtube.com/watch?v=rkHV8y0V_Yc)
bruteforce simple linear search easy
how to optimize from o(n) next is logn so binary search
now how to proceed
think how to divide the search space into parts such that both are different based on some property
draw graph
it has two parts
left sorted and right sorted parts
agar mid calculate karenge then
mid can be in two parts either left sorted or right sorted part
the two parts are one sorted part and other is unsorted use the sorted part to discard one half check the given element konse part me hoga
now do the coding own if not see the code
link:https://leetcode.com/problems/search-in-rotated-sorted-array/submissions/2004215704/
another https://leetcode.com/problems/search-in-rotated-sorted-array/submissions/2006777370/ for skipping duplicates
we can also solve it by first find the min element then do binary searach on left part and right part
code
```c++
int search(vector<int>& nums, int target) {
        int n=nums.size();
        int left=0;
        int right=n-1;
        while(left<=right){
            int mid=(right+left)/2;
            if(nums[mid]==target) return mid;
            //now check which part it is lies mid in upper or lower curve
            if(nums[mid]>=nums[left]){
                //we are in upper part
                //left part is always sorted so use it
                if(target>=nums[left] and target < nums[mid]){
                    right=mid-1;
                }
                else{
                    left=mid+1;
                }
            }
            else{
                //we are in lower part
                //right part is sorted so use it
                if(target<=nums[right] and target > nums[mid]){
                    left=mid+1;
                }
                else{
                    right=mid-1;
                }
            }
        }
        return -1;
    }
```
<!--ID: 1778963005722-->




Q: [Leetcode 153 Find minimum in rotated sorted Array I](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/description/) 
if you are doing with bs way what would be the default value when it work when it not.
?
A:  arr[mid]<arr[0] 1st
arr[mid]<=arr[n-1] 2nd
follow up problem
[Leetcode 154. Find Minimum in Rotated Sorted Array II](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array-ii/)
one more follow-up
https://takeuforward.org/plus/dsa/problems/find-out-how-many-times-the-array-is-rotated
easy hai same as previous parts 
for optimal
mid can be in two part upper half or lower half
if upper half min will be right
else left
now how to find the min element
now code by vivek gupta best one to remember what should be default
```c++
bool check(int mid,vector<int>& nums){
        return nums[mid]<nums[0];
    }
    int findMin(vector<int>& nums) {
        int n=nums.size();
        int left=0,right=n-1;
        int ans=0;
        while(left<=right){
            int mid=right+(left-right)/2;
            if(check(mid,nums)){
                ans=mid;
                right=mid-1;
            }
            else{
                left=mid+1;
            }
        }
        return nums[ans];
    }
```
code by striver take u forward
```c++
int findMin(vector<int>& nums) {
        int n=nums.size();
        int left=0;
        int right=n-1;
        int ans=INT_MAX;
        while(left<=right){
            int mid=(left+right)/2;
            if(nums[mid]>=nums[left]){
                ans=min(ans,nums[left]);
                left=mid+1;
            }
            else{
                ans=min(ans,nums[mid]);
                right=mid-1;
            }
        }
        return ans;
    }
```
code by sanket singh discarded not feels good hard implementation.
```c++
int findMin(vector<int>& nums) {
        int n=nums.size();
        int left=0;
        int right=n-1;
        while(left<=right){
            int mid=(left+right)/2;
            if(nums[left]<=nums[right]) return nums[left];
            if(mid+1<=n-1 and nums[mid+1]<nums[mid]){
                return nums[mid+1];
            }
            if(mid-1>=0 and nums[mid-1]>nums[mid]) return nums[mid];
            if(nums[mid]>nums[left]){
                left=mid+1;
            }
            else{
                right=mid-1;
            }
        }
        return -1;
    }
```
<!--ID: 1778963067608-->





Q: Given a sorted array of length n having integers in the range 0,n-2. Every element is present once but only one element is present twice. Find the repeated element. Do in less than O(n).
?
A: for this use binary search source algocamp bs sanket singh
now mid
arr[mid] = = mid-1 if this is true means
answer is left or arr[mid] is answer check a test case why.
gfg article link https://www.geeksforgeeks.org/dsa/find-repeating-element-sorted-array-size-n/
```c++
while(left<=right){
      int mid=(left+right)/2;
      if(arr[mid]==mid-1){
           if(arr[mid]==arr[mid-1]){
              ans=arr[mid];
           }
           right=mid-1;
      }
      else{
           left=mid+1;
      }
}
```
<!--ID: 1778963067615-->




Q: [540. Single Element in a Sorted Array](https://leetcode.com/problems/single-element-in-a-sorted-array/)
?
A: using binary search how will i divide the array into two parts do indexing check and figure out.
src codestorywithmik and striver take u forward
two codes possible but striver i like it
how to find two parts just index them check parity stuff then discard halves.
code
```c++
int singleNonDuplicate(vector<int>& nums) {
        int n=nums.size();
        if(n==1){
            return nums[0];
        }
        if(nums[0]!=nums[1]){
            return nums[0];
        }
        if(nums[n-1]!=nums[n-2]){
            return nums[n-1];
        }
        int left=1;
        int right=n-2;
        while(left<=right){
            int mid=(left+right)/2;
            if(nums[mid]!=nums[mid-1] and nums[mid]!=nums[mid+1]){
                return nums[mid];
            }
            if((mid%2==0 and nums[mid]==nums[mid-1])or
            (mid%2==1 and nums[mid]==nums[mid+1])){
                right=mid-1;
            }
            else{
                left=mid+1;
            }
        }
        return -1;
    }
```
<!--ID: 1778963067622-->



Q: https://maang.in/problems/Bitonic-Array-107 another link https://www.interviewbit.com/problems/search-in-bitonic-array/ 
Statement
Given a bitonic array AA consisting of NN integers and an integer QQ. In each query, you will be given an integer KK, find the positions of KK in AA. Integer KK exists in AA.
A bitonic array is a sequence with A[1]<A[2]<A[3]…A[k]>A[k+1]>A[k+2]…>A[N]A[1]<A[2]<A[3]…A[k]>A[k+1]>A[k+2]…>A[N] for some 1≤K≤N1≤K≤N.
input
The first line contains TT, the number of test cases (1≤T≤100001≤T≤10000). For each test case, the first line contains two space separated integers N,QN,Q where 1≤N≤1051≤N≤105, 1≤Q≤1061≤Q≤106. The second line contains NN space-separated integers A1,A2,…,ANA1​,A2​,…,AN​ where −109≤Ai≤109−109≤Ai​≤109. The next QQ lines each contain an integer KK, where −109≤K≤109−109≤K≤109. Sum of NN and QQ across all test cases ≤106≤106.
For each test case print the positions of KK in AA in sorted order in a new line. **Positions are 1-indexed.**
constraint
1≤T≤10000 1≤N≤1051≤N≤105 1≤Q≤1061≤Q≤106 −109≤Ai,K≤109−109≤Ai​,K≤109 Sum of NN and QQ across all test cases ≤106≤106
A: find the peak (maximum) element of the bitonic array using binary search. Then for each query KK, perform binary search on the increasing left part and the decreasing right part. For the sample, positions of queried values are printed (1-indexed).
```c++
#include<bits/stdc++.h>
#define int long long
using namespace std;
bool check(int mid,vector<int> &arr){
    if(mid+1>=arr.size()) return 1;
    if(arr[mid]>=arr[mid+1])return 1;
    return 0;
}
void myf() {
    int n,q;cin>>n>>q;
    vector<int> v(n);
    for(int i=0;i<n;i++){
        cin>>v[i];
    }
    int left=0;
    int right=n-1;
    int ans1=-1;
    while(left<=right){
        int mid=right+(left-right)/2;
        if(check(mid,v)){
            ans1=mid;
            right=mid-1;
        }
        else{
            left=mid+1;
        }
    }
    int miniindx=ans1;
    while(q--){
        int k;cin>>k;
        int left1=0;
        int right1=miniindx-1;
        vector<int> ans;
        while(left1<=right1){
            int mid=right1+(left1-right1)/2;
            if(v[mid]==k) {
                ans.push_back(mid+1);
                break;
            }
            if(v[mid]>k){
                right1=mid-1;
            }
            else{
                left1=mid+1;
            }
        }
        int left2=miniindx;
        int right2=n-1;
        while(left2<=right2){
            int mid=right2+(left2-right2)/2;
            if(v[mid]==k) {
                ans.push_back(mid+1);
                break;
            }
            if(v[mid]>k){
                left2=mid+1;
            }
            else{
                right2=mid-1;
            }
        }
        sort(ans.begin(),ans.end());
        for(auto it:ans){
            cout<<it<<" ";
        }
        cout<<endl;
    }
}
int32_t main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    int t;
    t=1;
    cin>>t;
    while(t--) {
        myf();
    }
    return 0;
}
```
<!--ID: 1779227011159-->






























