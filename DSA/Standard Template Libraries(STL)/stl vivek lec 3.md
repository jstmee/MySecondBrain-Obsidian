


Two array types
1.window maintain sliding window
2.subarray finding



Ques find min of every k size window of an array 
Similar no of district of every k window
Find max
No of even no in every  k length
Find no of prime no in every k length
All of these have almost same code template
It is like find something(f(x)) all x of length k in array.
Simple is n.k solution
For a subarray we need to find min so that we can also find the min of next subarray after removing but how?? Two thing ways to optimize
1.either observation
2.things /information are shared
Now write requirement 
We have to maintain a data structure which support erase, and get min element
This can easily be done by multiset stl
This can be solved using deque most optimized(monotone deque)
Now if the question change no of distinct batao then how?? We have to create a data structure using map
Now to optimize original question to oofn
Obs is whenever we get min element element greater can never be answer this is main core obs
Now think of deque do dry run using this obs then code it own.
Time complexity of code will o(n2)but amortised complexity is oofn 

