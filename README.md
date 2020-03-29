# inside-javascirpt
인사이드 자바스크립트 내용 정리

## 목차
1. 자바스크립트 데이터 타입과 연산자
* 기본타입
  - 숫자
  - 문자열
  - 불린값
  - undefined
  - null
* 참조타입
  - 객체
    + 배열
    + 함수
    + 등등

---
# 기본타입
## 숫자
 자바스크립트는 하나의 숫자형만 존재한다.
## 문자열
  한번 정의된 문자열은 변하지 않는다
  ```javascript
    // str 문자열 생성
    var str = 'test';
    console.log(str[0], str[1], str[1], str[2], str[3]); // (출력값) test
    
    // 문자열의 첫 글자를 대문자로 변경
    str[0] = 'T';
    console.log(str); // (출력값) test
  ```
  즉 자바스크립트에서의 문자열은 읽기만 가능하고 수정은 불가능하다.
## 불린값
`0, -0, null, false, NaN, undefined, 빈 문자열 ("")`이라면 객체의 초기값은 `false`
```javascript
  consolel.log(!!'')  // false
  console.log(!!0)    // false
  console.log(!!-0)   // false
  console.log(!!null) // false
  console.log(!!NaN)  // false
  console.log(!!undefined) // false
  console.log(!![]) // true  이부분에서 실수를 많이 하는 것 같다.
  console.log(!!{}) // true
```
## undefined & null
  두타입 모두 '값이 비어있음'을 나타낸다.
  기본적으로 할당되지 않았을 경우 `undefined`, 명시적으로 비어있음을 나타낼 경우 `null`.
  
  null 의 typeof는 `null`이 아닌 `object` 이므로 `일치 연산자(===)`를 사용 할 것
  ```javascript
    // null 타입 변수 생성
    var nullVar = null;
    
    console.log(typeof nullVar === 'null'); // false
    console.log(nullVar === null); // true
  ```
# 참조타입(객체 타입)
  위에 원시형 타입을 제외한 나머지 타입은 참조타입이라고 볼 수 있다.
## 객체 생성
  객체를 생성하는 방법은 크게 3가지 정도로
  1. Object() 생성자 함수이용
  2. 객체 리터럴 방식 이용
  3. 생성자 함수 이용
  으로 분류된다.
### Object() 생성자 함수 이용
```javascript
  var obj1 = new Object(); // Object 생성자 함수 이용
  var obj1.name = 'MK';
  console.log(typeof obj1)
  console.log(obj1); // {name: "mk"}
```
### 객체 리터럴 방식 이용
```javascript
  var obj1 = {
    name: 'MK',
    age: 21,
    fn: function() {} // 이처럼 프로퍼티가 함수일 경우 메서드라고 한다.
  }

  console.log(typeof obj1) // object
  console.log(obj1); // {name: "MK", age: 21, fn: ƒ}
```
### 생성자 함수 이용
함수를 통해 객체를 반환하는 형태로 객체생성이 가능하다.
(생성자 함수 학습후 추후 내용 추가)

## 객체 프로퍼티 읽기/쓰기/갱신
객체의 프로퍼티에 접근하려면 다음과 같이 두 가지 방법을 사용하여 접근이 가능하다.
1. 마침표(.) 표기법
2. 대괄호([]) 표기법

```javascript
  var obj1 = {
    name: 'MK',
    age: 21,
    fn: function()
  }
  
  // 객체 프로퍼티 읽기
  console.log(obj1['name']) // MK
  console.log(obj1.name) // MK
  console.log(obj1.lastname) // undefined - 해당 프로퍼티가 존재하지 않으므로 undefined가 출력된다.

  // undefined - 프로퍼티 이름을 문자열 형태로 만들지 않으면 name.toString()를 호출하게 되는데,
  // name.toString의 값은 '' 이므로 obj1['']과 같아진다 이로인해 결과는 undefinde
  console.log(obj1[name])
  
  // 객체 프로퍼티 갱신
  obj1.name = 'HMK'
  console.log(obj1.name) // HMK
  console.log(obj1['name']) // HMK
  
  // 객체 프로퍼티 동적할당
  obj1.address = 'korea'
  console.log(obj1.address) // korea - 프로퍼티가 존재하지 않을 시 프로퍼티를 추가하여 korea 라는 값을 할당했다.
  
  // 대괄호 표기법만을 사용해야 할 경우
  obj1['full-name'] = 'MK.Han' // 접근 할려는 프로퍼티가 표현식이거나 예약어일 경우 대괄호 표기법만을 사용해야 한다.
  console.log(obj1['full-name']) // MK.Han
  console.log(obj1.full-name) // NaN - full - name 으로 인식하여 undefined - undefined = NaN
```
## 참조 타입의 특성
