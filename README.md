# Longestcommonsubstring
**Inputs:**
The program accepts two strings, say of strings such as ABAB and BABA and compares them.

**Dynamic Programming Table:**
The program is not exhaustively searching through all the substrings (this would be extremely slow), but rather maintaining a table of sequences matching the pattern in the current step (a vector of vectors).
One line of the first row is one position in the first string.
The second string is matched by each column.
The lengths of common substrings that terminate precisely in those positions are stored in the table.

**Filling the Table:**
The program takes each character in the first string (idx) and compares it with each character in second string (idj).
In case the characters are similar, the value of the current cell is 1 + the value of the cell, which is diagonally ahead of the current cell (row, column). This implies that the corresponding substring is increased by a character.
When they do not coincide they are set to 0 because the substring should be consecutive.

**Longest Substring:**
As the table is filled, the program keeps a record of:
The maximum length of a substring that was identified up to now (maxLen).
The last index of this substring in the first string (endIdx).

**Result Extraction and Result:**
The program then takes the first string with endIdx and maxLen and extracts the longest substring in the first string.
It then shows this substring with the length of it.

**Why It Uses Two Rows**
In general, a 2D table of length(s1) x length(s2) would be required, whereas in the current case, the new value can only be calculated as a result of the last row, and thus the program only has to store two rows at once.
This minimizes the memory usage but does not cause the algorithm to run improperly.

**what it prints the output:**
Comparing ABAB and BABA...
Longest common substring: BAB (length: 3)

This allows an effective means of finding the longest common substring of two strings through the construction of solutions to smaller subproblems using a dynamic programming table and printing the optimal solution that has been discovered.
