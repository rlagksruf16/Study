# 자바스크립트 데이터 타입과 연산자


## 자바스크립트 기본 타입

- 기본 데이터 타입(숫자, 문자열, 불린값, null, undefined)
- 참조 데이터 타입(객체, 배열)


자바스크립트는 **느슨한 타입 체크 언어**이다. `var`이라는 한 가지 키워드로 변수를 선언하고 이러한 변수는 어떠한 데이터도 저장한다.

```html    
	// 숫자 타입
	var Num = 10;
	// 문자열 타입
	var SingleQuote = 'Hello world';
	// 불린 타입
	var boolA = true;
```

### 숫자
> 하나의 숫자형만 존재(모든 숫자를 실수로 처리), 나눗셈을 할 경우 주의. 정수 부분만을 원할 경우 `Math.floor()` 메서드를 이용하면 된다.
```html    
	var num = 5/2;
	console.log(num); // 2.5
	console.log(Math.floor(num)); // 2
```
### 문자열
> 작은 따옴표나 큰 따옴표로 설정 가능하다. 한번 정의된 문자열은 변하지 않는다.
```html    
	var str = 'hello';
	console.log(str); // hello
	
	str[0] = 'T'; // str 첫 글자 T 로 변경
	console.log(str); // hello
```

## 자바스크립트 참조 타입

### 객체
> 객체를 생성하는 방법에는 3가지가 존재한다. `Object()` 객체 생성사 함수 이용, 객체 리터럴 이용 그리고 생성자 함수를 이용하는 방법이 있다.

- `Object()` 객체 생성사 함수 이용
```html    
	var kim = new Object();
	
	kim.name = 'kim';
	kim.age = '23';
	kim.gender = 'male';
	
	console.log(kim); //(출력값) {name: 'kim', age: 23, gender: 'male'}
```

- 객체 리터럴 방식 이용
```html    
	var kim = {
	name : 'kim',
	age : '23',
	gender : 'male'
	};
	
	console.log(kim); //(출력값) {name: 'kim', age: 23, gender: 'male'}
```
- 생성자 함수 이용
```html    
	var kim = {
	name : 'kim',
	age : '23',
	gender : 'male'
	};
	
	console.log(kim); //(출력값) {name: 'kim', age: 23, gender: 'male'}
```