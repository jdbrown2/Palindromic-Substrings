# Palindromic-Substrings

A word is a palindrome when it is 1 letter, 2 of the same letter, or when (this is where dynamic programming comes in) a palindrome has two of the same letter added to both sides.

If we have a word "aXa" and we know that "X" is a palindrome, then we also know that "aXa" is a palindrome.  
So in order to use dynamic programming, we just need to store whether words  
are palindromic or not in a 2d `boolean` array `dp[][]`.

Initially, we store all the 1 length words, then the 2 length words. Then using the answers stored in the `boolean` array, we can determine if words that have 3 or greater length are palindromes.

First, go through the `length` of the array and set all `dp[i][i] = true` while increasing the  
palindrome count for all the single letters.

Second, go through the `length-1` and check every letter with the next; if they match, increase  
the count and set `dp[i][i+1] = true`.

Now we have a completed array of all 1 and 2 length palindromes.  
We then compare every element with every other element but starting 2 away to get every subset of 3 or more letters. If the 'inside' is a palindrome and if the two outer letters match, increase count and set `dp[i][j] = true` because we might use that for bigger words containing that word in the future.
