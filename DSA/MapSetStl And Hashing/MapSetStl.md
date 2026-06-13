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
use of map how store slope count in map now slope is fraction use faction reduce method to do this
make sure to handle negative number in fract in the leetcode version it has given all points are unique 
submission- https://leetcode.com/problems/max-points-on-a-line/submissions/2031991906/
how to handle if points are not uniques 2,2 2,2 3,3 3,3 for this answer sould be 4 for this see the video again and again to understand it is because we return 0,0 for the same numbers.
submission of not unique - https://leetcode.com/problems/max-points-on-a-line/submissions/2032005313/
<!--ID: 1781369999247-->


