## [010]week1 review

#### 1.本週進度

- 本週完成六題easy級別的題目，分別來總結個別題目的重點，

- [[005]14. Longest Common Prefix](https://github.com/YenKang/Leetcode/blob/master/%5B005%5D14.%20Longest%20Common%20Prefix.md)，這題關鍵在於找出comparisonWord, comparisonLetter，還有currentWord, currentLetter做比較（這題我熟悉度大約，60%，得再拿白紙手寫幾遍）

- [[006]26. Remove Duplicates from Sorted Array](https://github.com/YenKang/Leetcode/blob/master/%5B006%5D26.%20Remove%20Duplicates%20from%20Sorted%20Array.md)，這題我本來想用arrayList解決，第一是初始化時可以不用固定size，第二是arrayList可以用add.()跟arrayList.remove(int index), contains()的方式，關鍵是在於針對“原有的array”去做modify，因此就要思考邏輯跟判斷的filter，具體方式就是用**Two pointers**去解。

- [[007]27. Remove Element](https://github.com/YenKang/Leetcode/blob/master/%5B007%5D27.%20Remove%20Element.md) 本題思路與[Remove Duplicates from Sorted Array](https://github.com/YenKang/Leetcode/blob/master/%5B006%5D26.%20Remove%20Duplicates%20from%20Sorted%20Array.md)有高度相似性，需要針對原有array做修改，並且用**two pointers**去實作(這個部分熟悉度也只有65%，需要在紙上默寫幾次）

- [[007] 28. Implement strStr()](https://github.com/YenKang/Leetcode/blob/master/%5B007%5D28.%20Implement%20strStr().md)，本題原本想用很複雜的方式逐一char去做比對，但後來想到，只要用一行就解決了 int index = string.indexOf( subString )

- [[008]35. Search Insert Position](https://github.com/YenKang/Leetcode/blob/master/%5B008%5D35.%20Search%20Insert%20Position.md)，這題也是一個突然的靈感，解著同時，想到“區域邊界的切割”，排除各種可能性。

- [[009]38. Count and Say](https://github.com/YenKang/Leetcode/blob/master/%5B009%5D38.%20Count%20and%20Say.md)，從完全讀不懂題意，到讀懂題目，然後在第一種參考做法時，還遇到string吃太多記憶體問題，以至於換成StringBuilder來做，需要在默寫一遍(官方說facebook有出過這題）

#### 2.下週進度

- 週一(167. Two Sum II - Input array is sorted、15. 3Sum)、

- 週二(937. Reorder Data in Log Files、415. Add Strings)、

- 週三(53. Maximum Subarray)、

- 週四(443. String Compression)、

- 週五(66. Plus One)、

- 週六(67. Add Binary)

#### 3.總結：
刷題一週後才發現，有些能力就像吃飯，一口一口吃，有些方法就是得反覆琢磨，到變為自己的第一反應，像是indexOf還走string vs StringBuilder的比較，甚至，會遇到一些莫名的錯誤，但是這些錯誤早就有所規範、命名，我們能做的就是更加心平氣和地把題目給搞懂，代碼寫好，糾正錯誤，如此罷了，不需要有太多不必要的情緒。