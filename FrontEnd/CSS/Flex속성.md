
## flex 레이아웃을 만들기 위한 기본 HTML 구조

```
 <div class="container">
	<div class="item">helloflex</div>
	<div class="item">abc</div>
	<div class="item">helloflex</div>
</div>
```

부모 요소인 div.container를 Flex Container(플렉스 컨테이너)라고 부르고,
자식 요소인 div.item들을 Flex Item(플렉스 아이템)이라고 부른다.

<hr>

-컨테이너에 적용하는 속성

먼저 Flex 컨테이너에 display : flex;를 적용한다.
```
.container {
	display: flex;
}
```

이렇게 적용을 하면 flex컨테이너의 아이템들이 가로로 배치가 된다.
길이는 아이템 자기 자신이 가진 내용물의 width만큼 정해진다.
height는 컨테이너의 높이만큼 늘어난다.


inline-flex 는 컨테이너가 아이템이 끝나는 길이에 맞춰서 끝나는 것이다

아이템들이 배치된 방향의 축을 메인축,
메인축과 수직인 축을 수직축(교차축)이라고 한다.
메인축은 오뎅꼬치? 라고 생각하면 된다.

메인축이 오뎅꼬치라면 flex item 은 오뎅꼬치에 꽂힌 오뎅이라고 볼 수 있다.

## flex-direction
메인축의 방향을 정하는 속성
 
 ```
.container {
	flex-direction: row;
	/* flex-direction: column; */
	/* flex-direction: row-reverse; */
	/* flex-direction: column-reverse; */
}
```
row
아이템들이 가로 방향으로 배치

aaa bbbbbb ccccccc

row-reverse
아이템들이 역순 가로 배치

                           ccccccc bbbbbb aaa

column
아이템들이 세로 방향으로 배치된다
AAAAAA
BBBBBB
CCCC

column-reverse
아이템들이 역순으로 세로 배치 된다
CCCC
BBBBBB
AAAAAAA

## flex-wrap
아이템들의 크기가 컨테이너를 초과할 때
줄바꿈을 어떻게 할지 결정하는 속성
```
.container {
	flex-wrap: nowrap;
	/* flex-wrap: wrap; */
	/* flex-wrap: wrap-reverse; */
}
```

nowrap(기본)
줄바꿈을 하지 않고 그냥 삐져 나간다

wrap
줄바꿈을 한다

wrap-reverse
줄바꿈을 하고 아이템을 역순으로 배치한다

## flex-flow

flex-direction과 flex-wrap을 한꺼번에 지정할 수 있는 단축 속성
flex-direction, flex-wrap의 순으로 한 칸 떼고 쓰면 된다

```
.container {
	flex-flow: row wrap;
	/* 아래의 두 줄을 줄여 쓴 것 */
	/* flex-direction: row; */
	/* flex-wrap: wrap; */
}
```

## justify-content
메인축 방향 정렬

```
.container {
	justify-content: flex-start;
	/* justify-content: flex-end; */
	/* justify-content: center; */
	/* justify-content: space-between; */
	/* justify-content: space-around; */
	/* justify-content: space-evenly; */
}
```

flex-start (기본값)
아이템들을 시작점으로 정렬

flex-end
아이템들을 끝점으로 정렬

center
아이템들을 가운데로 정렬

space-between
아이템들의 사이에 간격을 만들어 준다

space-around
아이템들의 둘레에 간격을 만들어 준다

space-evenly
위 두 속성보다 더 적은 간격을 만든다

