

 ## Need to cover
- [ ] codestorywithmik
- [ ] takeuforward



[Leetcode 1339](https://leetcode.com/problems/maximum-product-of-splitted-binary-tree/description/)  #TreeDp #Recursion #DFS #MapSTL #Tree #BinaryTree
have solve it my own tree dp problem which is not the most optimal way
Solve it using most optimal approach need to revise it again.

---

## LCA(Lowest Common Ancestors)

[Leetcode 236](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/) #Recusion #MapSTL #Tree #BinaryTree #DFS 
use of recursion only one more solution not optimal use of array
follow up problems
[Leetcode 865](https://leetcode.com/problems/smallest-subtree-with-all-the-deepest-nodes/description/) and [Leetcode 1123](https://leetcode.com/problems/lowest-common-ancestor-of-deepest-leaves/) 
###### method 1 
use of height of tree, lca, map, vector

```cpp
class Solution {
public:
    map<TreeNode*,int > mp;
    void depth(TreeNode* root,int height){
        if(root==NULL) return;
        mp[root]=height;
        depth(root->left,height+1);
        depth(root->right,height+1);
    }
    TreeNode* solve(TreeNode* root,TreeNode* p,TreeNode* q){
        if(root==NULL) return NULL;
        if(root==p or root==q) return root;
        TreeNode* a=solve(root->left,p,q);
        TreeNode* b=solve(root->right,p,q);
        if(a!=NULL and b!=NULL) return root;
        if(a==NULL) return b;
        if(b==NULL) return a;
        return NULL;
    }
    TreeNode* subtreeWithAllDeepest(TreeNode* root) {
        mp.clear();  
        depth(root,0);
        TreeNode *p=NULL;
        TreeNode * q=NULL;
        int maxi=INT_MIN;
        for(auto it:mp){
            if(maxi<=it.second){
                maxi=it.second;
            }
        }
        vector<TreeNode*> deepest;
        for(auto it:mp){
            if(it.second == maxi){
                deepest.push_back(it.first);
            }
        }
        if(deepest.size() == 1) return deepest[0];
        TreeNode* ans = deepest[0];
        for(int i = 1; i < deepest.size(); i++){
            ans = solve(root, ans, deepest[i]);
        }
        return ans;
    }
};
```

###### method 2 
remove call for lca function previous it is called many times just call it two time only needed.
###### method 3  
modify lca function code so that is give correct answer try to use map but it used 2 pass o(2n) Most optimal is only o(n).
###### method 4 
1 pass solution exist codestorywithmik most optimal code for this question.
in 1 recursion try to find the height and lca in reverse order
```c++

```

