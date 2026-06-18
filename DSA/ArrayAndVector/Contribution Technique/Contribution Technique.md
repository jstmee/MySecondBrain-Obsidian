
TARGET DECK: DSA::Array::Contribution Technique


https://srinivastechblog.hashnode.dev/contribution-technique-the-secret-trick-to-faster-dsa-solutions?t=1770904730168

https://medium.com/@alok.g.v/data-structures-and-algorithms-dsa-concept-subarrays-part-2-cb7f4432aba6

https://youkn0wwho.academy/topic-list/contribution_technique


### problems on contribution thinking reverse


Q: Given array find sum of all subarrays
Link-https://www.geeksforgeeks.org/problems/sum-of-subarrays2229/1 there are two method to solve it first i ending at index i method dp wala and other is contribution technique think in opposite
A: Method 1 contribution technique note this can also be solved using ending at index i sum of subarray method dp method
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
 Now how many times a particular value is coming.
 If we start from nay element how many start can be possible and how many end is possible
 Then multiply them to get.
 xC1xyC1 IS ANSWER.
If we at i the then I+1 line left left
Is total - I+1 total is n+1 lines.
submission for method 2-
<!--ID: 1779507707035-->


Q: You are given an array Arr of N integers. Calculate the sum of Arri+arr[j]+arrk for all triplets of indices (i,j,k) such that 0<=i<j<k<=n-1. Print final answer mod 1e9+7. n<=1e5
A: Same as sum of all subarrays do column vise
How many times each element is coming in all triplet
So we have.   _  _ _ one we knw one other can be anything else apart from chosen
we know one element say mid or first now we have to select any two element from the rest of the elements
So n-1C2 × arr[I] for all elements.
<!--ID: 1779670288719-->


Q: an inversion is define as pair of i,j i< j and arr[i]>arr[j]. Given array of sz n calculate the sum of inversion counts of all possible subarrays. 
A: same as previous think of atomic item it is inversion
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
So overall it will be o(n^2). We can also do this nlogn using advance data structure derive right part.
```c++
void solve(){
	int arr[n];
	int ans=0;
	for(int i=0;i<n;i++){
		for(int j=i+1;j<n;j++){
			if(ar[i]>arr[j]){
				ans+=(i+1)*(n-j);
			}
		}
	}
}
```
<!--ID: 1779671705375-->



Q:  [2262. Total Appeal of A String](https://leetcode.com/problems/total-appeal-of-a-string/) 
A: need to solve using contribution technique many other possible way to solve
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
Now the problem is reduced to find total no of subarray which contains a character vivek method uses total find not contain
It also contains find no of subarray that does not contains x this can be solved using map and without map
How to code it.
```c++
long long appealSum(string s) {
        long long n = s.length();
        long long ans = 0;
        for (char ch ='a'; ch<='z'; ch++) {
            int last = -1;
            long long contrib = n * (n + 1) / 2;
            for (int i = 0; i < n; i++) {
                if (s[i] == ch) {
                    long long len = i - last - 1;
                    contrib -= (len + 1) * len / 2;
                    last = i;
                }
            }
            long long len = n - last - 1;
            contrib -= (len + 1) * len / 2;
            ans += contrib;
        }
        return ans;
    }
```
for total subarray which contain a character directly uses codingmohan method
codingmohan no need to see the video just use ending at j method to find it.
its code basically this is ending at method using contribution
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
method above solution led to this o(n) solution
this method is based on ending at ith index dp method ending at 
its code:
```c++
long long appealSum(string s) {
        long long n=s.size();
        long long ans=0;
        long long curr=0;
        map<char,int> mp;
        for(char c='a';c<='z';c++){
            mp[c]=-1;
        }
        for(int i=0;i<n;i++){
            curr+=(i-mp[s[i]]);
            mp[s[i]]=i;
            ans+=curr;
        }
        return ans;
    }
```
it can also be solved using two pointer method atmostk -atmostk-1 distinct method
another solution
```c++
long long appealSum(string s) {
        long long ans = 0;
        int n = s.size();
        unordered_map<char, int> mp;
        for(int i = 0; i < n; i++) {
            if(mp.find(s[i]) != mp.end()) {
                ans += 1LL * (i - mp[s[i]]) * (n - i);
            }
            else {
                ans += 1LL * (i + 1) * (n - i);
            }
            mp[s[i]] = i;
        }
        return ans;
    }
```
<!--ID: 1779676463418-->


Q: https://atcoder.jp/contests/abc186/tasks/abc186_d
A: sol it is of abs we need to find
for any fix j we have to find it positive and negative contribution because of absolute.
if we sort it then we can easily do this
for fix index j we have  left contribution which will be positive and its right contribution which is negative. Only think what would be left and right
left would be i x v[i] and right would be (n-i-1) x v[i]
submission - https://atcoder.jp/contests/abc186/submissions/76114734 
<!--ID: 1779676923434-->



Q: [828. Count Unique Characters of All Substrings of a Given String](https://leetcode.com/problems/count-unique-characters-of-all-substrings-of-a-given-string/) 
A: use of contribution instead of all substring think in reverse count for all char in how many string it will be unique
rest solution is implementation based ek particular index ya char left side utna he extend ho paega jab tak voh vapis na ajae similarly for right so overall implementation. For this we will use 2d matrix
ek particular character kis kis position pe hai uske store karlenge sath me -1 aur n be dalenge start aur end me fir es par traverse karenge answer nikalne ke liye easy.
source vivek video solution on question link - https://maang.in/problems/Count-Unique-Char-in-Substrings-63
submission link: https://leetcode.com/problems/count-unique-characters-of-all-substrings-of-a-given-string/submissions/2012115389/
<!--ID: 1779679464273-->


Q: [2063. Vowels of All Substrings](https://leetcode.com/problems/vowels-of-all-substrings/)
A: think in reverse way contribution technique contribution of all vowels
read the question what it ask for then count the contribution of each vowels then add all
my own code - https://leetcode.com/problems/vowels-of-all-substrings/submissions/2011951258/
we can also solve it using ending at i index method dp method ending which can be reduce to o(1) space easily.
<!--ID: 1779680726930-->

