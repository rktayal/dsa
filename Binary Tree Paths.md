### Problem Statement
Given the root of a binary tree, return all root-to-leaf paths in any order.

A leaf is a node with no children.

Example 1:

Input: root = [1,2,3,null,5]
Output: ["1->2->5","1->3"]

```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def __init__(self):
        self.result = []
        
    def dfs(self, root, path):
        if root is not None:
            if root.left is None and root.right is None:
                # leaf node reached
                path += str(root.val)
                self.result.append(path)
                
            path += str(root.val) + '->'
            self.dfs(root.left, path)
            self.dfs(root.right, path)
            
            
    def binaryTreePaths(self, root: Optional[TreeNode]) -> List[str]:
        self.dfs(root, "")
        #print(self.result)
        return self.result
```
