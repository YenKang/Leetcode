## [064]Week9 Review

> date:2020-Nov-16~2020-Nov-22

### 1.本週已完成任務
- [058]10. Regular Expression Matching

- [059]17. Letter Combinations of a Phone Number


- [060]23. Merge k Sorted Lists

- [061]32. Longest Valid Parentheses

- [062]39. Combination Sum

- [063]46. Permutations

### 2.下週任務(1116~1122)
- [Mon][401. Binary Watch](https://leetcode.com/problems/binary-watch/), [78. Subsets](https://leetcode.com/problems/subsets/)

- [Tue][44. Wildcard Matching](https://leetcode.com/problems/wildcard-matching/)


- [Wed][263. Ugly Number](https://leetcode.com/problems/ugly-number/), [204. Count Primes](https://leetcode.com/problems/count-primes/), [264. Ugly Number II](https://leetcode.com/problems/ugly-number-ii/)

- [Thu][49. Group Anagrams](https://leetcode.com/problems/group-anagrams/)

- [Fir][121. Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

- [063][70. Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)

### 週總結：

#### [[058]10. Regular Expression Matching](https://github.com/YenKang/Leetcode/blob/master/%5B058%5D10.%20Regular%20Expression%20Matching.md):
這題我覺得要複習到3次以上，才能更熟，現在weekend review後，發現對於以下這個code還是不熟，


```java
// 預處理，case:("aab", "c*aab")
for(int i=0;i<p.length();i++){
    if(p.charAt(i)=='*' && dp[0][i-1]){
        dp[0][i+1] = true;
    }
}
```

另外，有三種case，而且每一種的

> dp[i+1][j+1]=?

的變化，都要在多次複習，這種題型我還是不大熟，需要多次操練

#### [[059]Letter Combinations of a Phone Number](https://github.com/YenKang/Leetcode/blob/master/%5B059%5D17.%20Letter%20Combinations%20of%20a%20Phone%20Number.md):
這題起初我也想不出來，但是看完他人的思路後，比較有概念，現再右用手寫code一次整理思路，
發現，
> letters.substring(i,i+1) 也是我過去沒想到的基本功，真的落地抄一遍，大於敲打鍵盤，騙自己大腦已經會了，其實百紙黑字寫下，可以發現更多盲點。

#### [[060]23. Merge k Sorted Lists](https://github.com/YenKang/Leetcode/blob/master/%5B060%5D23.%20Merge%20k%20Sorted%20Lists.md)：

- 這題我還是不懂，因此用手寫方式再把影片的概念逐步run過一遍，真的發現過去盲點
> - ListNode dummy = new ListNode(-1)
> - ListNode cur = dummy // 其實是把cur指標，對到dummy上

這種鍊錶，其實是一步連著一步，cur.next = node // 是把cur.next這條，連到pop出來的node，然後cur也要移動，透過手寫一遍，對代碼的認知更清晰

#### [[061]32. Longest Valid Parentheses](https://github.com/YenKang/Leetcode/blob/master/%5B061%5D32.%20Longest%20Valid%20Parentheses.md)
- 這題適用approach:stack去做，記住每個index，如果遇到"("正括號，就是push進去stack裡面，如果非正括號，就要進入下一個動作，首先判斷是否為空，空的話就是要改變start index，非空的話就是pop出element，接著又判斷是否回空，
    - 1空：res = Math.max(res, i-start);
    - 2非空：res = Math.max(res, i-stack.peek());
    
[[062]39. Combination Sum](https://github.com/YenKang/Leetcode/blob/master/%5B062%5D39.%20Combination%20Sum.md) 與 [[063]46. Permutations](https://github.com/YenKang/Leetcode/blob/master/%5B063%5D46.%20Permutations.md)都有相似的邏輯解法，就是backtrack，模板如下

```java
helper(a,b,c){
    
    if(){
     // judge
    }

    // for-loop
    for(){
        list.add()
        helper(a,b,c);
        list.remove()
    }

}
```

> 本週最關鍵的一點，就是計時30寫題，如果完全無頭緒，就看視頻，聽解答，週末手寫一遍，但我發現下週開始實施，當天晚上就要抄一遍，雖然不可能懂，但至少先“背”，背多次後，週末再去review會吸收更深。