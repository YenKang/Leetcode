## Week6 Review

- date:2020-11-01(sat)
- author:Bryan Yen

##### 本週日期：2020-10-26～11-01

### 1.本週任務完成度：100%

- [x] 125. Valid Palindrome
- [x] 34. Find First and Last Position of Element in Sorted Array
- [x] 33. Search in Rotated Sorted Array I
- [x] 81. Search in Rotated Sorted Array II
- [x] 153. Find Minimum in Rotated Sorted Array
- [x] 154. Find Minimum in Rotated Sorted Array II

### 2.下週任務
- [ ] [4. Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/)

- [ ] [29. Divide Two Integers](https://leetcode.com/problems/divide-two-integers/)

- [ ] [74. Search a 2D Matrix](https://leetcode.com/problems/search-a-2d-matrix/)

- [ ] [162. Find Peak Element](https://leetcode.com/problems/find-peak-element/)

- [ ] [174. Dungeon Game](https://leetcode.com/problems/dungeon-game/)

- [ ] [327. Count of Range Sum](https://leetcode.com/problems/count-of-range-sum/)


### 3.複盤總結：
[125. Valid Palindrome](https://github.com/YenKang/Leetcode/blob/master/%5B038%5D125.%20Valid%20Palindrome.md)：

本題間在於Charater語法的使用

> - Character.isLetterOrDigit(Char c)
> - Character.lowerCase(Char c)

[34. Find First and Last Position of Element in Sorted Array I](https://github.com/YenKang/Leetcode/blob/master/%5B039%5D34.%20Find%20First%20and%20Last%20Position%20of%20Element%20in%20Sorted%20Array.md)

兩個關鍵點，第一是return new int[]{-1,-1} 回傳陣列的語法，第二是如果是FindFirst，那麼大於等於的那邊，就是要往左邊


```java
if(target <= nums[mid]){
    end = mid;
}
```


[33. Search in Rotated Sorted Array](https://github.com/YenKang/Leetcode/blob/master/%5B040%5D33.%C2%A0Search%20in%20Rotated%20Sorted%20Array.md)

邏輯在於，有兩層，第一層if是判斷nums[mid]跟nums[start]大小比較，第二層是target是否回遞增函數

```java
 if(nums[start]<nums[mid]){
 // chech ascending order in left part
     if(nums[start]<=target && target<=nums[mid]){
         end =mid;
     }
     else{
         start = mid; 
     }
 }
```

[153. Find Minimum in Rotated Sorted Array](https://github.com/YenKang/Leetcode/blob/master/%5B042%5D153.%20Find%20Minimum%20in%20Rotated%20Sorted%20Array.md)

關鍵在於最後return nums[mid]

```java
if(nums[mid]<nums[right]){
    right = mid;
}
else if(nums[mid]>nums[right]){
    left = mid+1;
}
else if(nums[mid] == nums[right]){
    return nums[mid];
}
```

[154. Find Minimum in Rotated Sorted Array II](https://github.com/YenKang/Leetcode/blob/master/%5B043%5D154.%20Find%20Minimum%20in%20Rotated%20Sorted%20Array%20II.md
)

```java
if(nums[mid]<nums[right]){
    right = mid;
}
else if(nums[mid]>nums[right]){
    left = mid+1;
}
else{
    right--;
}
```


