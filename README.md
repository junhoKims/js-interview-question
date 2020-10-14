# JavaScript 인터뷰 문제 & 답안

> 해당 사이트의 인터뷰 문제를 참고하여 번역하였습니다.<br/>
> [https://dev.to/macmacky/70-javascript-interview-questions-5gfi](https://dev.to/macmacky/70-javascript-interview-questions-5gfi)
> <br><br/>
> 해당 사이트의 디자인 및 레이아웃을 참고하였습니다.<br/>
> [https://github.com/sudheerj/reactjs-interview-questions](https://github.com/sudheerj/reactjs-interview-questions)

---

### 문제 테이블

| No. | 문제 |
| --- | --------- |
|1    | [undefined와 null의 차이점은 무엇입니까?](#undefined와-null의-차이점은-무엇입니까) |
|2    | [연산자 &&는 무엇입니까?](#연산자-&&는-무엇입니까) |
|3    | [연산자 \|\|는 무엇입니까?](#연산자-\|\|는-무엇입니까) |
|4    | [+ 또는 단항 더하기 연산자를 사용하는 것이 문자열을 숫자로 변환하는 가장 빠른 방법일까?](#+-또는-단항-더하기-연산자를-사용하는-것이-문자열을-숫자로-변환하는-가장-빠른-방법일까) |

### 답안

1. ### undefined와 null의 차이점은 무엇입니까?

    undefined와 null은 JavaScript의 7개의 기본적인 타입이다.
    
    undefined와 null의 값은 false를 가진다. 이는 ( !!value ) 등을 통해 확인할 수 있다.
    ``` javascript
    console.log(!!null); //logs false
    console.log(!!undefined); //logs false
    ```

    undefined는 특정 값이 할당되지 않은 변수의 기본값이다.
    보통 선언만 하고 초기화를 하지 않은 경우에 undefined 값을 가지게된다.
    ``` javascript
    let test;
    const doNothing = () => {};

    console.log(test); //logs undefined
    console.log(doNothing()); //logs undefined
    ```
    
    null은 일종의 '값이 없는 값'이다. 명시적으로 정의된 타입 중 하나이다.
    여기서 fs.readFile 메소드가 오류를 발생시키지 않으면 null 값을 얻는다.
    ``` javascript
    var test = null;
    console.log(test);

    fs.readFile('path/to/file', (e,data) => {
      console.log(e); //it logs null when no error occurred
      console.log(data);
    });
    ```


    **[⬆ Back to Top](#문제-테이블)**
    
2. ### 연산자 &&는 무엇입니까?

    **논리 연산자**의 AND 라고 하며, 논리 연산자는 보통 Boolean(논리적) 값과 함께 쓰이며, 불리언 값을 반환한다.
    첫번째 표현식이 거짓이면 첫번째 표현식을 반환하며, 참이면 두번째 표현식을 반환한다.

    conMobile의 값이 존재한다면 true를 반환한다. 때문에 release()함수를 수행할 수 있다. if 대신 && 연산자를 사용해서 진행할 수 있다.
    ``` javascript
    // if문 사용
    if (conMobile) {
      conMobile.release();
    }

    // && 연산자 사용
    conMobile && conMobile.release();
    ```

    **[⬆ Back to Top](#문제-테이블)**

3. ### 연산자 ||는 무엇입니까?

    **논리 연산자**의 OR 라고 하며, 논리 연산자는 보통 Boolean(논리적) 값과 함께 쓰이며, 불리언 값을 반환한다.
    첫번째 표현식이 거짓이면 두번째 표현식을 반환하며, 참이면 첫번째 표현식을 반환한다.
    
    null은 false값을 가지고 1은 true값을 가진다. 때문에 1이 먼저 반환되고, undefined와 다시 || 연산을 수행한다. undefined는 false값을 가지기에 true값인 1이 리턴된다.
    ``` javascript
    console.log(null || 1 || undefined); //logs 1
    ```

    인자 name에 어떤 값도 주지 않았기 때문에 name은 undefined이며, undefined는 false 이므로 ||연산자에 의해 'Mark'를 반환한다.
    ``` javascript
    function logName(name) {
      var n = name || "Mark";
      console.log(n);
    }

    logName(); //logs "Mark"
    ```

    **[⬆ Back to Top](#문제-테이블)**
    

4. ### 단항 더하기 연산자를 사용하는 것이 숫자를 문자열로 변환하는 가장 빠른 방법일까?

    MDN Documentation에 의하면 `+`를 통한 변환은 숫자를 문자열로 변경하는 가장 빠른 방법이다. 왜냐하면 이미 숫자인 경우, 값에 대하여 어떤한 동작도 수행하지 않기 때문이다.

    ```javascript
    console.log(+'3'); // logs 3
    ```

    **[⬆ Back to Top](#문제-테이블)**