## CSS cursor 속성

cursor 속성을 이용하면 해당 태그 위에 위치하는 마우스 커서의 모양을 바꿀 수 있다

auto: 자동
default: 기본값 (화살표)
pointer: 손가락 모양 (클릭 가능한 버튼)
wait: 로딩

.btn-wait { cursor: wait } // wait 라는 버튼에 cursor:wait 라는 속성 부여
```js
<style type="text/css">
	.cursors span{
		display: inline-block;
		margin: 5px;
		padding: 5px 10px;
		background-color: #d2f4ff;
		border: 2px solid #09c;
	}
</style>
```
```js
<div class="cursors">
	<span style="cursor: auto">Auto</span>
	<span style="cursor: crosshair">Crosshair</span>
	<span style="cursor: default">Default</span>
	<span style="cursor: pointer">Pointer</span>
	<span style="cursor: move">Move</span>
	<span style="cursor: e-resize">e-resize</span>
	<span style="cursor: ne-resize">ne-resize</span>
	<span style="cursor: nw-resize">nw-resize</span>
	<span style="cursor: n-resize">n-resize</span>
	<span style="cursor: se-resize">se-resize</span>
	<span style="cursor: sw-resize">sw-resize</span>
	<span style="cursor: s-resize">s-resize</span>
	<span style="cursor: w-resize">w-resize</span>
	<span style="cursor: text">Text</span>
	<span style="cursor: wait">Wait</span>
	<span style="cursor: help">Help</span>
</div>
```

## Clear 속성
float 속성을 통해 태그를 띄운 후 문서의 흐름을 제어하기 위해 쓰임

left: 좌측 부유 제거
right: 우측 부유 제거
both: 양쪽 모두 제거

```js
<html>
<head>
<style>
	.float-container{ width: 320px; border: 2px solid #09c; }
	.float-container img{ float: left; margin: 5px; padding: 5px; border: 2px solid #90C; }
</style>
</head>
<body>
	<div class="float-container">
		<img src="/images/attach/earth.jpg">
		<p>This is first line with floating image.</p>
		<p style="clear: both">This is second line with cleared property.</p>
	</div>
</body>
</html>
```

## float 속성

웹 페이지에서 이미지를 어떻게 띄워서 텍스트와 함께 배치할것인가에 대한 속성

inherit: 부모 요소에서 상속<br>
left: 왼쪽에 부유하는 블록 박스를 생성. 페이지 내용은 박스 오른쪽에 위치하며 위에서 아래로 흐름.<br>
right: 오른쪽에 부유하는 블록 박스를 생성. 페이지 내용은 박스 왼쪽에 위치하며 위에서 아래로 흐름. 이후 요소에 clear 속성이 있으면 페이지 흐름이 달라짐. none 이 아니라면 display 속성은 무시된다.<br>
none - 요소를 부유시키지 않음<br>
```
.content > img{ float: left }
```
```js
<html>
<head>
<style>
	.float-container{
		width: 320px;
		border: 2px solid #09c;
	}
	.float-container img{
		float: left;
		margin: 5px;
		padding: 5px;
		border: 2px solid #90C;
	}
</style>
</head>
<body>
	<div class="float-container">
		<img src="/images/attach/earth.jpg">
		Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
		tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
		quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
		consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
		cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
		proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
	</div>
</body>
</html>
```
