

TARGET DECK: DSA::Standard Template Libraries(STL)::Algorithm Design Using STL


more sheet on design https://docs.google.com/spreadsheets/d/1tKUIxkCscKuSY-Q7Mq3EG1amc6XZYkIf8ty8HrkEw4E/edit?gid=1429868306#gid=1429868306



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

Q: design a structure where we have to insert x  and given k find the sum of top k max elements
A: answer we can use multiset here as well multiset and priority queue both have same things need to remember this multiset is much better than all pq functions are present but important for interviews  but tit take some extra time. thats all otherwise multiset
```c++
struct bag{
	int k;
	priority_queue<int> pq;
	int sumk;
	void init(int _k){
		k=_k;
		sumk=0;
	}
	void insert(int x){
		sum+=x;
		pq.push(-x);//logn
		if(pq.size()>k){//o1
			int sm=-pq.top();//o1
			pq.pop();//logn
			sumk-=sm;
		}
	}
	int topk(){
		return sumk;
	}
};
```
<!--ID: 1780748483715-->



Q:  implement structure where insert, removed, getsum of top k elements is supported efficiently
A: now we have to support remove in this operation as well for this we need to use 2 structure 
one for k topk and other is for the other numbers. that is two partition
as we have to remove from both part so multiset should be used from the both sets and partition doing coz we have to efficiently. use we are maintaining a k size fixed and inserting removing it here and there
```c++
struct bag{
	int k;
	//we needed to partition
	multiset<int> topk,removed;
	int sumk=0;
	void init(int _k){
		k=_k;
		sumk=0;
		topk.clear();
		removed.clear();
	}
	void insert(int x){
		topk.insert(x);
		sumk+=x;
		if(topk.size()>k){
			auto it=topk.begin();
			sumk-=*it;
			removed.insert(*it);
			topk.erase(it);
		}
	}
	void removed(int x){
		if(topk.find(x)!=topk.end()){
			topk.erase(topk.find(x));
		}
		else if(removed.find(x)!=removed.end()){
			removed.erase(removed.find(x));
		}
		if(topk.size()<k and removed.size()>0){
			auto it=removed.end();
			it--;
			int val=*it;
			removed.erase(it);
			topk.insert(val);
			sumk+=val;
		}
	}
	int getSumOfTopK(){
		return sumk;
	}
};
```
<!--ID: 1780748798231-->


Q: design a structure where we can insert a number remove and find the median at any points
relation question but easy one : https://leetcode.com/problems/find-median-from-data-stream/description/ but how can i solve it with priority queue as we don't need remove operation here.
there is one more question related to this https://atcoder.jp/contests/abc458/tasks/abc458_d
same as partition into two parts where we we have maintain size we don't knw. think more he has shown the code he has shown write code again in another video 
same now find mean median and mode, variance including insert and remove
https://maang.in/playlists/STL-Applications-3395?resourceUrl=cs87-cp504-pl3395-rs7925&returnUrl=%5B%22%2Fcourses%2FSTL-in-C-87%3Ftab%3Dchapters%22%5D
A: means is sum of all number / size of number this is easy in previous upar hai that is by keeping sum and count variable
median is middle part
mode is most frequent element
variance is summation of (xi-means)^2/n
this gives xi^2 -2xi(means)+means^2 /n
this gives 
summation of xi^2 /n- means^2  extra is only summation of x^2 so calculated as sum so variance can be found o(1)
median we need two partition things using multisets 
mode is most frequent element think how??
for this we need to maintain two stl which does frequency count and reverse multiset of pair of map freq and element
```c++
struct data_dashboard{
	//mean
	int sum=0;
	int cnt=0;
	//variance
	int sumsq=0;
	//mode
	map<int,int> frq;
	multiset<pair<int,int>> freq_order;
	//median
	multiset<int> low,high;
	void balance(){
		while(low.size()<high.size()){
			int x=*high.begin();
			high.erase(high.find(x));
			low.insert(x);
		}
		while(low.size()>high.size()+1){
			int x=*low.rbegin();
			low.erase(low.find(x));
			high.insert(x);
		}
	}
	void insert(int x){
		cnt++;
		sum+=x;
		sumsq+=x*X;
		//now mode
		if(freq_order(make_pair(freq[x],x))!=freq_order.end()){
			freq_order.erase((freq_order(make_pair(freq[x],x))));
		}
		freq[x]++;
		freq_order.insert((make_pair(freq[x],x)));
		//median
		if(low.size()==0) low.insert(x);
		else if(x<=(*low.rbegin())){
			low.insert(x);
		}
		else{
			hi.insert(x);	
		}
		balance();
	}
	void remove(int x){
		cnt--;
		sum-=x;
		sumsq-=x*x;
		//mode now for mode
		if(freq_order(make_pair(freq[x],x))!=freq_order.end()){
			freq_order.erase((freq_order(make_pair(freq[x],x))));
		}
		freq[x]--;
		if(freq[x]){
			freq_order.insert((make_pair(freq[x],x)));
		}
		//median
		if(high.find(x)!=high.end()){
			high.erase(high.find(x));
		}
		else if(low.find(x)!=low.end()){
			low.erase(low.find(x));
		}
		balance();
	}
	double mean(){
		return sum/cnt;
	}
	double variance(){
		return sumsq/cnt-means()*mean();
	}
	double mode(){
		//returning any no with highest frequency
		return freq_order.rbegin()->second;
	}
	double median(){
		if(cnt%2){
			return *low.rbegin();
		}
		else{
			return (*low.rbegin())+(*high.begin())/2.0;
		}
	}
};
```
<!--ID: 1780748917808-->


Q: [1352. Product of the Last K Numbers](https://leetcode.com/problems/product-of-the-last-k-numbers/) solve it using o1 complexity only
A: src solution is vivek video - https://maang.in/playlists/Algorithmic-Design-Ideas-3400?resourceUrl=cs87-cp504-pl3400-rs7938&returnUrl=%5B%22%2Fcourses%2FSTL-in-C-87%3Ftab%3Doverview%22%5D
method 1 is maintain a list then find the product of last k elements; which is very easy do not need to implement it;
solve it suing o1 time complexity
using of product prefix array how will we handle 0 case 
https://leetcode.com/problems/product-of-the-last-k-numbers/submissions/2046269323/
<!--ID: 1782431956019-->
