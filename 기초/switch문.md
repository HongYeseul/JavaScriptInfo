# switch문
복수의 if 조건문은 switch문으로 바꿀 수 있습니다.

## 문법
```switch```문은 하나 이상의 ```case```문으로 구성됩니다. 대개 ```default```문도 있지만, 이는 필수는 아닙니다.

``` js
switch(x) {
  case 'value1':  // if (x === 'value1')
    ...
    [break]

  case 'value2':  // if (x === 'value2')
    ...
    [break]

  default:
    ...
    [break]
}
```
변수 x값과 value변수들의 값을 비교하여 일치하면 case ~ break 사이의 코드들을 수행합니다.

여기서 주의해야 할 것은 ```break```를 꼭 써주어야 한다는 점입니다.   
break문이 없다면 다음 ```case```의 코드까지 실행이 됩니다.

예시
``` js
let a = 2 + 2;

switch (a) {
  case 3:
    alert( '비교하려는 값보다 작습니다.' );
    break;
  case 4:
    alert( '비교하려는 값과 일치합니다.' );
    break;
  case 5:
    alert( '비교하려는 값보다 큽니다.' );
    break;
  default:
    alert( "어떤 값인지 파악이 되지 않습니다." );
}
```

break가 없을 때
``` js
let a = 2 + 2;

switch (a) {
  case 3:
    alert( '비교하려는 값보다 작습니다.' );
  case 4:
    alert( '비교하려는 값과 일치합니다.' );
  case 5:
    alert( '비교하려는 값보다 큽니다.' );
  default:
    alert( "어떤 값인지 파악이 되지 않습니다." );
}
```

예제2
``` js
let a = 3;

switch (a) {
  case 4:
    alert('계산이 맞습니다!');
    break;

  case 3: // (*) 두 case문을 묶음
  case 5:
    alert('계산이 틀립니다!');
    alert("수학 수업을 다시 들어보는걸 권유 드립니다.");
    break;

  default:
    alert('계산 결과가 이상하네요.');
}
```
이와 같이 a의 값이 3, 5였을 때 동일한 코드를 실행 하게 할 수도 있습니다.

### 자료형의 중요성
자바스크립트에서 switch-case문을 사용할 때는 자료형에 맞추어 사용을 해야합니다.
``` js
let arg = prompt("값을 입력해주세요.");
switch (arg) {
  case '0':
  case '1':
    alert( '0이나 1을 입력하셨습니다.' );
    break;

  case '2':
    alert( '2를 입력하셨습니다.' );
    break;

  case 3:
    alert( '이 코드는 절대 실행되지 않습니다!' );
    break;
  default:
    alert( '알 수 없는 값을 입력하셨습니다.' );
}
```

# Practice
1. 제시된 'if'문을 'switch'문으로 변경해 보세요.
  ``` js
  let a = +prompt('a?', '');

  if (a == 0) {
    alert( 0 );
  }
  if (a == 1) {
    alert( 1 );
  }

  if (a == 2 || a == 3) {
    alert( '2,3' );
  } 
  ```
