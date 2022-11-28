# ReactNative

## React Native란 뭔가 ?

- react.js + reactNative = > ios나 android같은 모바일앱을 만들 수 있다.
- react라이브러리 자체는 플랫폼에 구애받지 않는다.
- 리액트는 상태를 관리하고 가상의 컴포넌트를 구축하는 툴일 뿐이다.
- 여기에 react-dom 라이브러리등을 통해 react의 결과를 브라우저에 보여주는것 뿐
- ReactNative는 React-dom 의 대안이다.
- 리액트 네이티브에선 Native 기기 api 등을 이용해서 js를 실행할 수도 있고
- 플랫폼 대상이 웹이 아니라 ios와 android 인것

## ReactNative 내부 살펴보기

코드를 작성하면 RealNativeApp으로 컴파일되어 네이티브 앱에 묶인다..

- View 는 리액트 네이티브의 특별한 컴포넌트로 네이티브가 컴파일한다.
- 논리는 컴파일 되지 않는다.
- js로 작성한 논리는 컴파일되지 않고, 구축한 Native앱에서 네이티브가 호스트한대로 스레드로 관리한다. js코드는 앱안에서 앱을 통해 언어의 장벽은 넘어 android와 ios 와 상호작용한다.
