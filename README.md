# LEETCODE-Arrays-3043

**1. TrieNode Class:**
- Defines a class `TrieNode` with a single property `children`.
- `children` is an array of size 10 (assuming digits 0-9) that holds references to other `TrieNode` objects.

**2. Trie Class:**
- Defines a class `Trie` with a private `root` property and two methods: `insert` and `search`.
  - `insert(String word)`: Takes a string (converted to a character array) and inserts it into the trie.
    - Iterates through each character in the string.
    - Calculates the index based on the character (assuming digits 0-9, 'a' - '0' = index).
    - If a child node doesn't exist at that index, create a new `TrieNode`.
    - Update the current node to point to the child node.
  - `search(String word)`: Takes a string (converted to a character array) and searches for it in the trie.
    - Initializes `prefixLength` to 0 and `node` to the root.
    - Iterates through each character in the string.
    - Calculates the index based on the character.
    - If a child node doesn't exist at that index, break the loop (no match).
    - Update the current node to the child node and increment `prefixLength`.
    - Returns the final `prefixLength`.

**3. Solution Class:**
- Defines a class `Solution` with a single method: `longestCommonPrefix(int[] arr1, int[] arr2)`.
  - This method finds the Longest Common Prefix (LCP) between two integer arrays `arr1` and `arr2`.
  - Initializes `ans` to 0 and creates a new `Trie` object.
  - Iterates through each integer in `arr1` and converts it to a string using `Integer.toString(num)`. Then, inserts the string representation of the integer into the trie using `trie.insert`.
  - Iterates through each integer in `arr2` and converts it to a string. Then, uses `trie.search` to find the longest prefix of the string present in the trie. Updates `ans` with the maximum value encountered.
  - Returns the final `ans` which represents the LCP between the two arrays.

**Overall Functionality:**

This code utilizes a trie to efficiently find the Longest Common Prefix between two integer arrays. The trie stores the string representations of the integers in `arr1`. Then, it searches for prefixes of the string representations of integers in `arr2`. The longest prefix found in the trie for any integer in `arr2` represents the LCP between the two arrays. 
