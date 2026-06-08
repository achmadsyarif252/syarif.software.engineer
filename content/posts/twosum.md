+++
date = '2026-06-08T23:41:41+07:00'
draft = false
title = 'Twosum'
tags = ["Leetcode"]
+++

Soal: Diberikan array integer nums dan integer target, kembalikan indices dari dua angka yang jika dijumlahkan hasilnya sama dengan target.

```kotlin
class Solution {
    fun twoSum(nums: IntArray, target: Int): IntArray {
        for(i in nums.indices){
            for(j in i+1 until nums.size){
                if(nums[i]+nums[j] == target){
                    return intArrayOf(i,j)
                }
            }
        }
        throw IllegalArgumentException("No solution found")
    }
}
```
