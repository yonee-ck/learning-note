# Exception Handling

### 예외처리: 프로그램 실행 중 문제가 발생했을 경우 대처할 수 있도록 처리하는 것

### throw
강제로 예외를 발생시키는 경우 throw 키워드를 사용한다.
사용자 정의 예외를 던질 수 있다.
현재 함수의 실행이 중지되고 throw 이후의 명령문은 실행되지 않는다. 
컨트롤은 콜 스택의 첫 번째 catch(예외 처리기) 블록으로 전달되며, 
호출자 함수 사이에 catch 블록이 없으면 해당 함수를 호출했던 블록으로 그 예외가 전파되어 올라간다.
(호출 스택(call stack)을 따라서 예외가 전파되어 올라감)
콜 스택을 따라 올라가도 예외 처리기가 없다면 이 예외는 에러로 취급

```js
    let active = false
    
    if (!el) throw el
    active = true
    return active
```

### try...catch

실행할 코드블럭을 표시하고 예외(exception)가 발생(throw)할 경우의 응답을 지정한다.
try 절에 코드를 작성. try 절에서 예외가 발생할 경우 catch 절이 호출.
맨 마지막 finally 절은 앞의 try 절의 결과와 관계 없이 항상 실행이 보장된다.
(break, return 문 등으로 인해 try 블록에서 제어가 빠져 나와도 finally 절은 실행. 무조건 try 절 실행 후 바로)

```js
    try {
        result = A / B;
        // A or B가 숫자가 아닌 경우 에러 발생!
    } catch (e) {
    /** try 절에서 예외가 발생한 경우에만 실행
     * 지역 변수 e를 사용하여 Error 객체나 try 절에서 전달 받은 값을 참조할 수 있다.
     */
        console.error('연산 에러 발생 ', e);
    } finally {
        alert('연산을 종료합니다.')
    }
```
