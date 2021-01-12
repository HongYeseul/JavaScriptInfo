# if와 조건부연산자, 그리고 논리 언산자

조건에 따라 다른 행동을 취해야 할 때, ```if```문과 ‘물음표’ 연산자라고도 불리는 조건부 연산자 ```?```를 사용하면 됩니다.

## if 문
```if(...)```문은 괄호 안에 들어가 있는 조건을 평가 하며, 만약 조건이 true라면 코드블록이 실행됩니다.

``` js
let year = 2021;
if(year == 2021){
    alert("TRUE");
} 
// 혹은 한 문장일 때
if(year == 2021) alert("TRUE");
```

- 참고
    ``` js
    // true가 1, false가 0인 것은 알고 있을 것입니다. 이를 사용하면
    if(1){
        // 무조건 실행
    }
    if(0){
        // 무조건 실행되지 않음
    }
    ```

조건이 틀렸을 때 실행되는 코드블록도 사용할 수 있습니다.   
이는 else 절을 사용합니다.

``` js
if(thisYear == 2021){
    // true
}else{
    // false
}
```

else문을 사용하면 복수로 조건을 처리 해 줄 수도 있습니다.
``` js
let thisYear = prompt('올해의 년도는?', '');
if(thisYear > 2021){
    alert( 'Down' );
}else if(thisYear < 2021){
    alert( 'Up' );
}else{
    alert('Correct!');
}
```
코드는 위에서 아래로 실행이 되기 때문에 ```thisYear > 2021``` 조건이 먼저 실행 된 후 거짓이라면 ```thisYear < 2021``` 이 실행 됩니다.

마지막에 존재하는 else문은 선택사항이므로 쓰지않아도 됩니다.

또한
``` js
if(조건){
    // 이렇게 쓰던,
}
if(조건)
{
    // 이렇게 쓰던 상관은 없습니다.
}
```

## 조건부 연산자 '?'

조건에 따라 다른 값을 변수에 할당해줘야 할 때가 있습니다.

``` js
let flag;
let age = prompt('당신의 나이는?', '');

if (age > 18) {
  flag = true;
} else {
  flag = false;
}
```

이 코드는 조건부 연산자를 사용하면 1줄로 줄일 수 있습니다.

``` js
let result = condition ? value1 : value2;
```
조건부 연산자는 피연산자가 3개이기 때문에 삼항 연산자로 불리기도 합니다.   
평가되는 조건(condition)이 true라면 value1이, false라면 value2가 result에 할당되게 됩니다.

예시
``` js
let result = (myAge > 20 ) ? true : false;
result
```

이러한 삼항 연산자를 사용하면 다중 조건을 처리 할 수도 있습니다.   
앞서 봤던 예시와 동일한 기능을 하는 코드를 만들어 보겠습니다.

``` js
let thisYear = prompt('올해의 년도는?', '');

let flag = (thisYear > 2021) ? 'Down' : 
            (thisYear < 2021) ? 'Up' : 
            'Correct';
alert(flag);

// 이 코드도 앞의 if-else문과 동일하게
let flag = (thisYear > 2021) ? 'Down' 
        : (thisYear < 2021) ? 'Up' 
        : 'Correct';
// 로 사용하셔도 됩니다.
```

삼항 연산자가 if문과 동일한 연산을 한다고 해서 삼항 연산자를 if문 대신 사용하는 것은 적절하지 않습니다.

물론 물음표를 사용하면 코드 길이가 짧아진다는 매력적인 포인트가 있으나, 이를 사용함으로 인해 가독성이 떨어지기 때문에 적절할 때만 삼항 연산자를 사용하고 그 외의 상황에서는 if-else 문을 사용하시길 바랍니다.
```
참고 ) 물음표 연산자'?'는 조건에 따라 반환 값을 달리하려는 목적으로 만들어졌습니다.
```

# Practice
- 아래 코드에서의 실행 결과는 무엇일까요?
    ``` js
    if ("0") {
    alert( 'Hello' );
    }
    ```

- if-else문을 사용하여    
    '나의 이름은 무엇일까요?' 를 물어본 후, 정답이면 '정답입니다!'를, 틀렸다면 '틀렸습니다!'   
    라는 메시지를 띄울 수 있게 만들어 보세요.

- 조건부 연산자'?'를이용한 코드로 바꾸어 보세요.
    ``` js
    let result;

    if (a + b < 4) {
    result = '미만';
    } else {
    result = '초과';
    }
    ```

- 조건부 연산자'?'를이용한 코드로 바꾸어 보세요.
    ``` js
    let message;

    if (login == '직원') {
    message = '안녕하세요.';
    } else if (login == '임원') {
    message = '환영합니다.';
    } else if (login == '') {
    message = '로그인이 필요합니다.';
    } else {
    message = '';
    }
    ```


## 논리 연산자
자바스크립트엔 세 종류의 논리 연산자 ```||```(OR), ```&&```(AND), ```!```(NOT)이 있습니다.   
논리 연산자이기 때문에 이 연산자들은 대부분 if문과 함께 사용이 됩니다.

### || (OR)   
OR 연산자는 인수 중 하나라도 ```true```이면 ```true```를, 그렇지 않으면 ```false```를 반환합니다.

``` js
let time = 3;

if (time < 10 || time > 18) { // true
  console.log( '영업시간이 아닙니다.' );
}
```
혹은 한 번에 여러 조건을 사용할 수도 있습니다.

``` js
let time = 12;
let isWeekend = true;

if (time < 10 || time > 18 || isWeekend) {
  alert( '영업시간이 아닙니다.' ); // 주말이기 때문임
}
```

### OR을 사용하여 다른 기능 이용하기

``` js
result = value1 || value2 || value3;
```
이 때, OR ```||```연산자는 다음 순서에 따라 연산을 수행합니다.

- 가장 왼쪽 피연산자부터 시작해 오른쪽으로 나아가며 피연산자를 평가합니다.
- 각 피연산자를 불린형으로 변환합니다. 변환 후 그 값이 ```true```이면 연산을 멈추고 해당 피연산자의 변환 전 원래 값을 반환합니다.
- 피연산자 모두를 평가한 경우(모든 피연산자가 ```false```로 평가되는 경우)엔 마지막 피연산자를 반환합니다.

이러한 점을 이용하면 다음과 같은 일들을 할 수 있습니다.
1. 변수 또는 표현식으로 구성된 목록에서 첫 번째 true 값 얻기
    ``` js
    let firstName = "";
    let lastName = "";
    let nickName = "닉네임";

    console.log( firstName || lastName || nickName || "익명"); // 바이올렛
    // -> 만약에 모든 변수가 false 값이라면 익명이 출력 됩니다.
    ```

2. 단락 평가   
    단락 평가는 연산자 왼쪽 조건이 false일 때만 명령어를 실행하고자 할 때 자주 쓰입니다.
    ``` js
    true || alert("not printed");
    false || alert("printed");
    // true 까지만 진행이 되므로 두 번째 줄에 존재하는 메시지만 출력됩니다.
    ```

### && (AND)
AND 연산자는 두 피연산자가 모두가 참일 때 true를 반환하고, 그 외의 경우는 false를 반환합니다.
``` js
result = a && b;
```

if문과 AND 연산자를 함께 사용한 예제입니다.
``` js
let hour = 15;
let minute = 45;

if (hour == 15 && minute == 45) {
  console.log( '현재 시각은 15:45입니다.' );
}
```

AND 연산을 사용했을 때도 OR 연산자와 마찬가지로 피연산자가 여러개였을 때에도 사용이 가능합니다.   
각 연산은 비슷하긴하지만, AND 연산자가 첫 번째 falsy를 반환하는 반면, OR은 첫 번째 truthy를 반환한다는 점이 다릅니다.

자세한 사항은 [이곳](https://ko.javascript.info/logical-operators#ref-832)을 참고하시면 좋을 것입니다.

### ! (NOT)
NOT의 연산은 무척 간단한데, 인수를 하나만 받아 반환합니다.   
만약 입력 받은 값이 true라면 false를, false라면 true를 반환 시키는 연산자 입니다.

``` js
result = !value;
```

이 연산자를 사용하여 쉽게 if문에 활용 할 수 있습니다.
``` js
let isTrue = true;

if(!isTrue){
    console.log("TRUE");
}else{
    console.log("FALSE");
}
// isTrue에 NOT 연산자를 사용하므로 false값이 if문에 사용되기 때문에 FALSE가 출력됩니다.
```

참고   
NOT을 두 개 연달아 사용(```!!``)하면 값을 Boolean형으로 바꿔 줄 수 있습니다.
``` js
console.log( !!"non-empty string" ); // true
console.log( !!null ); // false

// 이는 Boolean()을 사용한 것과 동일한 결과를 도출합니다.
console.log( Boolean("non-empty string") ); // true
console.log( Boolean(null) ); // false
```

# Practice
1. age(나이)가 14세 이상 90세 이하에 속하는지를 확인하는 if문을 작성하세요.
2. age(나이)가 14세 이상 90세 이하에 속하지 않는지를 확인하는 if문을 작성하세요.   
답안은 NOT ```!``` 연산자를 사용한 답안과 사용하지 않은 답안 2가지를 제출해야 합니다.
3. 로그인 구현하기   
문제는 [이곳](https://ko.javascript.info/logical-operators#ref-842)을 참고하세요.
