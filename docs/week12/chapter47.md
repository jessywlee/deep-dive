---
sidebar_position: 53
---
# 47장 에러 처리

## 에러 처리의 필요성

에러가 발생하지 않는 코드를 작성하는 것은 불가능하다. 발생한 에러에 대해 대처하지 않고 방치하면 프로그램은 강제 종료된다.
```try…catch``` 문을 사용해 발생한 에러에 적절히 대응하면 프로그램이 강제 종료 되지 않고 계속해서 코드를 실행시킬 수 있다.

## ```try…catch…finally``` 문

기본적으로 에러 처리를 구현하는 방법은 크게 두가지가 있다. 예외적인 상황이 발생하면 반환하는 값을 if 문이나 단축 평가 또는 옵셔널 체이닝 연산자를 통해 확인해서 처리하는 방법과 **에러 처리 코드를 미리 등록해 두고 에러가 발생하면 에러 처리 코드로 점프**하도록 하는 방법 (```try…catch…finally``` 등)이 있다. 일반적으로 이 두번째 방법을 error handling 이라한다.

```jsx
try {
	//실행할 코드 
} catch (err) {
	//try 코드 블록에서 에러가 발생하면 실행되는 코드 블록
	//err에는 try 코드 블록에서 발생한 Error 객체가 전달
} finally {
	//에러 발생과 상관없이 반드시 한 번 실행
}
```

## ```Error``` 객체

Error 생성자 함수는 에러 객체를 생성한다. 에러를 상세히 설명하는 에러 메시지를 인수로 전달할 수 있다.

```jsx
const error = new Error(’invalid’);
```

에러 객체는 message 프로퍼티와 stack 프로퍼티를 갖는다. message 프로퍼티는 Error 생성자 함수에 인수로 전달한 에러 메시지이고, stack 프로퍼티의 값은 에러를 발생시킨 콜스택의 호출 정보를 나타내느 문자열이며 디버깅 목적으로 사용한다.

자바스크립트는 Error 생성자 함수 포함 7가지 에러 객체를 생성할 수 있는 생성자 함수 (Error, SyntaxError, ReferenceError, TypeError, RangeError, URIError, EvalError) 를 제공한다. 이들 생성자 함수로 생성한 에러 객체의 프로토타입은 모두 ```Error.prototype```을 상속받는다.

## ```throw``` 문

Error 생성자 함수로 에러 객체를 생성한다고 에러가 발생하는 것은 아니다. 에러를 발생시키려면 try 코드 블록에서 throw 문으로 에러 객체를 던져야한다.

```jsx
throw 표현식;
```

**에러를 던지면 catch 문의 에러 변수가 생성되고 던져진 에러 객체가 할당**된다. 그리고 catch 블록이 실행되기 시작한다.

## 에러의 전파

에러는 호출자 방향, 즉 **콜스택의 아래 방향**으로 전파된다.

```jsx
const foo = () = > {
	throw Error();
}

const bar = () = > {
	foo();
}

cons baz  = () = > {
	bar();
}

try {
	baz();
} catch (err) {
	console.error(err);
}
```

**throw 된 에러를 캐치하지 않으면 호출자 방향으로 전파**된다. 이때 throw된 에러를 캐치하여 적절히 대응하면 프로그램을 강제 종료시키지 않고 코드의 실행 흐름을 복구할 수 있다. 어디에서도 캐치 하지 않으면 강제 종료된다.

주의: **비동기 함수인 setTimeout이나 프로미스 후속 처리 메서드의 콜백 함수는 호출자가 없다**는 것. setTimeout이나 프로미스 후속 처리 메서드의 콜백 함수는 태스크 큐나 마이크로태스크 큐에 일시 저장되었다가 콜 스택이 비면 이벤트 루프에 의해 콜스택으로 푸시되어 실행된다. **이때 콜스택에 푸시된 콜백 함수의 실행 컨텍스트는 콜 스택의 가장 하부에 존재하므로 에러를 전파할 호출자가 존재하지 않는다.**