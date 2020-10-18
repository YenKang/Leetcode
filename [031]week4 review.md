## [031]week4 review

##### 本週日期：2020-10-12～10-18

#### 1.本週任務完成度：100%

- [x] 2. Add Two Numbers
- [x] 82. Remove Duplicates from Sorted List II
- [x] 21. Merge Two Sorted Lists
- [x] 50. Pow(x, n)
- [x] 326. Power of three
- [x] 3. Longest Substring Without Repeating Characters

#### 2.下週任務
- [ ] [43. Multiply Strings](https://leetcode.com/problems/multiply-strings/)

- [ ] [371. Sum of Two Integers](https://leetcode.com/problems/sum-of-two-integers/)

- [ ] [237. Delete Node in a Linked List](https://leetcode.com/problems/delete-node-in-a-linked-list/)

- [ ] [349. Intersection of Two Arrays](https://leetcode.com/problems/intersection-of-two-arrays/)

- [ ] [704. Binary Search](https://leetcode.com/problems/binary-search/)

- [ ] [1237. Find Positive Integer Solution for a Given Equation](https://leetcode.com/problems/find-positive-integer-solution-for-a-given-equation/)

### 3.複盤總結：

#### 1.[Add Two Numbers](https://github.com/YenKang/Leetcode/blob/master/%5B025%5D2.%20Add%20Two%20Numbers.md)：

這題是由兩個ListNode相加，主要是用到ListNode temp的概念，

```java
ListNode tempHead = new ListNode(0);
ListNode l1_curNode = l1;
ListNode l2_curNode = l2;
ListNode curNode = tempHead;
```
然後，做一個while回圈，裡面有對ListNode l1跟l2的判斷，如果相加成功的話，就要做

```java
curNode.next = new ListNode(sum%10); // 把相加後%10 等於下一個node
sum = sum /10; // sum ＝ sum/10 目的是找餘數
curNode = curNode.next;
```
最後要判斷，如果carry==1，就要多加一位數

```java
if(sum==1){
  curNode.next = new ListNode(1);
}
```

#### 2.[[026]82. Remove Duplicates from Sorted List II](https://github.com/YenKang/Leetcode/blob/master/%5B026%5D82.%20Remove%20Duplicates%20from%20Sorted%20List%20II.md)：

> - Input: 1->1->1->2->3
> - Output: 2->3
要刪除重複的ListNode，因為有可能第一個數就重複，所以要在創立first node，還有對當index =i時，就要判斷 

```java
 if(nums[i+1]==nums[i+2]){
     int val = nums[i+1];
     while(nums[i+1]!=null && val==nums[i+1]){
         nums[i+1] = nums[i+2];
     }
}
else{
    i++;
}
```

上述是把ListNode寫法改成array的邏輯

#### 3.[[027]21. Merge Two Sorted Lists](https://github.com/YenKang/Leetcode/blob/master/%5B027%5D21.%20Merge%20Two%20Sorted%20Lists.md):
邏輯跟 [[022]88. Merge Sorted Array](https://github.com/YenKang/Leetcode/blob/master/%5B027%5D21.%20Merge%20Two%20Sorted%20Lists.md) 非常像，只是要替換成ListNode的語法，寫這題時，是我用手寫在白紙上，最後直接compile，沒想到直接能work

最重要的是create dummy Node

```java
ListNode l1cur = l1;
ListNode l2cur = l2;
ListNode dummy = new ListNode(0);
ListNode curMerge = dummy;
        
while(l1cur !=null && l2cur!=null){
    if(l1cur.val <= l2cur.val){
        curMerge.next = l1cur;
        l1cur = l1cur.next;
        curMerge = curMerge.next;
    }
    else{
        curMerge.next = l2cur;
        l2cur = l2cur.next;
        curMerge = curMerge.next;
    }
}
```

### 4.[[028]50. Pow(x, n)](https://github.com/YenKang/Leetcode/blob/master/%5B028%5D50.%20Pow(x%2C%20n).md)
這題最直接邏輯就是用while loop對val做計算，還有對與

> 底數是-1 or +1
>
> 指數超過Integer的邊界

```java
else if(n>0){
    while(n>0){
        val =val*x;
        n--;
    }
    return val;
}
```

### 5.[[029]326. Power of Three](https://github.com/YenKang/Leetcode/blob/master/%5B029%5D326.%20Power%20of%20Three.md)，
判斷是否為次方數，需要用到while loop跟餘數的判定


```java
while(n>1){
     if(n%3 != 0){
         return false;
     }
     n = n/3;
}
```

### 6.[[030]3. Longest Substring Without Repeating Characters](https://github.com/YenKang/Leetcode/blob/master/%5B030%5D3.%20Longest%20Substring%20Without%20Repeating%20Characters.md)

- 原本這題我有兩個解法，解法一遇到大量的資料後就無法處理，後者標準解法可以因應大量的資料，也比較簡潔
- ＨashSet, two pointers, 存在該有元素的話remove，並且i pointer停在原處，繼續做判定，如沒有的話，就set.add，然後找尋最大的set.size，而這個寫法也能抓取最後的set元素


```java
HashSet<Character> set = new HashSet<>();
int max =0;
for(int i=0, j=0;i<s.length();i++){
    if(set.contains(s.charAt(i))){
        set.remove(s.charAt(j++));
        i--;
        //System.out.println("if set:"+ set);
    }
    else{
        set.add(s.charAt(i));
        max = Math.max(max, set.size());
        //System.out.println("else set:"+ set);
    }
    //System.out.println("set:"+ set);
}
```

本週的解題速度更快了，甚至對於 [Hash Tables: Ransom Note](https://www.hackerrank.com/challenges/ctci-ransom-note/problem) 也完整地解出來(之前面試失敗題)


```java
static void checkMagazine(String[] magazine, String[] note) {
     Map<String, Integer> magMap = new HashMap<String, Integer>();
     for(String eachString:magazine){
        if(magMap.containsKey(eachString)==false){
            magMap.put(eachString,1);
        }
        // map裡本來就有該值
        else{
            int val = magMap.get(eachString);
            val = val+1;
            magMap.put(eachString, val);
        }
     }
     int flagVal = note.length;
     //System.out.println("flagVal:"+ flagVal);

     for(String s:note){
         if(magMap.containsKey(s)==false){
             flagVal= flagVal-1;
         }
         else if(magMap.containsKey(s)==true){
             int val = magMap.get(s);
             val = val-1;
             if(val<0){
                 flagVal=flagVal-1;
             }
             magMap.put(s, val);
         }
         //System.out.println("flagVal:"+ flagVal);
     }
     
     if(flagVal == note.length){
         System.out.println("Yes");
     }
     else{
         System.out.println("No");
     }
        
}
```





