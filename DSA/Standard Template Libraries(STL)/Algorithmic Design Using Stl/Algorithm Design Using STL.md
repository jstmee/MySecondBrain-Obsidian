

TARGET DECK: DSA::Standard Template Libraries(STL)::Algorithm Design Using STL



Q: Design a data structure in form of struct where insert, remove, sum getmax and getdistinct is possible we will getting a number everytime do it own easy hai
A: do it own here is code
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
<!--ID: 1780662327885-->
