## Tree

A tree is non-linear and a hierarchical data structure consisting of a collection of nodes such that each node of the tree stores a value and a list of references to other nodes (the “children”).

## Terminologies

### Parent Node
The node which is a predecessor of a node.

### Child Node
The node which is the immediate successor of a node.

### Root Node
The topmost node of a tree or the node which does not have any parent node.
A non-empty tree must contain exactly one root node.

__Traversal__
Inorder => Left, Root, Right.
Preorder => Root, Left, Right.
Post order => Left, Right, Root.

Inorder traversal
First, visit all the nodes in the left subtree
Then the root node
Visit all the nodes in the right subtree
```
inorder(root->left)
display(root->data)
inorder(root->right)
```

```java
public void inorderTraversal(TreeNode root, List<Integer> res) {
        if (root != null) {
            inorderTraversal(root.left, res);
            res.add(root.val);
            inorderTraversal(root.right, res);
        }
}
```

```java
class Solution {
    public List<Integer> postorderTraversal(TreeNode root) {
        List<Integer> list = new ArrayList<>();
        if(root == null) return list;
        Stack<TreeNode> stack = new Stack<>();
        stack.push(root);
        while(!stack.isEmpty()){
            TreeNode cur = stack.pop();
            list.add(0, cur.val);
            if(cur.left != null)
                stack.push(cur.left);
            if(cur.right != null)
                stack.push(cur.right);
        }
        return list;
    }
}
```

Ancestor problem :-
1. https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/
2. https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/
3. https://leetcode.com/problems/maximum-difference-between-node-and-ancestor/
4. https://leetcode.com/problems/lowest-common-ancestor-of-deepest-leaves/
5. https://leetcode.com/problems/kth-ancestor-of-a-tree-node/
6. https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/

Root to leaf path problems:-
1. https://leetcode.com/problems/binary-tree-paths/ EASY
2. https://leetcode.com/problems/path-sum-iii/submissions/
3. https://leetcode.com/problems/smallest-string-starting-from-leaf/
4. https://leetcode.com/problems/sum-of-root-to-leaf-binary-numbers/
5. https://leetcode.com/problems/insufficient-nodes-in-root-to-leaf-paths/
6. https://leetcode.com/problems/pseudo-palindromic-paths-in-a-binary-tree/

Serialize and deserialize:-
1. https://leetcode.com/problems/serialize-and-deserialize-binary-tree/ Hard
2. https://leetcode.com/problems/verify-preorder-serialization-of-a-binary-tree/ Medium
3. https://leetcode.com/problems/serialize-and-deserialize-bst/
4. https://leetcode.com/problems/serialize-and-deserialize-bst/

Leaves related problem:-
1. https://leetcode.com/problems/sum-of-left-leaves/ EASY
2. https://leetcode.com/problems/leaf-similar-trees/ EASY
3. https://leetcode.com/problems/deepest-leaves-sum/
4. https://leetcode.com/problems/delete-leaves-with-a-given-value/

Level order traversal:-
1. https://leetcode.com/problems/smallest-subtree-with-all-the-deepest-nodes/
2. https://leetcode.com/problems/path-in-zigzag-labelled-binary-tree/
3. https://leetcode.com/problems/maximum-level-sum-of-a-binary-tree/
4. https://leetcode.com/problems/sum-of-nodes-with-even-valued-grandparent/
5. https://leetcode.com/problems/frog-position-after-t-seconds/
6. https://leetcode.com/problems/even-odd-tree/
7. https://leetcode.com/problems/binary-tree-level-order-traversal/
8. https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/
9. https://leetcode.com/problems/binary-tree-level-order-traversal-ii/
10. https://leetcode.com/problems/binary-tree-right-side-view/
11. https://leetcode.com/problems/n-ary-tree-level-order-traversal/
12. https://leetcode.com/problems/find-largest-value-in-each-tree-row/
13. https://leetcode.com/problems/add-one-row-to-tree/
14. https://leetcode.com/problems/average-of-levels-in-binary-tree/
15. https://leetcode.com/problems/maximum-width-of-binary-tree/

Node deletion:-
1. https://leetcode.com/problems/delete-nodes-and-return-forest/
2. https://leetcode.com/problems/delete-node-in-a-bst/

Tree construction:-
1. https://leetcode.com/problems/construct-binary-tree-from-preorder-and-postorder-traversal/
2. https://leetcode.com/problems/all-possible-full-binary-trees/
3. https://leetcode.com/problems/construct-binary-search-tree-from-preorder-traversal/
4. https://leetcode.com/problems/recover-a-tree-from-preorder-traversal/
5. https://leetcode.com/problems/validate-binary-tree-nodes/
6. https://leetcode.com/problems/number-of-ways-to-reconstruct-a-tree/
7. https://leetcode.com/problems/merge-bsts-to-create-single-bst/
8. https://leetcode.com/problems/unique-binary-search-trees-ii/
9. https://leetcode.com/problems/convert-sorted-list-to-binary-search-tree/
10. https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/

Distance between two Nodes:-
1. https://leetcode.com/problems/minimum-distance-between-bst-nodes/
2. https://leetcode.com/problems/sum-of-distances-in-tree/ Hard
3. https://leetcode.com/problems/all-nodes-distance-k-in-binary-tree/

**Inorder traversal**
1. https://leetcode.com/problems/increasing-order-search-tree/
2. https://leetcode.com/problems/binary-search-tree-to-greater-sum-tree/
3. https://leetcode.com/problems/all-elements-in-two-binary-search-trees/
4. https://leetcode.com/problems/validate-binary-search-tree/
5. https://leetcode.com/problems/convert-bst-to-greater-tree/
Rangesum of BT
1.https://leetcode.com/problems/range-sum-of-bst/

Flipping:-
1. https://leetcode.com/problems/flip-equivalent-binary-trees/
2. https://leetcode.com/problems/flip-binary-tree-to-match-preorder-traversal/

Check binary tree:-
1. https://leetcode.com/problems/check-completeness-of-a-binary-tree/
2. https://leetcode.com/problems/check-completeness-of-a-binary-tree/
3. https://leetcode.com/problems/univalued-binary-tree/

Tree relations:-
1. https://leetcode.com/problems/cousins-in-binary-tree/

Counting of nodes:-
1. https://leetcode.com/problems/count-good-nodes-in-binary-tree/
2. https://leetcode.com/problems/number-of-nodes-in-the-sub-tree-with-the-same-label/
3. https://leetcode.com/problems/number-of-good-leaf-nodes-pairs/
4. https://leetcode.com/problems/unique-binary-search-trees/

Recovery:-
1.https://leetcode.com/problems/recover-binary-search-tree/

Kth smallest :-
1. https://leetcode.com/problems/kth-smallest-element-in-a-bst/
2. https://leetcode.com/problems/kth-largest-element-in-a-stream/

Trimming or pruning:
1. https://leetcode.com/problems/trim-a-binary-search-tree/

Searching:-
1. https://leetcode.com/problems/search-in-a-binary-search-tree/

Difference problem in BT:-
1. https://leetcode.com/problems/kth-largest-element-in-a-stream/

Tree checking:-
1. https://leetcode.com/problems/same-tree/
2. https://leetcode.com/problems/symmetric-tree/

Depth problem:-
1. https://leetcode.com/problems/maximum-depth-of-binary-tree/
2. https://leetcode.com/problems/minimum-depth-of-binary-tree/
3. https://leetcode.com/problems/minimum-absolute-difference-in-bst/
4. https://leetcode.com/problems/maximum-depth-of-n-ary-tree/
