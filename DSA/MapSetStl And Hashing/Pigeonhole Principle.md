

TARGET DECK: DSA::Array::Pigeonhole Principle

video link
https://maang.in/playlists/Greedy-Sweepline-Day-5-4962?resourceUrl=pl4962-rs8460&returnUrl=%5B%22%2Fcohorts%2FAZ-Premium-Cohort-13-64%3Ftab%3Dassignments%22%5D


https://www.youtube.com/watch?v=4VyJrH3ynqg&list=PLEPYybVRtwQdv0dGnfmCj9I4_d0GLPVGt&index=4

5 pigeon and 4 holes then at least 1 hole has 2 pigeon


problem discuss by vivek was https://www.codechef.com/problems/DIVSUBS 



Q: You have given an array of _n_ numbers and a positive integer _m_. Lets define _c(i, j) = |ai - aj|_.  
Your task is to find the product of _c(i, j)_ for all 1 ≤ _i_ < _j_ ≤ _n_. Since this product can be very large, print it with modulo _m_. src https://maang.in/problems/Pair-Products-282
A: Let's consider 2 cases.
1. _n_ ≤ _m_. Then we can calculate this product directly in _O(n2)_.
2. _n_ > _m_. Note that there are only _m_ possible remainders under division by _m_, so some 2 numbers of _n_ have the same remainder. Then their difference is divisible by _m_, so the entire product is 0 mod _m_.
similar problem
https://www.codechef.com/problems/DIVSUBS 
#PigeonholePrinciple 
<!--ID: 1782492320369-->
