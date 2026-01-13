

 ## Need to cover
- [ ] codestorywithmik
- [ ] takeuforward



[Leetcode 1339](https://leetcode.com/problems/maximum-product-of-splitted-binary-tree/description/)  #TreeDp #Recursion #DFS #MapSTL #Tree #BinaryTree
have solve it my own tree dp problem which is not the most optimal way
Solve it using most optimal approach need to revise it again.

---

## LCA(Lowest Common Ancestors)

Q1
[Leetcode 236](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/) #Recusion #MapSTL #Tree #BinaryTree #DFS 
use of recursion only one more solution not optimal use of array
follow up problems
[Leetcode 865](https://leetcode.com/problems/smallest-subtree-with-all-the-deepest-nodes/description/) and [Leetcode 1123](https://leetcode.com/problems/lowest-common-ancestor-of-deepest-leaves/) 
[Leetcode 104](https://leetcode.com/problems/maximum-depth-of-binary-tree/) height of tree
##### method 1 
use of height of tree, lca, map, vector [link](https://leetcode.com/problems/smallest-subtree-with-all-the-deepest-nodes/submissions/1879877003/) 
##### method 2 
remove call for lca function previous it is called many times just call it two time only needed.
##### method 3  
modify lca function code so that is give correct answer try to use map but it used 2 pass o(2n) Most optimal is only o(n). [Link](https://leetcode.com/problems/smallest-subtree-with-all-the-deepest-nodes/submissions/1879898026/) 
##### method 4 
1 pass solution exist codestorywithmik most optimal code for this question.
in 1 recursion try to find the height and lca in reverse order
try to make recursive function which return depth and lca of a root in 1 time when it is at any root.
[Link](https://leetcode.com/problems/smallest-subtree-with-all-the-deepest-nodes/submissions/1879946522/) 