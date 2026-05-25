
TARGET DECK: DSA::Array::Contribution Technique


https://srinivastechblog.hashnode.dev/contribution-technique-the-secret-trick-to-faster-dsa-solutions?t=1770904730168

https://medium.com/@alok.g.v/data-structures-and-algorithms-dsa-concept-subarrays-part-2-cb7f4432aba6

https://youkn0wwho.academy/topic-list/contribution_technique


### problems on contribution thinking reverse


Q: Given array find sum of all subarrays
Link-https://www.geeksforgeeks.org/problems/sum-of-subarrays2229/1
A: Method 1 contribution technique
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
<!--ID: 1779507707035-->


Q: ![[Pasted image 20260525061819.png]]
A: Same as sum of all subarrays do column vise
How many times each element is coming in all triplet
So we have.   _  _ _ one we knw one other can be anything else apart from chosen
we know one element say mid or first now we have to select any two element from the rest of the elements
So n-1C2 × arr[I] for all elements.
<!--ID: 1779670288719-->


Q: ![[Pasted image 20260525063447.png]]
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



 [2262. Total Appeal of A String](https://leetcode.com/problems/total-appeal-of-a-string/) 
It can be solved by use ending at j index thing to solve it) and two pointer(vivek method)
its code:
```c++
long long appealSum(string s) {
        vector<int> last(26, -1);
        long long ans = 0;
        long long cur = 0;
        for(int i = 0; i < s.size(); i++) {
            cur += i - last[s[i] - 'a'];
            ans += cur;
            last[s[i] - 'a'] = i;
        }
        return ans;
    }
```
but need to solve using contribution technique many other possible way to solve
codingmohan video:https://www.youtube.com/watch?v=uuBBafS9rgU his solution and code is simple
think of smaller problem of having only two characters, total no of substring atleast 1 1
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
