## CSS Grid

<hr>

Grid 는 flex 와는 다르게 두방향 레이아웃 시스템이다

Grid를 사용할때는 flex와 마찬가지로 display : grid를 주고 시작한다.

## 용어 정리

* Grid container<br>
아이템들을 감싸는 큰 틀

* Grid item<br>
컨테이너 안에 있는 아이템

* Grid Track<br>
Grid의 행(Row) 또는 열(Column)

* Grid Cell<br>
Grid의 한 칸

* Grid Line<br>
Grid 셀을 구분하는 선

* Grid Number<br>
Grid 라인의 각 번호
  
* Grid Gap<br>
Grid 셀 사이의 간격
  
* Grid Area<br>
Grid 라인으로 둘러싸인 사각형 영역

<hr>

## grid-template-rows
## grid-template-columns

그리드의 형태를 정의해 주는 것 <br>

```js
ex) 	grid-template-columns: 200px 200px 500px;<br>
colums는 열 배치 <br>
ex) 	grid-template-rows: 200px 200px 500px; <br>
row는 행 배치 <br>
```
## grid-template-columns: 1fr 1fr 1fr;
fr의 의미는 숫자 비율대로 그리드를 나누겠다는 것<br>
예제는 1:1:1 비율로 그리드를 나누겠다는 뜻이다<br>

### 이런식으로 컨테이너의 폭을 조절 할 수 있다

## repeat 함수
```js
	grid-template-columns: repeat(5, 1fr);
  ```
  repeat 함수는 반복되는 값을 자동으로 처리 할 수 있는 함수이다.<br>
  repeat(반복횟수,반복값)을 넣어주면 된다.
  
  ## minmax 함수
 최솟값과 최댓값을 지정할 수 있는 함수
```js
	grid-template-rows: repeat(3, minmax(100px, auto));
  ```
  이 코드의 의미는 최소한 100px 최대한 auto라는 의미이다.
  
  
