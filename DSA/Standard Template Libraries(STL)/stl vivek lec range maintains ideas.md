
https://maang.in/playlists/STL-Applications-3395?resourceUrl=cs87-cp504-pl3395-rs7927&returnUrl=%5B%22%2Fcourses%2FSTL-in-C-87%3Ftab%3Dchapters%22%5D
https://maang.in/playlists/STL-Applications-3395?resourceUrl=cs87-cp504-pl3395-rs7928&returnUrl=%5B%22%2Fcourses%2FSTL-in-C-87%3Ftab%3Dchapters%22%5D


Quest given n ranges many range and then q query of type y you need to tell at y how many ranges are present or covers end points are included in range count no of interval in which y lies
constraint first is n<=1e3, q<=1e3 and li ri,y<=1e9 this is easy bruteforce
second is n,q<=1e5 and li ri,y<=1e9 try to count which do not cover
third is n,q<=1e5 and li ri, y <=1e5 this can be solved using partial sum or sweep line
now code for second
answer is total - (no of ri< y+ no of li>y) using lower bound and upper bound 
```c++
write it own
```


Qu 1 fill the range [l,r] that is merging of two interval that is union
2 clear range [l r]     remove this range if it covered.
3 check point x       whether that point is active not mean this point is present in any interval or not
4 check interval inside [x,y] check if any point is active in range xy
constraint q<=1e5, l,r<=1e9 x,y <=1e9 all points are distinct
how?? we need to maintain sorted in set of pair
need to make cases 
```c++
struct range_maintainance{
    set<pair<int,int>> st;
	void fill_range(int l,int r){
		//find partial merging at start and ending ignore middle ranges then merge
		//removed from l 
		//removed frm r
		//removed from between
		
	}
	void clear_range(int l,int r){
	}
	bool check_point(int x){
		auto it=upper_bound({{x,1e9}})//imp line for using upper bound in pair of set
		if(it==it.begin()){
			return 0;
		}
		else{
			it--;
			if(it->second>=x){
				return 1;
			}
			else return 0;
		}
	}
	bool check_range_any(int x,int y){
		auto it=st.upper_bound({x,1e9});
		if(it!=st.end()){
			if(it->first<=y){
				return 1;
			}
		}
		//there is 1 more case need to think which and why
		return check_point(x);
	}
	bool check_range_all(int x,int y){
		auto it=upper_bound({{x,1e9}})//imp line for using upper bound in pair of set
		if(it==it.begin()){
			return 0;
		}
		else{
			it--;
			if(it->second>=y){
				return 1;
			}
			else return 0;
		}
	}
};
```