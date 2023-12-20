---
{"dg-publish":true,"permalink":"/pattern-matching-algorithms/"}
---

ie `CTRL F`

These algorithms operate on a long string called the **text** string, and a shorter string called the **pattern** string to find occurrences of the pattern in the text. **Single occurrences** detect if any occurrence occurs at all, while **all occurrences** finds all occurrences, even if they overlap.

All WC TC become brute force (hence WC lol)
# 💪 Brute Force 
1. Line up index 0 of the pattern with index 0 of text 
2. Compare each character with each character of text 
3. If there's a mismatch, shift pattern over by 1 
4. Return depending on: 
	1. First Occurrence: stop iteration; return index of 1st occurring pattern 
	2. All Occurrences: return list of indices of all occurring patterns
## Time Complexity 

| Scenario         | Best Case | Example                       | Worst Case | Example                       |
| ---------------- | --------- | ----------------------------- | ---------- | ----------------------------- |
| No occurances    | O(n)      | pattern (baaa), text (aaaaa)  | O(mn)      | pattern (aaab), text (aaaaa)  |
| Single occurance | O(m)      | pattern (aaa), text (aaaaa)   | O(mn)      | pattern (aaab), text (aaaaab) |
| All occurances   | O(n)      | pattern (baaa), text (aaabaa) | O(mn)      | pattern (aaab), text (aaaaab)                              |
# 🧐 Boyer-Moore (BM)
Use the character that caused mismatch to make a smart shift (Last Occurrence Table). Need to preprocess data to create the table -- $O(n)$. 
```
Algorithm BoyerMooreLastTable(pattern) {
	m <– pattern.length
	last <– HashMap<character,index> // use getOrDefault() for "bad" characters 
	for all i from 0 to m - 1 
		last <– put(pattern[i],i)
	return last
}

MAKE LOT(pattern)
	table = new Map<char, Integer> 
	for i: 0 -> length(pattern) - 1 
		table.put(pattern[i],i)
	return table 

Algorithm BoyderMoore(text, pattern) {
// Note: we're going through the pattern R to L
last <– BoyderMooreLastTable(pattern)
i <– 0
while i<= length of text - length of pattern
	j <– length of pattern - 1 
	while j >= 0 and text[i + j] = pattern[j]
		j <– j - 1
	if j = -1 
		return i // pattern found 
	else 
		shift <– last[text[i+j]]
		if shift < j 
			i <– i + j - shift 
		else 
			i <– i + 1 
return pattern not found 
}
```
## Time Complexity 
- Creating the Table: $O(n)$ 
- Runtime of Table: $O(m)$

| Scenario         | Best Case  | Example                       | Worst Case | Example                       |
| ---------------- | ---------- | ----------------------------- | ---------- | ----------------------------- |
| No occurances    | O(m + n/m) | pattern (bbbb), text (aaaaa)  | O(mn)      | pattern (baaa), text (aaaaa)  |
| Single occurance | O(m)       | pattern (aaa), text (aaaaa)   | O(mn)      | pattern (baaa), text (aaabaa) |
| All occurances   | O(m + n/m) | pattern (aaab), text (aaaaab) | O(mn)      | pattern (baaa), text (aaabaa) |
# 😈 Knuth-Morris-Pratt (KMP)
Exploit repetitions in the pattern to have smart shifts; the "merge sort" of PM -- most consistent. 

**Failure Table**: length of the longest string that's both a prefix of the pattern and a proper suffix of pattern \[0...i]
```
Algorithm makeFail(pattern) {
	i = 0 // last char prefix 
	j = 1 // "last char of suffix" -- current index of FT to fill
	FT = arr[len(pattern)]
	FT[0] = 0; // always! 
	while j < len(pattern)                
		if pattern[i] == pattern[j]    // extend prev pattern; salvage prefix
			FT[j] = i + 1              // suffix pair 
			i++
			j++
		else if (i == 0)          // no prefix suffic matches
			FT[j] = 0 
			j++
		else                     // try a shorter prefix / suffix
			i = FT[-1]?
}

KMP(pattern, text) {
	FT = makeFail(pattern)
	i = 0 // current 
	j = 0 //
	while (i < len(pattern)) {
		if text[i] == pattern[j]
			// making progress case 
			if k == len(pattern - 1) // found pattern! return / add to list	
				i++
				j = FT[j]
			else 
			i++
			j++
		else 
			if j == 0 // failed at beginning, shift 1 
				i++
			else  // made progress, and then failed 
				j = FT[j - 1] 
	}
} 
```
## Time Complexity 
At each step: increment i, decrement j
O(m) for FT + O(n) to iterate through text

| Scenario         | Best Case  | Worst Case |
| ---------------- | ---------- | ---------- |
| No occurances    | O(m + n) | O(m + n)      | 
| Single occurance | O(m), found at start      |  O(m + n)     |
| All occurances   | O(m + n) |  O(m + n)     |

# Rabin-Karp (RK)
Uses (rolling) hash functions to find pattern matches

Actual Hash: text string as base-B (prime) hash
`new hash` = (`old hash` - `oldFirst`\*) + `newLast`\*   
	\* 2 operations = O(1)
$(OldHash - oldFirst(B^{n-1}))B + newLast$
	$h(abcd)$ –> $aB^3 + bB^2 + cB + d$
	hash 2: ($B$($aB^3 + bB^2 + cB + d$) - $aB^3$) + $e$ = $bB^3 + cB^2 + dB + e$

1. hash pattern 
2. initial hash of text  
3. roll hash 
## Time Complexity 

| Scenario         | Best Case  | Worst Case |
| ---------------- | ---------- | ---------- |
| No occurances    | O(m + n) | O(mn)      | 
| Single occurance | O(m)       |  O(mn)     |
| All occurances   | O(m + n) |  O(mn)     |