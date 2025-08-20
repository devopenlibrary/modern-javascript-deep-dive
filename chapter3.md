# 3장 자바스크립트 개발환경과 실행 방법

## 3.1 자바스크립트 실행 환경

브라우저와 Node.js 는 자바스크립트를 해석하고 실행할 수 있는 자바스크립트 엔젠을 내장하고 있다. 한가지 주의할 점은, **브라우저와 Node.js는 용도가 다르다**는 것이다. 

- 브라우저 : 자바스크립트를 실행해 **웹 페이지를 브라우저 화면에 렌더링**하는 것이 목적.
- Node.js : 자바스크립트 **실행 환경을 제공**하는 것 자체가 목적.

따라서 브라우저와 Node.js 모두 핵심 문법인 ECMAScript 는 실행가능 하지만, **추가로 제공하는 기능은 Node.js 에서 호환되지 않는다**.

대표적으로 **브라우저는 파싱된 HTML 요소를 선택하거나 제어하는 DOM API를 제공**하지만, Node.js 에서는 제공하지 않는다. 당연하게도 브라우저 외부환경에서는 DOM을 제어할 필요가 없기 때문이다.

반대로 **Node.js에서는 파일을 생성하고 수정할 수 있는 파일 시스템을 기본제공**하지만, 브라우저는 그렇지 않다.

이처럼 **브라우저만이 사용할 수 있는** DOM, XMLHttpRequest, fetch 등 과 같은 API를 **클라이언트 사이드 Web API**라고 부른다. **Node.js 역시 고유한 API** 를 지원한다.

![alt text](/img/chapter3/browser-and-nodejs.png)

이를 염두에 두고 자바스크립트 개발 환경을 구축하고, 자바스크립트를 실행하는 방법을 살펴보자.

## 3.2 웹 브라우저

다양한 웹 브라우저가 있지만 이 책에서는 구글 크롬 브라우저를 사용한다. 크롬 브라우저 역시 V8 자바스크립트 엔진을 사용하고 있다.

### 3.2.1 개발자 도구

크롬 브라우저가 제공하는 **개발자 도구**는 웹 앱 개발에 필수적인 강력한 도구다. 개발자 도구는 크롬에 내장되어 있어 별도의 설치가 필요하지 않다. 개발자 도구는 다음의 단축키로 열수 있다.

- 윈도우 : F12 or Ctrl + Shift + I
- MacOS : command + option + I

개발자 도구는 웹 개발에 유용한 다양한 기능을 제공한다. 

- Elements : 웹 페이지의 DOM과 CSS를 살펴볼수 있다.
- Console : 웹 페이지의 에러를 확인하거나, 자바스크립트 소스코드에서 작성한 console.log 메서드의 실행 결과를 확인할 수 있다.
- Sources : 웹 페이지의 자바스크립트 코드를 디버깅할 수 있다.
- Network : 웹 페이지에 관련된 네트워크 요청 정보와 성능을 확인할 수 있다.
- Application : 웹 스토리지, 세션, 쿠키 등을 확인하고 관리할 수 있다.

자세한 내용은 [Chrome DevTools](https://developer.chrome.com/docs/devtools/overview?hl=ko) 에서 확인해보자.

### 3.2.2 콘솔

개발자 도구의 Console 기능(이하 콘솔)은 **자바스크립트 코드에서 에러가 발생할 경우 가장 먼저 살펴보아야할** 곳이다.

혹은, 구현 단계에서 디버깅보다 간편하게 코드의 실행 결과를 확인하면서 개발을 진행하기 위해 console.log 메서드를 사용하는 경우가 많은데, 그 결과를 확인할 수 있는 것이 콘솔이다.

콘솔은 자바스크립트 코드를 직접 입력해 그 결과를 확인할 수도 있다. 이를 REPL(Read Eval Print Loop: 입력 수행 출력 반복) 환경이라고 부른다.

<p align="center">
  <img src="img/chapter3/console.png" alt="설명" />
</p>

### 3.2.3 브라우저에서 자바스크립트 실행

<a href="./hi.html" target="_blank" rel="noopener noreferrer">HTML 파일 새창에서 열기
</a>

```html
<!DOCTYPE html>
<html>
   <meta charset="UTF-8"> 
   <title>Javascript in browser</title>
   <body>
    <h1>Hi</h1>

    <script>
        alert("Hi");
    </script>
    </body>
</html>
```
