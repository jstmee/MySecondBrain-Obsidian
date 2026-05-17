
TARGET DECK: DSA::Binary Search::Popular Problems On Binary Search
TAGS: Purely Binary Search

#flashcards/DSA/BinarySearch/PopularProblemsOnBinarySearch #PureBinarySearchProblems


Q: [Leetcode 33 Search in Rotated Sorted Array I](https://leetcode.com/problems/search-in-rotated-sorted-array/description/)
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

<!--SR:!2026-05-19,3,250-->


Q: [Leetcode 153 Find minimum in rotated sorted Array I](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/description/)
?
A: follow up problem
[Leetcode 154. Find Minimum in Rotated Sorted Array II](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array-ii/)
one more follow-up
https://takeuforward.org/plus/dsa/problems/find-out-how-many-times-the-array-is-rotated
easy hai same as previous parts 
for optimal
mid can be in two part upper half or lower half
if upper half min will be right
else left
now how to find the min element
now code by vivek gupta best
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
code by sanket singh
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

<!--SR:!2026-05-19,3,250-->



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

<!--SR:!2026-05-19,3,250-->


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

<!--SR:!2026-05-19,3,250-->




















