## align-items
수직축 방향으로 아이템들을 정렬
(=justify-content와 수직 방향 정렬)
```
.container {
	align-items: stretch;
	/* align-items: flex-start; */
	/* align-items: flex-end; */
	/* align-items: center; */
	/* align-items: baseline; */
}
```

stretch (기본값)
아이템들이 수직축 방향으로 끝까지 늘어남

flex-start (컨테이너의 위에 붙는 것)
아이템들을 시작점으로 정렬
flex-direction이 row(가로 배치)일 때는 위, column(세로 배치)일 때는 왼쪽이다.

flex-end (컨테이너의 아래에 붙는 것)
아이템들을 끝으로 정렬
flex-direction이 row(가로 배치)일 때는 아래, column(세로 배치)일 때는 오른쪽이다.

center
아이템들을 가운데로 정렬

baseline
아이템들을 텍스트 베이스라인 기준으로 정렬

*베이스 라인 이란?
<br>
Thinking! 텍스트의 맨 아래 선

*아이템을 가운데 정렬하는 법!
<br>
justify-content: cneter;<br>
align-item: center;

## align-content
flex-wrap: wrap; 이 설정된 상태에서,
아이템들의 행이 2줄 이상 되었을 때의 수직축 방향 정렬을 결정하는 속성
```
.container {
	flex-wrap: wrap;
	align-content: stretch;
	/* align-content: flex-start; */
	/* align-content: flex-end; */
	/* align-content: center; */
	/* align-content: space-between; */
	/* align-content: space-around; */
	/* align-content: space-evenly; */
}
```
stretch
수직축 방향으로 똑같이 늘어나는 것

flex-start
시작점에서 정렬

flex-end
끝점에서 정렬

center
가운데에서 정렬

space-between
컨테이너의 크기에 벗어나지 않는 속성이 맨위로, 벗어나는 속성이 맨아래로 가는것

space-around
around만큼의 빈칸을 두는 것

space-evenly
evenly만큼의 빈칸을 두는 것

*Flex 아이템에 적용하는 속성들

## flex-basis
flex-basis는 Flex 아이템의 기본 크기를 설정(flex-direction이 row일 때는 너비, column일 때는 높이).
```
.item {
	flex-basis: auto; /* 기본값 */
	/* flex-basis: 0; */
	/* flex-basis: 50%; */
	/* flex-basis: 300px; */
	/* flex-basis: 10rem; */
	/* flex-basis: content; */
}
```
기본적인 단위 모두 사용 가능하다
기본값 auto는 해당 아이템의 width값을 사용한다
width를 따로 설정하지 않으면 컨텐츠의 크기로 설정된다

## flex-grow
flex-grow는 아이템이 flex-basis의 값보다 커질 수 있는지를 결정하는 속성
flex-grow에는 숫자값이 들어가는데, 몇이든 일단 0보다 큰 값이 세팅이 되면 해당 아이템이 유연한(Flexible) 박스로 변하고 원래의 크기보다 커지며 빈 공간을 메우게 됨.
기본값이 0이기 때문에, 따로 적용하기 전까지는 아이템이 늘어나지 않는 것이다.
```
.item {
	flex-grow: 1;
	/* flex-grow: 0; */ /* 기본값 */
}
```
flex-grow에 들어가는 숫자의 의미는, 아이템들의 flex-basis를 제외한 여백 부분을 flex-grow에 지정된 숫자의 비율로 나누어 가지는 것이다.
```
/* 1:2:1의 비율로 세팅할 경우 */
.item:nth-child(1) { flex-grow: 1; }
.item:nth-child(2) { flex-grow: 2; }
.item:nth-child(3) { flex-grow: 1; }
```
