# DOM 트리

간단한 문서를 이용해 DOM 구조에 대해 알아보겠습니다.

``` html
<!DOCTYPE HTML>
<html>
<head>
  <title>사슴에 관하여</title>
</head>
<body>
  사슴에 관한 진실.
</body>
</html>
```

이러한 HTML은 [이곳](https://ko.javascript.info/dom-nodes#ref-121)과 같이 태그 트리 구조로 표현합니다.

이 사진에서 각 객체들은 노드라고 부르고, ```<html>```은 루트 노드, ```<head>```와 ```<body>```는 루트 노드의 자식이 됩니다.

위 그림에서 ```<title>``` 태그는 "사슴에 관하여"라는 텍스트 노드를 자식으로 갖습니다.

## Practice
[ __프로젝트__ ] ```document```가 제공하는 프로퍼티들을 이용하여 TodoList를 작성할 수 있는 만들어 봅시다.