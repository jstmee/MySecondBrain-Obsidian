
https://maang.in/playlists/STL-Applications-3395?resourceUrl=cs87-cp504-pl3395-rs7920&returnUrl=%5B%22%2Fcourses%2FSTL-in-C-87%3Ftab%3Dchapters%22%5D



first part is solution of this https://maang.in/problems/Buy-Maximum-Objects-II-74 and its first part using stl which is easy


algorithm design
ques need to implement a structure where insertion of element and sum till now is very fast in o(1)
Sol
```c++
struc bag{
	int currsum=0;
	void insert(int x){
		currsum+=x;
	}
	int sum(){
		return currsum;
	}
}
```

now we have to implement the maximum number till now how??
```c++
struc bag{
	int currsum=0;
	int currmax=INT_MIN;
	void insert(int x){
		currsum+=x;
		currmax=max(currmax,x);
	}
	int sum(){
		return currsum;
	}
	int getmax(){
		return currmax;
	}
}
```
now i also want to get distinct no of element till now distinct() just keep set
```c++
struc bag{
	int currsum=0;
	int currmax=INT_MIN;
	set<int> st;
	void insert(int x){
		currsum+=x;
		currmax=max(currmax,x);
		st.insert(x);//logn 
	}
	int sum(){
		return currsum;
	}
	int getmax(){
		return currmax;
	}
	int getdistinct(){
		return st.size();//it is of o(1) for all stl
	}
}
```
now we want to support remove a element single occurence out of this bag how??use map it maintain in sorted manner its last value stores maximum
```c++
struc bag{
	int currsum=0;
	int currmax=INT_MIN;
	//set<int> st;//
	map<int,int> mp;
	void insert(int x){
		currsum+=x;
		//currmax=max(currmax,x);
		//st.insert(x);//logn 
		mp[x]++;
	}
	void remove(x){
		currsum-=x;
		mp[x]--;
		if(mp[x]==0) mp.erase(x);
	}
	int sum(){
		return currsum;
	}
	int getmax(){
	    auto it=mp.rbegin();
		//return currmax;
		return  *it.first;//we can also write here it->first
	}
	int getdistinct(){
		//return st.size();//it is of o(1) for all stl
		return mp.size();
	}
}
```