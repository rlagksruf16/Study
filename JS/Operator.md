# 연산자

> 자바스크립트 연산자의 대부분은 다른 언어와 유사하다.

 ### typeof 연산자
 > typeof 연산자는 피연산자의 타입을 문자열 형태로 리턴한다. null가 배열은 `object`, 함수는 `function`이다.

 ### ==(동등) 연산자와 ===(일치) 연산자
 > == 연산자는 비교하려는 피연산자의 타입이 다를 경우 변환을 거친 다음 비교한다.
 > === 연산자는 타입이 다를 경우 변환을 하지 않고 비교한다.
 
 ```javascript     
	console.log(1 == '1'); // true
	console.log(1 === '1'); // false
```

 ### !! 연산자
 > 피연산자를 불린값으로 변환하는 연산자이다.
 ```javascript     
	console.log(!!0); // false
	console.log(!!1); // true
```