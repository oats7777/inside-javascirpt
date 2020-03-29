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
  ```
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
```
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
  ```
    // null 타입 변수 생성
    var nullVar = null;
    
    console.log(typeof nullVar === 'null'); // false
    console.log(nullVar === null); // true
  ```
  # 참조타입(객체 타입)
