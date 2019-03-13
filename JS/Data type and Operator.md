# 자바스크립트 데이터 타입


## 자바스크립트 기본 타입

- 기본 데이터 타입(숫자, 문자열, 불린값, null, undefined)
- 참조 데이터 타입(객체, 배열)


자바스크립트는 **느슨한 타입 체크 언어**이다. `var`이라는 한 가지 키워드로 변수를 선언하고 이러한 변수는 어떠한 데이터도 저장한다.

```javascript    
	// 숫자 타입
	var Num = 10;
	// 문자열 타입
	var SingleQuote = 'Hello world';
	// 불린 타입
	var boolA = true;
```
  
### 숫자
> 하나의 숫자형만 존재(모든 숫자를 실수로 처리), 나눗셈을 할 경우 주의. 정수 부분만을 원할 경우 `Math.floor()` 메서드를 이용하면 된다.
```javascript     
	var num = 5/2;
	console.log(num); // 2.5
	console.log(Math.floor(num)); // 2
```  
### 문자열
> 작은 따옴표나 큰 따옴표로 설정 가능하다. 한번 정의된 문자열은 변하지 않는다.
```javascript     
	var str = 'hello';
	console.log(str); // hello
	
	str[0] = 'T'; // str 첫 글자 T 로 변경
	console.log(str); // hello
```
  
## 자바스크립트 참조 타입
  
### 객체
> 객체를 생성하는 방법에는 3가지가 존재한다. `Object()` 객체 생성사 함수 이용, 객체 리터럴 이용 그리고 생성자 함수를 이용하는 방법이 있다.

- `Object()` 객체 생성사 함수 이용
```javascript     
	var kim = new Object();
	
	kim.name = 'kim';
	kim.age = '23';
	kim.gender = 'male';
	
	console.log(kim); //(출력값) {name: 'kim', age: 23, gender: 'male'}
```

- 객체 리터럴 방식 이용
```javascript     
	var kim = {
	name : 'kim',
	age : '23',
	gender : 'male'
	};
	
	console.log(kim); //(출력값) {name: 'kim', age: 23, gender: 'male'}
```
- 생성자 함수 이용
```javascript     
	var kim = {
	name : 'kim',
	age : '23',
	gender : 'male'
	};
	
	console.log(kim); //(출력값) {name: 'kim', age: 23, gender: 'male'}
```
  
- 객체 프로퍼티 읽기, 갱신, 동적 생성, 삭제
```javascript   
    var kim {
        name : 'kim',
        major : 'computer science'
    };
    // 객체 프로퍼티 읽기
	console.log(kim.name);  // (출력값) kim
    console.log(kim['name']); // (출력값) kim

    // 갱신
    kim.major = 'MIS';
    console.log(kim.major); // (출력값) MIS
    console.log(['major']; // (출력값) MIS

    // 생성
    kim.age = 23;
    console.log(kim.age); // (출력값) 23

	// 삭제
	delete kim.major;
	console.log(kim.major); // (출력값) undefined
```
> 자바스크립트에서 객체의 해당 프로퍼티가 없을 경우에는 새로운 프로퍼티가 동적으로 생성된 후 값이 할당된다. 
> `delete` 연산자는 프로퍼티만 삭제하고 객체 자체는 삭제할 수 없다.
  
- for in 문과 객체 프로퍼티 출력 
```javascript   
    var kim {
        name : 'kim',
        major : 'computer science',
        age : 24
    };
    // for in 문을 이용한 객체 프로퍼티 출력
    var kim {
        for (prop in kim) {
            console.log(prop, kim[prop]);
        }
    }
    /* 출력 결과
		name kim
		age 24
		major 'computer science'
	*/
```  
- 객체 비교
> 객체를 비교할 떄도 객체의 프로퍼티값이 아닌 참조값을 비교한다.
```javascript   
    var A = 100;
	var B = 100;

	var objA = { value: 100};
	var objB = { value: 100};
	var objC = objb;

	console.log(a == b); // true
	console.log(objA == objB); //false
	console.log(objB == objC); // true
```  
### 배열
> 크기를 지정하지 않아도 되며, 어떤 위치에 어느 타입의 데이터를 저장하더라도 에러가 발생하지 않는다.

- 배열 생성
```javascript   
   var ColorArr = ['red', 'yellow', 'green', 'blue'];
   console.log(ColorArr[1]); // yellow
```
> 배열에서 대괄호만 사용할 경우 빈 배열이 생성된다. 요소가 없는 빈 배열이므로 배열 원소에 접근하여도 `undefined`가 출력된다. 또한 동적 생성을 하였을 경우 배열의 인덱스 중 가장 큰 값을 기준으로 배열의 크기를 자동 설정한다.
```javascript   
   var EmptyArr= [];
   EmptyArr[0] = 1;
   EmptyArr[3] = 'hello';
   console.log(EmptyArr); // [1, undefined, undefined, hello]
```