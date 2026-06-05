

https://maang.in/playlists/STL-Applications-3395?resourceUrl=cs87-cp504-pl3395-rs7921&returnUrl=%5B%22%2Fcourses%2FSTL-in-C-87%3Ftab%3Dchapters%22%5D


Check balance parenthesis
Use a depth variable
Condition for balanced is depth at last should be 0 and depth at any point should not neg
Follow up if there are more than 1 type of bracket then depth thing won't work use of stack to solve it. Because relative order is not maintained using depth.
For any type of bracket closed last should be of same type of open bracket.
Convert to numbers +1,+2,+3,-1,-2,-3
Now try to do the code yourself for valid parenthesis leetcode 20
For code see the video.

first basis question 
Checked balanced parentheses 
()()((())) For this
By using depth variable if open depth +1 close depth-1
By using ( as +1 and ) as -1 it can extend to more if there are different brackets
Depth=(# of open - # of closed)
Now answer is if depth at last is 0 and depth at any points is not negative.
```c++
int solve(string s){
	//string s;cin>>s;
	int depth=0;
	int is_balanced=1;
	for(auto v:s){
		if(v=='('){
			depth++;
		}
		else{
			depth--;
		}
		if(depth<0){
			is_balanced=false;
			break;
		}
	}
	if(depth!=0) is_balanced=0;
	if(is_balanced) return true;
	else return false;
}
```
follow up is valid parentheses leetcode 20
next what if multiple types of characters are there how to solve it
same way but use of stack efficient implementation is important by using and it cannot be solved by depth variable alone why???? We need order maintenance hence stack
how to implement it without to0 much cases
convert all the opening bracket with +1,+2,+3 and closing
AS -1,-2,-3 can be extend to more 
```c++
solve(){
	string s;
    map<char,int> mp;
    mp['(']=+1;
    mp['[']=+2;
    mp['{']=+3;
    mp[')']=-1;
    mp[']']=-2;
    mp['}']=-3;
    stack<int> st;
    isbalanced=1;
    for(auto it:s){
	    int val=mp[it];
	    if(val>0){
		    //open bracket
		    st.push(val);
	    }
	    else{
		    if(st.size()>0 and st.top()+val==0){
			    st.pop();
		    }
		    else{
			    isbalacned=0;
			    break;
		    }
	    }
    }
    if(st.size()>0) isbalance=0;
    return isbalanced;
}
```