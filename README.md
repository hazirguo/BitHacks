# 玩转位操作

## 原文简介

By Sean Eron Anderson (seander@cs.stanford.edu)

Individually, the **code snippets here are in the public domain** (unless otherwise noted) — feel free to use them however you please. The aggregate collection and descriptions are © 1997-2005 Sean Eron Anderson. The code and descriptions are distributed in the hope that they will be useful, but **WITHOUT ANY WARRANTY** and without even the implied warranty of merchantability or fitness for a particular purpose. As of May 5, 2005, all the code has been tested thoroughly. Thousands of people have read it. Moreover, [Professor Randal Bryant](), the Dean of Computer Science at Carnegie Mellon University, has personally tested almost everything with his [Uclid code verification system](). What he hasn't tested, I have checked against all possible inputs on a 32-bit machine. **To the first person to inform me of a legitimate bug in the code, I'll pay a bounty of US$10 (by check or Paypal).** If directed to a charity, I'll pay US$20.

## 译文序
[***Bit Twiddling Hacks***](http://graphics.stanford.edu/~seander/bithacks.html) 一文作者是 Stanford 大学的 Sean Eron Anderson，我是偶然的机会看到这篇文章，甚是喜欢，决定好好学习该文章的内容。代码托管在 Github 上的 [BitHacks]() 库中。

## 原文目录

* [About the operation counting methodology]()
* [Computing the sign of an integer]()
* [Detect if two integers have opposite signs]()
* [Compute the integers absolute value(abs) without branching]()
* [Compute the minimum(min) or maximum(max) of two integers without branching]()
* [Determining if an integer is a power of 2]()
* Sing extending
	* [Sign extending from a constant bit-width]()
	* [Sign extending from a variable bit-width]()
	* [Sign extending from a variable bit-width in 3 operations]()
* Conditionally set or clear bits without branching
* Conditionally negate a value without branching
* [Merge bits from two value according to a mask]()
* Counting bits set
	* [Counting bits set, naive way]()
	* [Counting bits set by lookup table]()
	* [Counting bits set, Brain Kernighan's way]()
	* [Counting bits set in 14, 24, or 32-bit words using 64-bit instructions]()
	* [Counting bits set, in parallel]()
	* [Count bits set(rank) from the most-significant bit upto a given position]()
	* [Select the bit position(from the most-significant bit) with the given count(rank)]()
* Computing parity (1 if an odd number of bits set, 0 otherwise)
	* [Compute parity of a word the naive way]()
	* [Compute parity by lookup table]()
	* [Compute parity of a byte using 64-bit multiply and modulus division]()
	* [Compute parity of word with a multiply]()
	* [Compute parity in parallel]()
* Swapping Values
	* [Swapping values with subtraction and addition]()
	* [Swapping values with XOR]()
	* [Swapping individual bits with XOR]()
* Reversing bit sequences
	* [Reverse bits the obvious way]()
	* [Reverse bits in word by lookup table]()
	* [Reverse the bits in a byte with 3 operations (64-bit multiply and modulus division)]()
	* [Reverse the bits in a byte with 4 operations (64-bit multiply, no division)]()
	* [Reverse the bits in a byte with 7 operations (no 64-bit, only 32)]()
	* [Reverse an N-bit quantity in parallel with 5 * lg(N) operations]()
* Modulus division (aka computing remainders)]()
	* [Computing modulus division by 1 << s without a division operation (obvious)]()
	* [Computing modulus division by (1 << s) - 1 without a division operation]()
	* [Computing modulus division by (1 << s) - 1 in parallel without a division operation]()
* Finding integer log base 2 of an integer (aka the position of the highest bit set)
	* [Find the log base 2 of an integer with the MSB N set in O(N) operations (the obvious way)]()
	* [Find the integer log base 2 of an integer with an 64-bit IEEE float]()]()
	* [Find the log base 2 of an integer with a lookup table]()
	* [Find the log base 2 of an N-bit integer in O(lg(N)) operations]()
	* [Find the log base 2 of an N-bit integer in O(lg(N)) operations with multiply and lookup]()
* [Find integer log base 10 of an integer]()
* [Find integer log base 10 of an integer the obvious way]()
* [Find integer log base 2 of a 32-bit IEEE float]()
* [Find integer log base 2 of the pow(2, r)-root of a 32-bit IEEE float (for unsigned integer r)]()
* Counting consecutive trailing zero bits (or finding bit indices)
	* [Count the consecutive zero bits (trailing) on the right linearly]()
	* [Count the consecutive zero bits (trailing) on the right in parallel]()
	* [Count the consecutive zero bits (trailing) on the right by binary search]()
	* [Count the consecutive zero bits (trailing) on the right by casting to a float]()
	* [Count the consecutive zero bits (trailing) on the right with modulus division and lookup]()
	* [Count the consecutive zero bits (trailing) on the right with multiply and lookup]()
* [Round up to the next highest power of 2 by float casting]()
* [Round up to the next highest power of 2]()
* Interleaving bits (aka computing Morton Numbers)
	* [Interleave bits the obvious way]()
	* [Interleave bits by table lookup]()
	* [Interleave bits with 64-bit multiply]()
	* [Interleave bits by Binary Magic Numbers]()
* Testing for ranges of bytes in a word (and counting occurances found)
	* [Determine if a word has a zero byte]()
	* [Determine if a word has a byte equal to n]()
	* [Determine if a word has byte less than n]()
	* [Determine if a word has a byte greater than n]()
	* [Determine if a word has a byte between m and n]()
* [Compute the lexicographically next bit permutation]()


## 译文目录

　　　　
