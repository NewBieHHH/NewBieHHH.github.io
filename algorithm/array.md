### 数组原地去重
**题目详情:**给定一个排序数组，你需要在原地删除重复出现的元素，使得每个元素只出现一次，返回移除后数组的新长度。

**思路:**遍历数组,判断前后元素是否相等,然后利用splice删除数组重复的那个数<br>
利用javascript实现:
```
    /**
    * @param {number[]} nums
    * @return {number}
    */
    var removeDuplicates = function(nums) {
        var len = nums.length
        if(len < 2) return len
        for (var i = 1; i < len; i++) {
            if(nums[i-1] === nums[i]){
                nums.splice(i,1)
                len--
                i--
            }
        }
        return len
    };
```

**拓展:**如果给定的数组没有排序呢,怎样原地去重?


### 数组原地旋转
**题目详情:**给定数组，将数组中的元素向右移动 k 个位置，其中 k 是非负数。

**思路:**利用pop、shift、splice原地修改数组<br>
**关键点优化:**移动后的同一个结果对应多个k值，故取最小值，保证移动次数最少<br>
利用javascript实现:
```
    /**
    * @param {number[]} nums
    * @param {number} k
    * @return {void} Do not return anything, modify nums in-place instead.
    */
    var rotate = function(nums, k) {
        var realK = k%nums.length
        var tempnums = nums.splice(0, nums.length-realK)
        nums.push(...tempnums)
    };
```
