
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    bool isValidBST(TreeNode* root) {
        // Keep track of the previous node in in-order traversal
        TreeNode* previousNode = nullptr;
      
        // Lambda function for in-order traversal validation
        // In a valid BST, in-order traversal yields values in strictly ascending order
        function<bool(TreeNode*)> inOrderValidate = [&](TreeNode* currentNode) -> bool {
            // Base case: empty node is valid
            if (!currentNode) {
                return true;
            }
          
            // Recursively validate left subtree
            if (!inOrderValidate(currentNode->left)) {
                return false;
            }
          
            // Check BST property: current node value must be greater than previous node value
            if (previousNode && previousNode->val >= currentNode->val) {
                return false;
            }
          
            // Update previous node for next comparison
            previousNode = currentNode;
          
            // Recursively validate right subtree
            return inOrderValidate(currentNode->right);
        };
      
        // Start validation from root
        return inOrderValidate(root);
    }
};
