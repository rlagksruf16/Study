# 함수


> 함수를 생성하는 방법은 3가지가 존재한다. `add()` 함수를 3가지 방법을 통해 알아볼 것이다.
- 함수 선언문
- 함수 표현식
- `Function()` 생성자 함수

### 함수 선언문 방식
 > 반드시 함수명이 정의되어 있어야 한다. 변수타입은 기술하지 않는다.
 ```javascript     
function add(x,y) {
    return x + y;
}
console.log(add(3,4)); //7
```
> 위의 함수가 가능한 이유는 자바스크립트 엔진에 의해 함수 표현식 형태로 변경해주기 때문이다. (**함수 표현식 방식 참고**)



### 함수 표현식 방식
```javascript     
var add = function (x,y) {
    return x + y;
}
var plus = add;
console.log(add(3,4)); //7
console.log(plus(5,6)); // 11
```

> 함수명이 존재하지 않는 **익명함수** 표현 방식이다. 



> 함수명이 포함된 함수 표현식을 **기명 함수 표현식**이라고 한다. 여기에 사용된 함수명은 _외부 코드에서 접근 불가능하게_ 설정되어 있다. 
```javascript     
var add = function sum(x,y) {
    return x + y;
}
console.log(add(3,4)); //7
console.log(sum(5,6)); // 에러 발생
```


> 함수 표현식 방식에서 함수 이름을 이용하면 함수 코드 내부에서 함수 이름으로 함수의 재귀적인 호출이 가능하다. 아래의 예시를 살펴보자.
```javascript     
var factorial = function fact(n) {
    if(n <= 1) {
        return 1;
    }
    else
        return n * fact(n-1);
}
console.log(factorial(3)); // 6
```


### `Function()` 생성자 함수 호출 방식

```javascript     
var add = Function('x', 'y', 'return x + y');
console.log(add(3,4)); // 7
```