# DSAAssign5


# Q1

```
function construct2DArray(original, m, n) {
    const length = original.length;
    
    if (length !== m * n) {
        return [];
    }
    
    const result = [];
    
    for (let i = 0; i < length; i += n) {
        result.push(original.slice(i, i + n));
    }
    
    return result;
}


```

# Q2

```
function arrangeCoins(n) {
    let left = 0;
    let right = n;
    
    while (left <= right) {
        const mid = Math.floor((left + right) / 2);
        const totalCoins = (mid * (mid + 1)) / 2;
        
        if (totalCoins === n) {
            return mid;
        } else if (totalCoins < n) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    
    return right;
}

```

# Q3

```
function sortedSquares(nums) {
    return nums.map(num => num * num).sort((a, b) => a - b);
}

```

# Q4

```
function findDisappearedNumbers(nums1, nums2) {
    const set1 = new Set(nums1);
    const set2 = new Set(nums2);
    const result = [];
    
    for (let num of nums1) {
        if (!set2.has(num)) {
            result.push(num);
        }
    }
    
    for (let num of nums2) {
        if (!set1.has(num)) {
            result.push(num);
        }
    }
    
    return [result, result.reverse()];
}

```


# Q5

```
function findTheDistanceValue(arr1, arr2, d) {
    let count = 0;
    
    for (let num1 of arr1) {
        let isValid = true;
        
        for (let num2 of arr2) {
            if (Math.abs(num1 - num2) <= d) {
                isValid = false;
                break;
            }
        }
        
        if (isValid) {
            count++;
        }
    }
    
    return count;
}

```

# Q6

```
function findDuplicates(nums) {
    const set = new Set();
    const result = [];
    
    for (let num of nums) {
        if (set.has(num)) {
            result.push(num);
        } else {
            set.add(num);
        }
    }
    
    return result;
}

```

# Q7

```

function findMin(nums) {
    let left = 0;
    let right = nums.length - 1;
    
    while (left < right) {
        const mid = Math.floor((left + right) / 2);
        
        if (nums[mid] > nums[right]) {
            left = mid + 1;
        } else {
            right = mid;
        }
    }
    
    return nums[left];
}

```

# Q8

```
function findOriginalArray(changed) {
    if (changed.length % 2 !== 0) {
        return [];
    }
    
    changed.sort((a, b) => a - b);
    const original = [];
    const seen = new Set();
    
    for (let num of changed) {
        if (seen.has(num)) {
            seen.delete(num);
        } else {
            original.push(num);
            seen.add(2 * num);
        }
    }
    
    return original;
}

```




