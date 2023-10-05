---
title: "How I solved leetcode problem: Two Sum"

date: 2023-10-04T11:30:03+00:00
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
description: "How to solve two sum in a optimized way!"
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
Given an array of integers __nums__ and an integer __target__, return indices of the two numbers such that they add up to target.You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.
#### Example:
__Input__: nums = [2,7,11,15], target = 9  
__Output__: [0,1]  
__Explanation__: Because nums[0] + nums[1] == 9, we return [0, 1].

### How I break down this problem:
So, just let aside how I will code , let's think mathematically first. If you know sum of two integers and you know one of the integer, how do you find another? So simple , right? you will just substract the known integer from the sum. So we need the exact same thing to do and find the indices of two integers from a given array.

Now let's come up with the code:

```cpp
vector<int> twosum(vector<int> &nums, int target){
    unordered_map<int, int> seen;  // to keep track the seen elemnt of the given array nums
    for(int i=0; i<nums.size(); i++){
        int diff = target - nums[i];
        if(seen.count(diff) == 1){ // if difference of target and current elemnt found in the map seen
            return {seen[diff], i}
        }
        else{
            seen[nums[i]] = i
        }
    }
    return {-1, -1}
}
```

Let me explain it with data. If I condsider the above array from the example:  
the target is 9 . So we need to find out which two numbers make 9 after summation. Let's start with the first element of the array, which is 2. 
 
If we want to make 9 with 2 , we need 7(9 - 2). So our task is to find 7 from the given array.  

Till now I know nothing about the rest of the array. To keep track of the seen element from the given array, I will take an unordered map called __seen__ where key will be the element of the array and value will be the index, as we need to return indices.

so let alone 2 can't make 9. So, for now we just put it in the __seen__. Now move to the next element which is 7 . Now we need 9-7 = 2 to make the target 9. let's find out if 2 exists in __seen__ or not. Oh, yes! we found it! That means it exists in the array too! So now the task is simple , we just need to return the index of 7 which is the current element and the index of 2 from the unordered map __seen__.

See! How easily you solved this! 

### Time and space complexity:
Now Let's calculate how efficient our code is!
We are looping through an array of n elements and inside the loop we are assigining some value. So in worst case scenerio, our time complexity will be __O(n)__

Now come to the space complexity. We are allocating memories for an array of n elements. So our memory complexity will ne __O(n)__ as well.