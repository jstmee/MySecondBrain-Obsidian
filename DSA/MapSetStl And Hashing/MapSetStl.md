TARGET DECK: DSA::MapSetStl And Hashing::MapSetStl

1296 https://leetcode.com/problems/divide-array-in-sets-of-k-consecutive-numbers/

846 [https://leetcode.com/problems/hand-of-straights/description/](https://leetcode.com/problems/hand-of-straights/description/)         
solution is aryan mittal video               
most imp is time complexity



we can use lower bound upper bound in set


Basic hashing question use of set and map
https://leetcode.com/problems/maximum-square-area-by-removing-fences-from-a-field/
https://leetcode.com/problems/count-caesar-cipher-pairs/


hashing + prefix
https://leetcode.com/problems/stable-subarrays-with-equal-boundary-and-interior-sum/



Q: [3043. Find the Length of the Longest Common Prefix](https://leetcode.com/problems/find-the-length-of-the-longest-common-prefix/) read the problem and answer think
A: try bruteforce use of map set stl
submission: https://leetcode.com/problems/find-the-length-of-the-longest-common-prefix/submissions/2009325349/
#MapSetSTL #UseSTL #OnlySTL 
<!--ID: 1779389882400-->




Q: [2006. Count Number of Pairs With Absolute Difference K](https://leetcode.com/problems/count-number-of-pairs-with-absolute-difference-k/)
A: easy hai you can solve it own
#MapSTL #UseSTL #OnlySTL  
<!--ID: 1780217540668-->


Q: https://www.codechef.com/problems/DIVSUBS
A: given we have to find subsets and check whether there exist or not yes or not so what if we find any subarray present now according to pigeon hole there should be 1 subarray for the given condition
The answer is always YES irrespective of the array.  
Consider the _pref[i]_ = (_A1 + A2 + ... + Ai_) mod _N_. Base conditions _pref[0]_ = 0.  
Observe that there are _N_ + 1 values in the _pref_ array _(pref[0], pref[1], ...., pref[N])_, but the remainder can take in total _N_ values only (0, 1, ..., _N_ - 1). That means, there exists at least one pair in the _pref_ array which has the same entries.    
Suppose _pref[j] == pref[k]_, and _k_ > _j_. Then we can conclude that (_Aj+1 + ... + Ak_) is divisible by _N_.
hence, this solution.
submission link- https://www.codechef.com/viewsolution/1295750076
similar problems
[560. Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/)
[974. Subarray Sums Divisible by K](https://leetcode.com/problems/subarray-sums-divisible-by-k/) 
[2006. Count Number of Pairs With Absolute Difference K](https://leetcode.com/problems/count-number-of-pairs-with-absolute-difference-k/) 
#PigeonholePrinciple #PrefixSum #MapSetSTL 
<!--ID: 1782490775241-->




Q: given an array of sz n find no of pairs i j such that i< j and  arri x j=arrj x i
A: src is vivek video link - https://maang.in/playlists/Greedy-Sweepline-Day-1-4961?resourceUrl=pl4961-rs8461&returnUrl=%5B%22%2Fcohorts%2FAZ-Premium-Cohort-13-64%3Ftab%3Dassignments%22%5D
idea based on fractions one thing to keep in mind fraction can not have denomintor 0 so always try to use gcd reduce the fraction to lowest term which is same for any term
reduce the given form in arri/i=arrj/j and normal things wont work why because it is in fraction no two faction can be equal it is approx value.
gfg article- https://www.geeksforgeeks.org/dsa/count-number-of-pairs-i-j-from-an-array-such-that-arri-j-arrj-i/
```c++
pair<int,int> getredfrac(int a,int b){
	if(a==0&&b==0) return make_pair(0,0);
	if(a==0) return make_pair(1,0);
	if(b==0) return make_pair(0,1);
	//how to handle negative number easy hai think bas
	int x=__gcd(a,b);
	return make_pair(a/x,b/x);
}
int main(){
	int n;cin>>n;
	int arr[n];
	map<pair<int,int>> mp;
	int ans=0;
	for(int i=0;i<n;i++){
		cin>>arr[i];
		ans+=(mp[arr[i],i]);
		mp[getredfrac(arr[i],i)]++;
	}
	cout<<ans<<endl;
}
```
<!--ID: 1781368370814-->


Q: [149. Max Points on a Line](https://leetcode.com/problems/max-points-on-a-line/)
A: src vivek video - link https://maang.in/playlists/Greedy-Sweepline-Day-1-4961?resourceUrl=pl4961-rs8461&returnUrl=%5B%22%2Fcohorts%2FAZ-Premium-Cohort-13-64%3Ftab%3Dassignments%22%5D
bruteforce is go every pairs find the line and then check every point who lie on this line
this is easy have done it own- https://leetcode.com/problems/max-points-on-a-line/submissions/2031980932/
now try for n=2000 do it in n^2
use of map how store slope count in map now slope is fraction use faction reduce method to do this submission- https://leetcode.com/problems/max-points-on-a-line/submissions/2031991906/
make sure to handle negative number in fract in the leetcode version it has given all points are unique how in code https://leetcode.com/problems/max-points-on-a-line/submissions/2044803984/
how to handle if points are not uniques 2,2 2,2 3,3 3,3 for this answer should be 4 for this see the video again and again to understand it is because we return 0,0 for the same numbers.
submission of not unique - https://leetcode.com/problems/max-points-on-a-line/submissions/2032005313/
<!--ID: 1781369999247-->


Q: [1865. Finding Pairs With a Certain Sum](https://leetcode.com/problems/finding-pairs-with-a-certain-sum/) just an observation based question
A: submission- https://leetcode.com/problems/finding-pairs-with-a-certain-sum/submissions/2048100848/
<!--ID: 1782581456148-->



