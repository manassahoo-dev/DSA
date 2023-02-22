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
