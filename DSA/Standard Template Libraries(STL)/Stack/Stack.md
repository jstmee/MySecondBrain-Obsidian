
TARGET DECK: DSA::Standard Template Libraries(STL)::Stack


Q: Checked balanced parentheses basic
()()((())) For this
A: By using depth variable if open depth +1 close depth-1
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
#Stack #withoutstack #StackSTL #UseOfStack 
<!--ID: 1780666093109-->


Q: [20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/) do it your own easy hai 
A: same way but use of stack efficient implementation is important by using and it cannot be solved by depth variable alone why???? We need order maintenance hence stack
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
#Stack #StackSTL #UseOfStack 
<!--ID: 1780666229491-->



Q: [921. Minimum Add to Make Parentheses Valid](https://leetcode.com/problems/minimum-add-to-make-parentheses-valid/) there is o(1) space solution available solve it with stack and without stack.
A:  depth means no of unmatched '(' seen so far so when depth is negative we need one extra bracket and we have to set depth to 0 again. o(1) space solution https://leetcode.com/problems/minimum-add-to-make-parentheses-valid/submissions/2023329458/
submission link - https://leetcode.com/problems/minimum-add-to-make-parentheses-valid/submissions/2023323405/
#Stack #withoutstack #StackSTL #UseOfStack 
<!--ID: 1780667197408-->


Q: [1472. Design Browser History](https://leetcode.com/problems/design-browser-history/)
A: method 1 using two stacks 
history past use stack use 3 things first curr to track where are u currently past  and future stack.
link- https://leetcode.com/problems/design-browser-history/submissions/2047987843/
it can also be solved using linkedlist
using vector
<!--ID: 1782574649747-->





[1963. Minimum Number of Swaps to Make the String Balanced](https://leetcode.com/problems/minimum-number-of-swaps-to-make-the-string-balanced/)
src codestorywithmik need to understand again; https://www.youtube.com/watch?v=W61jIP-O8lw&t=585s


