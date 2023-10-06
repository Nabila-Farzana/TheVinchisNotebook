---
title: "Leetcode problem: First Missing Positive"

date: 2023-10-05T11:30:03+00:00
toc : true
# weight: 1
# aliases: ["/first"]
tags: ["Problem Solving"]
author: "Nabila Farzana"
# author: ["Me", "You"] # multiple authors
# showToc: true
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Let's solve First Missing Positive in an optimized way!"
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true

editPost:
    URL: "https://github.com/Nabila-Farzana/ThevinchisNotebook/blob/main/content/"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---


### problem statement: 
Given an unsorted integer array nums, return the smallest missing positive integer.
You must implement an algorithm that runs in O(n) time and uses O(1) auxiliary space.
#### Example 1:
__Input__: nums = [1,2,0]  
__Output__: 3  
__Explanation__: The numbers in the range [1,2] are all in the array.

#### Example 2:
__Input__: nums = [3,4,-1,1]  
__Output__: 2  
__Explanation__: 1 is in the array but 2 is missing.

### Let's break down the problem:
We need to find out smallest missing positive number from an given array. First of all we need to know that 0 is not a positive integer. Positive integer starts from 1 to infinity.

So at first, we will store our array into an unordered set. Because I don't want to check one element more than once. Let's call the set as __bucket__. And there is no possibility that, the missing positive number will exceed the range __[1, (the given array size + 1)]__.  

Let me explain this with data. Let's assume an array [1, 2, 3, 4]. Here the missing positive number is _5_, which is equal to the size of given array + 1. I hope you got my point.  

If the array is [2, 9, 1000], then the first missing positive number is 1.  

if the array is [-1, -2, 0, 1, 2, 3, 4, 5], then we will only consider the number greater than 0 and our missing positive number will be 6.

Now, we will execute an loop from 1 to (the size of the array + 1) and for each number we will check if the number exists in the __bucket__ or not. If the number does not exist in the bucket, then bingo!! that's our missing positive number!

__Now let's do the coding part__

```cpp
int firstMissingPositive(vector<int> nums){
    unordered_set<int> bucket(nums.begin(), nums.end());
    for(int num = 1; num <= nums.size()+1; num++){
        if(bucket.count(num) == 0){
            return num;
        }
    }
    return 0;
}
```
### The Time and Space Complexity :
The time complexity is __O(n)__ and the space complexity is __O(1)__