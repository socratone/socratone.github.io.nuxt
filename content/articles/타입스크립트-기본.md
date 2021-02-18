---
title: 타입스크립트 기본
description: 타입스크립트에서 기본적으로 사용하는 것들을 정리했습니다.
img: js.webp
alt: javascript icon
author: socratone
category: typescript
---

# 타입스크립트 기본

자바스크립트는 변수에 다른 타입의 값을 넣을 수 있다.

```ts
let any = '문자';
any = 1;
```

유연한 언어라고도 할 수 있지만 변수가 저렇게 자꾸 바뀌면 문제가 발생할 수 있다.\
any라는 변수가 숫자로 바뀌었는데 문자인줄 알고 문자에서만 사용할 수 있는 메소드를 사용하면 에러가 발생한다.\
때문에 변수의 타입을 유지하는 게 바람직하고 타입스크립트는 이를 강제해준다.

```ts
let a: any = 1;
let b: string;
let c: number;
let d: [];
let e: {};
```

설정한 변수에 다른 타입의 값을 넣으려고 하면 에러가 발생한다.\
변수는 위와 같이 타입을 명시하고 함수는 아래와 같이 타입을 명시한다.

```ts
function addOne(number: number): number {
  return number + 1;
}
```

함수가 받는 인자에도 타입을 지정할 수 있고(왼쪽의 number) return하는 값에도 타입을 지정할 수 있다. (오른쪽의 number)

## 인터페이스

인자를 객체로 받는 경우에는 interface를 사용할 수 있다.

```ts
interface Human {
  age: number;
  name: string;
}

function sayHi(person: Human): string {
  return `안녕 나는 ${person.age}살의 ${person.name}이라고 해.`;
}
```

## 클래스

클래스에서 변수나 메소드 앞에 private을 붙여주면 외부 인스턴스에서 접근할 수 없다.

아래는 어드밴스한 방법으로 constructor의 인자에 public이나 private을 붙여 별도의 변수 선언을 하지 않을 수 있다.

```ts
class Car {
  constructor(public position: number, private engine: string) {
    // public이나 private을 붙여주면 this.position = position;을 생략할 수 있다.
  }
}

const car = new Car(5, 'super');
``` 

## Enum

```ts
enum Color { Red, Green, Blue = 'blue' };
```

다른 언어에 있는 enum을 사용할 수 있다.

Color.Red의 값은 0이 되고\
Color.Green의 값은 1이 된다.\
Color.Blue처럼 따로 값을 넣지 않을 경우 0부터 오름차순으로 숫자 값이 들어간다.

## Angle Brackets

```ts
let vari; // 타입이 any로 설정된다.
vari = 'a';
let str = (<string>vari); // str은 타입이 string이 된다.
// 또는 let str = (vari as string);
let any = vari; // any는 타입이 any다.
```

변수 선언시에 값을 넣으면 그 값에 해당하는 타입이 적용되지만\
위처럼 선언만 했을 경우 타입이 any로 되는데\
3번째 줄에서처럼 vari라는 변수의 타입을 변경해서 str에 넣을 수 있다.