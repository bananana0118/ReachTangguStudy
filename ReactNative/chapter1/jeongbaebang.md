### React Native란 무엇인가

하나의 코드로 ios와 Android용 모바일 앱을 구축할 수 있다.

해당 플랫폼과 상호 작용하고 플랫폼을 위한 앱을 구축하기 위한 모든 컴포넌트와 API를 제공

### React Native원리

코드를 작성하면 Real Native App 코드로 컴파일

```<View />, <Text />```등 특정 컴포넌트를 사용한 JSX 요소는 각 플랫폼의 네이티브 요소로 컴파일된다.

React Native는 재사용 가능한 컴포넌트를 매핑하고 컴파일한다.

### JSX 외부에서 작성하는 JavaScript 코드는 어떻게 될까

UI 요소와 다르게 논리는 컴파일되지 않는다.

구축한 네이티브 앱 안에서 React Native가 호스트한 대로 JavaScript 스레드에서 실행된다.

즉 React Native는 간단한 JavaScript 프로세스를 구축하고 있는 네이티브 앱의 일부로 만들어

자동으로 이 프로세스를 관리해 네이티브 플랫폼과 상호작용할 수 있도록 한다.

app.json 파일은 React Native 앱의 설정과 실행 방식을 구성한다.
