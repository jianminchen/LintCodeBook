##Binary Tree Preorder Traversal

39% Accepted

	Given a binary tree, return the preorder traversal of its nodes' values.

	Have you met this question in a real interview? Yes
	Example
	Given binary tree {1,#,2,3}:

	1
	 \
	  2
	 /
	3
	return [1,2,3].

####Challenge
Can you do it without recursion?

####Tags Expand
- Recursion
- Binary Tree
- Binary Tree Traversal
- Non Recursion


```java
public class Solution {
    /**
     * @param root: The root of binary tree.
     * @return: Inorder in ArrayList which contains node values.
     */
    public ArrayList<Integer> preorderTraversal(TreeNode root) {
        // write your code here
        if(root == null){
            return new ArrayList<Integer>();
        }

        ArrayList<Integer> result = new ArrayList<Integer>();
        Stack<TreeNode> stack = new Stack<TreeNode>();

        TreeNode cur = root;
        while(!stack.isEmpty() || cur != null){
            while(cur != null){
                stack.push(cur);
                result.add(cur.val);
                cur = cur.left;
            }

            cur = stack.peek();
            stack.pop();
            cur = cur.right;
        }

        return result;
    }
}
```