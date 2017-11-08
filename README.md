# JavaScript

## 1주차

## 기본 타입

- number
- String
- boolean
- undefind
- null

## 참조형 타입 

- object
  - Array
  - Function 
  - 정규식
 
 
 ## 숫자 타입
 자바스크립트는 모든 숫자를 64비트 부동 소수점 형태로 저장하기 때문에 하나의 숫자형만 존재한다
 
 ```js
 var intNum = 3;
 var floatNum = 0.3;
 
 console.log( typeof intNum , typeof floatNum );// number , number 
 ```
 
자바스크립트는 모든 숫자를 실수형으로 처리하기 때문에 나눗셈 연산을 할때 조심해야 한다
소수 부분을 버리고 정수 부분만 구하고 싶을 경우 Math.floor( ) 메소드를 사용한다

```js
var num = 5 / 2;

console.log(num); // 2.5
console.log( Math.floor( num ) ); // 2

```

## 문자열

문자열은 작은따옴표 (') 나 큰 땅옴표( " ) 로 생성 한다. 무엇으로 선언 하든 typeof 결과는 string 으로 나온다 자바스크립튼 자바 나 C의 char 과 같은 문자하나만
별도로 나타내는 데이터 타입이 존재하지 않는다
```js 
var DoubleQuote = "test";
var SingleQuote = 'test';

console.log( typeof DoubleQuote , typeof SingleQuote ); // string , string
```

자바스크립트에서 한번 선언된 문자열은 일기만 가능할뿐 수정되지 않는다

```js

var str = "test";
console.log( str[0] ); // t

str[0] = "T";
console.log( str ); // test
```

## 불린 타입

자바스크립트는 true 와 false 값을 나타내는 불린 타입 이 있다 

## null 과 undefined

이두타입 모두 자바스크립트에서 값이 비어있음을 나타낸다, 기본적으로 값이 할당되지 않은 변수가 undefined 타입이자 변수의 값 또한 undefined 이다. null 타입 
변수는 명시적으로 값이 비어있음을 나타낸다<br>
 * null같은 경우 typeof 값이 object 이기에 null타입인지 확인 하기 위해서는 일치연산자 (===) 를 사용해 변수 값을 직접 확인해야한다

```js
var nullvar = null;

console.log( typeof nullvar === null ); // fasle
console.log( nullvar === null );        // true

```

## 참조형 타입 ( 객체 타입 )

자바스크립트 에서 숫자 , 문자열 , 불린값 , null , undefined 같은 기본값을 제외한 모든 값은 객체로 배열 , 함수 , 정규표현식 등 모두 자바스크립트 객체로 표시된다
<br>

### 객체 생성 

자바스크립트에서는 클래스 라는 개념이 없고 , 객체 리터럴 이나 생성자 함수 등 별도의 생성 방식이 존재 한다<br>
자바스크립트에서의 객체 생성 방법은 크게 세가지가 있다
- 기본제공하는 Object() 객체 생성자 함수를 이용하는 방법
- 객체 리터럴을 이용하는 방법
- 생성자 함수를 이용 하는 방법

### Object() 생성자 함수 사용 

자바스크립트에서 내장 함수인 Object() 를 사용 하여 빈 객체를 만들고 몆가지 프로퍼티를 넣는 방법

```js
var foo = new Object();

foo.name    = 'foo';
foo.age     = 35;
foo.gender  = 'male';

console.log( typeof foo ); // object
console.log( foo );        // { name : 'foo' , age : 35 , gender : 'male' }

```

### 객체 리터럴 을 이용 

객체 리터럴 방식은 간단한 표기법 만으로도 객체를 만들수 있다. 중괄호 ( {} )를 이용하여 생성하는데 중괄호 안에 아무것도 넣지 않을 경우 빈 객체가 생성되며
중괄호 안에 { 프로퍼티 이름 : 프로퍼티 값 } 형태로 표기 하면 해당 프로퍼티가 추가된 객체를 생성 할수 있다

```js
var foo = {
  name : "foo" ,
  age  : 35 ,
  gender : 'male'
}

console.log( typeof foo ); // object
console.log( foo );        // { name : 'foo' , age : 35 , gender : 'male' }

```

### 생성자 함수 이용

자바스크립트 에서 내장함수 function() 을 사용 하여 생성된 객체라고 할수있다

```js
var add = new Function ( 'x' , 'y' , 'return x + y');
console.log( add ( 3 , 5 ) ); // 8
```

# 연산자

## +연산자

더하기 연산과 문자열 연결 연산을 담당한다. 값이 모두 숫자일 경우만 더하기 연산을 하고 나머지는 문자열 연결 연산이 이루어 진다

```js
 var add1 = 1 + 2;
 var add2 = 'my' + 'string';
 var add3 = 1 + 'string';
 var add4 = 'string' + 2;
 
 console.log( add1 , add2 , add3 , add4 ); // 3 , mystring , 1string , string2

```

## typeof 연산자 

typeof 는 피연산자 의 타입을 문자열로 리턴 해준다
- null 이 object 라는 점과 함수는 function 이라는것을 유의한다

## == 동등연산자  === 일치 연산자

자바스크립트에서는 두연산자 모두 사용 가능 하다 
== 연산자는 타입이 다를경우 타입변환을 하고 비교 하지만 ===은 타입변환을 거치지 않는다.

```js
  console.log( 1 == '1'); // true
  console.log( 1 === '1'); // false
``

## !! 연산자
