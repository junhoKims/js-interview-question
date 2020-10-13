# JavaScript 인터뷰 문제 & 답안

> 해당 사이트의 인터뷰 문제를 참고하여 번역하였습니다.<br/>
> [https://dev.to/macmacky/70-javascript-interview-questions-5gfi](https://dev.to/macmacky/70-javascript-interview-questions-5gfi) 

---

### 문제 테이블

| No. | 문제 |
| --- | --------- |
|1    | [undefined와 null의 차이점은 무엇입니까?](#undefined와-null의-차이점은-무엇입니까) |
|2    | [React의 주요 기능은 무엇입니까?](#React의-주요-기능은-무엇입니까) |
|3    | [JSX는 무엇입니까?](#jsx는-무엇입니까) |

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
    
