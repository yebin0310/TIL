## Hoisting

JavaScript에서 호이스팅(hoisting)이란,

번역과 동시에 프로그램을 한 줄 단위로 즉시 실행시키는 프로그램)가

변수와 함수의 메모리 공간을 선언 전에 미리 할당하는 것을 의미한다.

 
```
function whoAreYou(name) {
  console.log("나는 " + name + "입니다.");
}

whoAreYou("크리스");

/*
result : "나는 크리스입니다."
*/
 ```
```
whoAreYou("장크리스");

function whoAreYou(name) {
  console.log("나는 " + name + "입니다.");
}

/*
result : "나는 장크리스입니다."
*/
 ```
 
호이스팅의 대상은 선언문만 가능
JavaScript는 초기화를 제외한 선언만 호이스팅

변수를 먼저 사용하고 그 후에 선언 및 초기화가 나타나면,

사용하는 시점의 변수는 기본 초기화 상태(var 선언 시 undefined, 그 외에는 초기화하지 않음)이다
```
console.log(num); 
var num; // 선언
num = 6; // 초기화
/*
result : undefined
호이스팅한 var 선언으로 인해 undefined 출력
*/
반면, 다음 예제는 선언 없이 초기화만 존재

따라서 호이스팅도 없고, 변수를 읽으려는 시도에서는 ReferenceError 예외가 발생

console.log(num); // result : ReferenceError
num = 6; // 초기화
```
