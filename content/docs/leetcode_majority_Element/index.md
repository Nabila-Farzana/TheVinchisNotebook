---
title: "How I solved leetcode problem: Majority Element"

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
description: "How to solve Mejority Element in a optimized way!"
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
Given an array nums of size n, return the majority element.
The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.
#### Example:
__Input__: nums = [2,7,11,15], target = 9  
__Output__: [0,1]  
__Explanation__: Because nums[0] + nums[1] == 9, we return [0, 1].

### How I break down this problem:






### Time and space complexity:
Now Let's calculate how efficient our code is!
We are looping through an array of n elements and inside the loop we are assigining some value. So in worst case scenerio, our time complexity will be __O(n)__

Now come to the space complexity. We are allocating memories for an array of n elements. So our memory complexity will ne __O(n)__ as well.