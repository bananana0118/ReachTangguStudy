# 챕터2

### App 컴포넌트

App 컴포넌트는 유일한 컴포넌트로서 최조 진입점으로 앱에 렌더링 되는 루트 컴포넌트이다.

Expo가 자동으로 App 컴포넌트를 App.js 파일에서 내보내서 루트 컴포넌트로 렌더링 진행.
### 핵심 컴포넌트

React-Native에서 제공하는 컴포넌트 이외에 웹에서 사용하는 태그는 사용을 할 수 없다.

React-Native 본질은 내장된 핵심 컴포넌트르 다루는 것이다.

UI를 구성하는 커스텀 컴포넌트는 핵심 컴포넌트를 합쳐서 만든것이다.

사용자 인터페이스를 구축할 때 다른 중요한 측면은 앱 스타일링

**View 컴포넌트** 

콘텐츠를 담는 상자나 컨테이너 구축에 사용되는 핵심 컴포넌트

다른 컴포넌트를 담을 순 있지만 텍스트를 표시할 순 없다.

컴포넌트를 담는 데 사용하는 유일한 컨테이너 컴포넌트

**Text 컴포넌트**

화면에 텍스트를 표시하는 컴포넌트

**ScrollView 컴포넌트**

목록이나 콘텐츠를 스크롤 가능한  속성을 제공하는 컴포넌트

스크롤 가능한 영역은 부모 요소가 결정하기 때문. → View가 차지할 높이를 설정하는 style을 적용.

**FlatList 컴포넌트**

기존 ScrollView 컴포넌트는 사용자에게 보이지 않더라도 모든 컨텐츠를 렌더링하는 한다.

컨텐츠의 개수가 동적이라면 사용자가 보이는 영역만 렌더링 할 수 있도록 최적화 시켜줘야 한다.

FlatList 컴포넌트는 목록을 최적화 시켜주는 컴포넌트이다.

data, renderItem 속성을 통해 리스트를 렌더링 한다.

Key 속성을 포함하는 객체를 전달하면 FlatList가 자동으로  Key 프로퍼티를 찾는다.

KeyExtractor 프로퍼티를 통해서 입력 테이터에 Key 프로퍼티를 설정하는 방법도 있다.

```jsx
<FlatList 
	data={data}
	renderItem={() => {}}
	**keyExtractor={(item, index)} => {
		return item.id;
  }}**
/>
```

**Pressable 컴포넌트**

특정 컴포넌트에 터치이벤트를 발생시킬때 사용하는 컴포넌트

onPress 속성을 제공한다.

style 속성에 함수를 전달할 수 있는데 전달되는 매개변수는 버튼 등의 요소를 눌렀는지에 대한 불리언 값이 들어있다.

**Modal 컴포넌트**

visible 속성을 통해 모달의 표시 유무를 선택할 수 있다.

**Image 컴포넌트**

source 속성에 require() 함수로 이미지의 경로를 지정해 주어야 한다.

### 앱 스타일링

React-Native에는 CSS가 없다.

대신 인라인 스타일을 적용하거나 **StyleSheet 객체**를 사용한다.

StyleSheet을 통해 유효성 검증을 할 수 있고 성능 향상에도 도움을 줄 수 있다.

결국 자바스크립트 객체를 통해서 스타일링을 작성하는 것.

React-Native 팀은 최대한 CSS와 비슷한 프로퍼티를 제공하기위해 비슷하게 디자인 됐다.

스타일을 지정하려면 style 프로퍼티를 지원하는 컴포넌트에 style 객체를 전달해주면 된다.

****CSS와 최대한 비슷한 형식을 유지하는 것이 RN의 목표****

웹용 CSS와 달리 스타일은 연속적으로 적용되지 않는다 → 스타일 상속이 되지 않는다.

***하지만 상속을 코드적으로 구현이 가능하다.**

**배경색상 지정**

Expo를 사용하는 경우 app.json에서 속성을 통해서 한번에 배경색상 지정이 가능하다.

### 레이아웃 구축

**플렉스 박스**

React-Native에서 구현된 플렉스 박스는 CSS 플렉스 박스와 유사하다.

**모든 기본값은 플렉스 박스로 구성되어 있다.**

해당 컨테이너 내부에 요소를 배치한다.

플렉스 박스를 통해 자식 컴포넌트를 정리한다.

플렉스 박스는 컨테이너 상의 두 축이 중요

row: left - right (수평) 

column: top - bottom (수직) (**기본값)**

주축과 교차축으로 요소를 나열 (main-asix, cross-axis)

justifyContent - 주축

alignitems - 교차축

**flex 속성**

flex: 1 설정은 화면의 모든 너비를 사용하겠다는 뜻

속성의 값은 서로 상대적인 값이다 → 각 flex 속성의 값의 합이 5이고 3을 지정한다면 5분의 3을 차지

### 이벤트 처리

이벤트 처리, 상태 관리 등 React의 핵심 기능은 웹용 React와 같은 방식으로 작동한다.
