# Longest_Balanced_Subarray
#Shubham
Longest Balanced Subarray

This project provides a C++ implementation to find the length of the longest balanced subarray, where the number of distinct even elements equals the number of distinct odd elements.

🚀 About the Program

A subarray is considered balanced if:

The count of unique even numbers = the count of unique odd numbers

This program checks all possible subarrays using a brute-force approach and returns the maximum length of such a balanced subarray.

📌 Features

Counts distinct even and distinct odd numbers in each subarray

Uses unordered_set for efficient uniqueness checking

Brute-force algorithm with nested loops

Clean and easy-to-understand implementation

🧠 How It Works

Iterate through all possible start indices i

For each start index, expand subarray using index j

Maintain two sets:

Even → stores unique even numbers

Odd → stores unique odd numbers

Whenever Even.size() == Odd.size(), update the longest length

Print the maximum balanced subarray length

📝 Sample Input
5
1 2 3 4 5

🎯 Sample Output
4

🧩 Time Complexity

Time: O(n²) — due to checking all subarrays

Space: O(n) — sets for storing distinct values

🛠 Technologies Used

C++

STL (vector, unordered_set)

📄 Code Snippet
class Solution {
public:
    int longestBalanced(vector<int>& nums) {
        int ans = 0;
        int n = nums.size();
        for (int i = 0; i < n; i++) {
            unordered_set<int> Even;
            unordered_set<int> Odd;
            for (int j = i; j < n; j++) {
                if (nums[j] % 2 == 0)
                    Even.insert(nums[j]);
                else
                    Odd.insert(nums[j]);
                if (Even.size() == Odd.size())
                    ans = max(ans, j - i + 1);
            }
        }
        return ans;
    }
};
