<h2> java스크립트의 소스코드는 html head태그 안에 들어감<br>
연동시 - >  <script src="../이름.js"></script>
<br/>
  <br/>
자료형

<h2> Primitive <h2/>
  
<li> boolean
<li> null
<li> undefined
<li> Number
<li> String

<h4> Object <h4/>
  
<li> Reference타입
  <br>

변수선언(C언어와 유사)
var(지역변수),let,const
-> var을 선언하지 않으면 자동으로 전역변수

ex) var intput = 'input1';
console.log(input);

if(true){
var input = 'input2';
console.log(input);

console.log(input);
<br/>
  <hr>
<h4> Hoisting ****
  <br/>
  <br/>
  <p>
끌어올리기 라는 사전적 의미를 지님. 변수에 할당된 형태를 제외한 모든 변수 선언은 호이스트됨.
<p/>
if (true) {
  console.log(input); // undefined
  var foo = 'input1';
  console.log(input);
}

-> 일반적으론 input이라는 변수가 선언되지 않고 쓰였기 때문에 에러가 나야 맞음. 하지만
함수선언이 호이스팅 되어 input변수에 할당 되었으므로 오류 X
<br/>
  <br/>
  <hr>
String 변수
문자열 표현<br/>
ex ) var string;<br/>
string = "Hello";
