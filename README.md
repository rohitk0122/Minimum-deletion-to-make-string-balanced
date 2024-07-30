# Minimum-deletion-to-make-string-balanced
class Solution {
    public int minimumDeletions(String s) {
       int minDeletions = 0; // Initialize to zero since no deletions needed at the start
        int countB = 0; // To track 'b's encountered so far

        // Iterate through the string
        for (char c : s.toCharArray()) {
            if (c == 'b') {
                countB++;
            } else { // c == 'a'
                // Either delete the current 'a' or delete all 'b's encountered so far
                minDeletions = Math.min(minDeletions + 1, countB);
            }
        }

        return minDeletions; 
    }
}
