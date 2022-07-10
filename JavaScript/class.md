## Class란?
```
class CoffeeMachine {
    constructor(coffee){
        this.coffee = coffee;
    }
}
```

*클래스 함수 이름의 첫 시작은 대문자여야 함. 일반 함수의 시작은 소문자.

 

constructor은 한국어로 생성자라고 한다. 생성자는 말 그대로 객체를 생성하게 한다.

이 생성자가 있어야 class가 호출된다.

또한, 클래스 안에서 생성자는 단 하나여야 한다. 

```

class CoffeeMachine {
    constructor(coffee){
        this.coffee = coffee;
    }
    machine(){
        console.log(`${this.coffee} 커피가 완성됐습니다.`);
    }
}
 
```

 machine()은 메소드 라고 한다. 메소드는 객체 내 프로퍼티 중 함수인 프로퍼티다.
```

const myCoffee = new CoffeeMachine("cold brew");

console.log(myCoffee.coffee);
myCoffee.machine();
```
*새 객체를 만들기 위해서는 new를 앞에 붙여주어야 한다.

결과는 아래와 같다.

```
class도입 전과 후
//before ES6
function CoffeeMachine(coffee) {
  this.coffee = coffee;
}

CoffeeMachine.prototype.machine = function() {
  return `${this.coffee} 커피가 완성됐습니다.`
}

const myCoffee = new CoffeeMachine("cold brew");

console.log(myCoffee.coffee);
myCoffee.machine();
//after ES6
class CoffeeMachine {
    constructor(coffee){
        this.coffee = coffee;
    }
    
    machine(){
        console.log(`${this.coffee} 커피가 완성됐습니다.`);
    }
}

const myCoffee = new CoffeeMachine("cold brew");

console.log(myCoffee.coffee);
myCoffee.machine();
```
*둘의 결과는 같다.

<hr>
### class의 장점
class는 함수 선언과 달리 호이스팅이 일어나지 않는다.

호이스팅은 함수 선언 유무와 상관 없이 선언 전에도 함수 사용이 가능 한 것이다.

함수를 호출하고 선언하는 경우, 호이스팅이 일어나면 문제없이 실행이 되지만,

그렇지 않으면 선언되지 않은 함수라는 에러가 뜬다.

 

호이스팅으로 인해 코드가 꼬일 수 있는 단점을 class는 해결해 줄 수 있다.

 

class는 자동으로 strict모드를 적용시킨다.

때문에, 좀 더 꼼꼼한 코딩이 가능해진다.
