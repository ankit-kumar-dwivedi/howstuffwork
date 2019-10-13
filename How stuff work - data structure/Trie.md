## What is Trie ?

![Trie from wikipedia](https://upload.wikimedia.org/wikipedia/commons/thumb/b/be/Trie_example.svg/640px-Trie_example.svg.png)
   
 Figure - A trie for keys "A", "to", "tea", "ted", "ten", "i", "in", and "inn". Note that this example does not have all the children alphabetically sorted from left to right as it should be (the root and node 't').

The trie is a tree of nodes which supports Find and Insert operations. 
Find returns the value for a key string, and Insert inserts a string (the key) and a value into the trie. Both Insert and Find run in O(n) time, where n is the length of the key. 
The main idea of the trie data structure consists of the following parts:

   - The trie is a tree where each vertex represents a single word or a prefix.

   - The root represents an empty string (“”), the vertexes that are direct sons of the root represent prefixes of length 1, the vertexes that are 2 edges of distance from the root represent prefixes of length 2, the vertexes that are 3 edges of distance from the root represent prefixes of length 3 and so on. In other words, a vertex that are k edges of distance of the root have an associated prefix of length k.

   - Let v and w be two vertexes of the trie, and assume that v is a direct father of w, then v must have an associated prefix of w.
   
## Why tries?

The tries can insert and find strings in o(L) time(where L represent the length of a single word) which is much faster than hash tables and binary search trees.

A binary search tree which stores each word as a node requires O(log(n)) time to search for a string where n represents the number of nodes in BST.
Contrary to Binary trees, Trie holds a single character and has a maximum fan-out equal to the length of the alphabet which says that the operations (insert, search, remove) would take time O(dn) where
d = alphabet size (26 in case of english alphabet)
n = size of the string involved in the operation

and the space complexity can be stated as O(W) where
W = total size of the string S

## When useful? 

**Auto Complete**

Auto Complete functionality is used widely in mobile apps and text editors. Trie is an efficient data structure widely used for its implementation. Trie provides an easy way to search for the possible dictionary words to complete word because of the following reasons
- Looking up data in a trie is faster in the worst case O(n)(n = size of the string involved in the operation) time compared to an imperfect hash table. An imperfect hash table can have key collisions. A key collision is the hash function mapping of different keys to the same position in a hash table.
- A trie can provide an alphabetical ordering of the entries by key.
- Searching in a trie enables us to trace pointers to get to a node that represent the string user has entered. By exploring a trie traversing down the tree, we can easily enumerate all strings that complete the user input.

**Spell Checkers**

Spell checking is a three-step process. Check if a word is in a dictionary, generate potential suggestions, and then sort the suggestions–hopefully with the intended word on top.
Tries can be used to store that dictionary and by searching the words over the data structure one can easily implement a spell checker in the most efficient way. 

Using trie not only the lookup for a word into the dictionary becomes easy but an algorithm to provide the list of valid words or suggestions can be easily constructed.

**Longest Prefix Matching**


Also called Maximum prefix length match refers to an algorithm used by routers in Internet protocol(IP) networking to select an entry from a routing table.
One of the first IP lookup techniques to employ tries is the radix trie implementation in the BSD kernel. 
Optimizations requiring contiguous masks bound the worst case lookup time to O(W) where W is the length of the address
in bits. In order to speed up the lookup process,multi bit trie schemes were developed which perform a search using multiple bits of the address at a time.

**Automatic Command completion**

when using an operating system such as Unix, we type in system commands to accomplish certain tasks. For example to see the list of commands (ls /usr/bin/ps*) having prefix ps can be autosuggested by just pressing tab

```
/usr/bin/psed        /usr/bin/pstopdf     /usr/bin/pstruct5.16
/usr/bin/psed5.12    /usr/bin/pstruct
/usr/bin/psed5.16    /usr/bin/pstruct5.12
```
We can simplify the task of typing in commands by providing a command completion facility which automatically types in the command suffix once the user has typed in a long enough prefix to uniquely identify the command. For instance, once the letters psi have been entered, we know that the command must be psidtopgm because there is only one command that has the prefix psi.

## Implementation

```
// C++ implementation of search and insert 
// operations on Trie 
#include <bits/stdc++.h> 
using namespace std; 

const int ALPHABET_SIZE = 26; 

// trie node 
struct TrieNode 
{ 
	struct TrieNode *children[ALPHABET_SIZE]; 

	// isEndOfWord is true if the node represents 
	// end of a word 
	bool isEndOfWord; 
}; 

// Returns new trie node (initialized to NULLs) 
struct TrieNode *getNode(void) 
{ 
	struct TrieNode *pNode = new TrieNode; 

	pNode->isEndOfWord = false; 

	for (int i = 0; i < ALPHABET_SIZE; i++) 
		pNode->children[i] = NULL; 

	return pNode; 
} 

// If not present, inserts key into trie 
// If the key is prefix of trie node, just 
// marks leaf node 
void insert(struct TrieNode *root, string key) 
{ 
	struct TrieNode *pCrawl = root; 

	for (int i = 0; i < key.length(); i++) 
	{ 
		int index = key[i] - 'a'; 
		if (!pCrawl->children[index]) 
			pCrawl->children[index] = getNode(); 

		pCrawl = pCrawl->children[index]; 
	} 

	// mark last node as leaf 
	pCrawl->isEndOfWord = true; 
} 

// Returns true if key presents in trie, else 
// false 
bool search(struct TrieNode *root, string key) 
{ 
	struct TrieNode *pCrawl = root; 

	for (int i = 0; i < key.length(); i++) 
	{ 
		int index = key[i] - 'a'; 
		if (!pCrawl->children[index]) 
			return false; 

		pCrawl = pCrawl->children[index]; 
	} 

	return (pCrawl != NULL && pCrawl->isEndOfWord); 
} 

// Driver 
int main() 
{ 
	// Input keys (use only 'a' through 'z' 
	// and lower case) 
	string keys[] = {"the", "a", "there", 
					"answer", "any", "by", 
					"bye", "their" }; 
	int n = sizeof(keys)/sizeof(keys[0]); 

	struct TrieNode *root = getNode(); 

	// Construct trie 
	for (int i = 0; i < n; i++) 
		insert(root, keys[i]); 

	// Search for different keys 
	search(root, "the")? cout << "Yes\n" : 
						cout << "No\n"; 
	search(root, "these")? cout << "Yes\n" : 
						cout << "No\n"; 
	return 0; 
} 

```
Code - geeksforgeeks

## Further Reading

https://medium.com/basecs/trying-to-understand-tries-3ec6bede0014
https://www.topcoder.com/community/data-science/data-science-tutorials/using-tries/
