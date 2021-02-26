---
title: 자바스크립트를 예제로 하는 자료구조와 알고리즘 3 - 링크드 리스트(Linked List)
description: 자료 구조의 Linked List에 대해서 설명했습니다.
img: javascript
alt: javascript icon
author: socratone
category: algorithm
---

# 자바스크립트를 예제로 하는 자료구조와 알고리즘 3 - 링크드 리스트(Linked List)

링크드 리스트는 노드 한 쪽에 값을 넣고 다른 한 쪽에는 다음 데이터의 위치를 참조할 수 있는 주소 값을 넣어  
꼬리를 물고 이어지는 자료구조다.

<img src="https://blog.kakaocdn.net/dn/V91we/btqYwhidgqi/3Y898Tbsn3qjNbbgOHLBO1/img.png" alt="linked list" style="max-width: 500px;">

head에는 시작하는 노드의 주소를, tail에는 끝나는 노드의 주소를 넣어  
링크드 리스트에 값을 추가 하거나 삭제할 수 있게 해준다.

## Lookup

링크드 리스트의 특정 값을 찾기 위해서는 head부터 시작해서 원하는 값이 나올 때까지 지속해야 한다.  
때문에 최악의 경우 O(n)의 시간 복잡도가 나올 수 있다.

## Insert

링크드 리스트에 노드를 추가하기 위해서는 최악의 경우 tail이 참조하는 노드 바로 전의 노드까지 head를 타고 들어와야 하므로 O(n)의 시간 복잡도가 나온다.

제일 앞에 추가하는 경우 새로운 노드를 head가 가리키던 노드를 가리키게 하고  
head가 새로운 노드를 가리키게 한다.  
O(1)의 시간 복잡도가 걸린다.

제일 뒤에 추가하는 경우 마지막 노드가 새로운 노드를 가리키게 하고  
tail 역시도 새로운 노드를 가리키게 한다.  
O(1)의 시간 복잡도가 걸린다.

## Delete

마찬가지로 중간에 있는 노드를 삭제하려면 head를 타고 노드수만큼 찾아봐야 하니  
O(n)의 시간 복잡도가 걸린다.

제일 앞의 노드를 삭제하려면 제일 앞의 노드가 가리킨던 두 번째 노드의 주소 값을 지우고  
head가 두 번째 노드를 가리키게 한다.  
더 이상 참조할 수 없는 첫 번째 노드는 가비지 컬렉터에 의해 메모리에서 삭제 된다.

제일 뒤의 노드를 삭제하려면 뒤에서 두 번째 노드를 찾아야 하므로  
head부터 시작해서 어느 노드가 마지막 노드를 가리키는지 알아야 하므로 O(n)의 시간 복잡도가 걸린다.  
두 번째 노드를 발견했다면 두 번째 노드에서 마지막 노드의 참조값을 삭제한다.  
tail은 새롭게 마련된 마지막 노드를 가리킨다.  
링크가 해제된 이전의 마지막 노드는 마찬가지로 가비지 컬렉터에 의해 메모리에서 삭제 된다.

## 자바스크립트 코드

리스트의 제일 앞에 노드를 추가하는 메소드와 제일 뒤에 노드를 추가하는 메소드를 대강 구현하면 아래와 같다.

```js
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

class LinkedList {
  constructor() {
    this.head = null;
    this.tail = null;
  }

  addLast(value) {
    const newNode = new Node(value);
    
    // list가 비어있을 때
    if (this.head === null && this.tail === null) {
      this.head = newNode;
      this.tail = newNode;
      return;
    }

    const lastNode = this.tail;
    lastNode.next = newNode;
    this.tail = newNode;
  }

  addFirst(value) {
    const newNode = new Node(value);

    // list가 비어있을 때
    if (this.head === null && this.tail === null) {
      this.head = newNode;
      this.tail = newNode;
      return;
    }

    newNode.next = this.head;
    this.head = newNode;
  }
}

const linkedList = new LinkedList();
linkedList.addFirst('가');
linkedList.addLast('나');
linkedList.addFirst('다');

console.log(JSON.stringify(linkedList, null, 2));
/*
{
  "head": {
    "value": "다",
    "next": {
      "value": "가",
      "next": {
        "value": "나",
        "next": null
      }
    }
  },
  "tail": {
    "value": "나",
    "next": null
  }
}
*/
```