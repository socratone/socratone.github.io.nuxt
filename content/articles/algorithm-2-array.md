---
title: 자바스크립트를 예제로 하는 자료구조와 알고리즘 2 - 배열(Array)
description: 자료 구조의 배열에 대해서 설명했습니다.
img: javascript
alt: javascript icon
author: socratone
category: algorithm
---

# 자바스크립트를 예제로 하는 자료구조와 알고리즘 2 - 배열(Array)

자바스크립트의 배열은 객체다.  
다른 언어의 배열과는 좀 다르다.

아래의 array와 object는 유사한 구조를 띈다.  
array[0]과 object[0]가 '가'인 것처럼  
배열이나 객체나 key와 value가 한 쌍을 이루면서 값이 담겨 있다.  
당연히 같지는 않다.  
(object와 같은 객체를 유사 배열이라고 한다.)

```js
const array = ['가', '나', '다'];

const object = {
  '0': '가',
  '1': '나',
  '2': '다'
}
```

## 시간 복잡도

### Access

인덱스(key)로 바로 접근할 수 있기 때문에  
자료를 조회하는 데 드는 시간 복잡도는 O(1)이다.

```js
const array = ['가', '나', '다'];

console.log(array[1]) // '나'
```

### Appending

배열 끝에 값을 추가할 경우 새로운 key를 할당해서 거기에 값을 넣으면 되기 때문에 시간 복잡도는 O(1)이 된다.

```js
const array = ['가', '나', '다'];

// O(1)
array.push('라'); // ['가', '나', '다', '라']

// 아래와 유사하다.
{
  '0': '가',
  '1': '나',
  '2': '다',
  '3': '라' // 새로 추가
}
``` 

### Prepending

배열 앞에 값을 추가할 경우 '0' 키에 새로운 값을 넣어야 하기 때문에  
기존에 있던 값들을 하나씩 뒤로 밀게 되니 시간 복잡도는 O(n)이 된다.

```js
const array = ['가', '나', '다'];

// O(n)
array.unshift('라'); // ['라', '가', '나', '다']

// 아래와 유사하다.
{
  '0': '라', // 새로 추가
  '1': '가', // 값을 하나씩 밑으로 밀었다.
  '2': '나',
  '3': '다' 
}
```

### Insertion

배열의 중간에 값을 추가할 경우 역시 최악의 경우 가장 앞쪽에 넣을 수 있으므로  
시간 복잡도는 O(n)이라고 해야한다.

```js
const array = ['가', '나', '다'];

// O(n)
array.splice(1, 0, '라'); // ['가', '라', '나', '다']
```

### Deletion

삭제하는 경우도 최악의 경우 제일 앞의 값을 삭제할 수 있으므로  
시간 복잡도는 O(n)이다.

```js
const array = ['가', '나', '다', '라'];

// O(n)
array.splice(1, 1); // ['가', '다', '라']
```

참고 : [stackoverflow.com/questions/11514308/big-o-of-javascript-arrays](https://stackoverflow.com/questions/11514308/big-o-of-javascript-arrays)