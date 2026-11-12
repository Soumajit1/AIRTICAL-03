/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;class SolutWhat is your Game Idea Concept ?
*ss Solution {
public:class Solution {
public:class Solution {
public:
    vector<vector<int>> merge(vector<vector<int>>& intervals) {What is your Game Idea Concept ?
*
                ed = intervals[i][1];
            } else {
                ed = max(ed, intervals[i][1]);
            }
        }
        ans.push_back({st, ed});
        return ans;
    }
};
        for (int i = 1; i < intervals.size(); ++i) {
            if (ed < intervals[i][0]) {
                ans.push_back({st, ed});
                st = intervals[i][0];
                ed = intervals[i][1];
            } else {
                ed = max(ed, intervals[i][1]);
            }
        }
        ans.push_back({st, ed});
        return ans;
    }
};
        for (int i = 1; i < intervals.size(); ++i) {
            if (ed < intervals[i][0]) {
                ans.push_back({st, ed});
                st = intervals[i][0];
                ed = intervals[i][1];
            } else {
                ed = max(ed, intervals[i][1]);
            }
        }
        ans.push_back({st, ed});
        return ans;
    }
};
                ans.push_back({st, ed});
                st = intervals[i][0];
                ed = intervals[i][1];
            } else {
                ed = max(ed, intervals[i][1]);
            }
        }
        ans.push_back({st, ed});
        return ans;
    }
};
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
