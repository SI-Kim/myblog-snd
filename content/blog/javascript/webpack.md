---
title: 'webpack'
date: 2021-07-25 20:30:39
category: 'javascript'
draft: false
---

## Definition

여러개 파일을 하나의 파일로 합쳐주는 번들러(bundler)다. 하나의 시작점(entry point)으로부터 의존적인 모듈을 전부 찾아내서 하나의 결과물을 만들어 낸다.
`--mode`, `--entry`, `--output`의 세 가지 옵션을 사용하면 코드를 묶을 수 있다.

- `--mode` : 최적화나 개발힌트 활성화 (development, production, none 선택)
- `--entry` : 컴파일 진입점 선택
- `--output` : 컴파일 결과물의 경로와 파일을 출력

### webpack 설치

`$ npm install -D webpack webpack-cli`

### Example 1:
```
Input: nums = [1,3,5,6], target = 5
Output: 2
```

### Example 2:
```
Input: nums = [1,3,5,6], target = 2
Output: 1
```

### Example 3:
```
Input: nums = [1,3,5,6], target = 7
Output: 4
```

### Example 4:
```
Input: nums = [1,3,5,6], target = 0
Output: 0
```

### Example 5:
```
Input: nums = [1], target = 0
Output: 0
```

### Constraints: 

- `1 <= nums.length <= 104`
- `104 <= nums[i] <= 104`
- `nums` contains distinct values sorted in ascending order.
- `104 <= target <= 104`

## Answer.

### Most Voted:

```js
var searchInsert = function(nums, target) {
    let start = 0;
    let end = nums.length - 1;
    while(start<=end) {
        const mid = Math.floor((start + end)/2);
        if(nums[mid] < target) {
            start = mid + 1;
        } else {
            end = mid -1;
        }
    }
    return start;
};
```
