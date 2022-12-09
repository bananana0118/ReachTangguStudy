### 섀도우

IOS에서는 배경색상을 지정해 주어야 borderRadius를 나타낼 수 있다.

overflew 속성을 플랫폼 별로 따로 관리해줘야 한다.

ios에서 overflew:hidden을 제거하면 borderRadius 상단 모서리가 제대로 표시되지 않은 이슈가 있다.

→ 내부컨테이너에 borderRadius를 지정과 overflew: hidden 속성을 지정

### React Navigation

라우팅 및 내비게이션을 추가하기 위해 만들어진 패키지 (컴포넌트 기반 라이브러리)

네이티브 스택은 네이티브 플랫폼 요소를 사용하기 때문에

네이티브 동작을 흉내 내는 스택보다 성능이 더 높을 수 있다.

기본 화면 옵션을 설정하는 방법 (내비게이터에 등록된 모든 화면에 적용)

→ 감싸고 있는 네이게이터에 적용시키면 된다. (screenOption 객체에 값 전달.)

화면중 한곳에 헤더 스타일 적용되어 있다면 충돌이 일어날 수도있다.

useNavigation

Screen으로 등록되지 않은 컴포넌트 내에서 내비게이션을 사용해야 할때 사용하면 좋다.

useRoute

Screen으로 등록되지 않은 중첩 컴포넌트에서 route 프로퍼티를 대신해서 값에 접근이 가능하다.

화면 간 데이터 전달하는 방법

두번째 인자로 객체를 전달한다. → 이후에 route.params 파라미터로 값을 받는다.

아웃소싱 

함수의 참조값으로 프로퍼티로 전달하는 방식 

코드의 가독성을 높이기 위해서

```jsx
function fn() {}     

<Component renderItem={fn} />
```

웹 이미지를 사용할 때는 이미지에 맞는 가로와 세로 너비 스타일을 지정해 줘야 한다.

 

네비게이션 옵션 동적으로 설정하기

Screen 컴포넌트의 option 속성에 함수를 전달할 수 있는데,

이때 두개의 매개변수를 전달 받는다. route, Navigation

반환값은 객체를 반환시켜야 한다.

```jsx
<Stack.Screen
	name="MealsOverview"
  component={MealsOverviewScreen}
  options={({ navigation, route }) => {
   return {
    title: route.params.categoryId,
   };
  }}
/>
```

부수효과는 useEffact 훅을 통해서 처리해야 한다.

navigation.setOptions 메소드를 통해서도 동적으로 설정이 가눙하다.

```jsx
useLayoutEffect(() => {
    const categoryTitle = CATEGORIES.find(category => {
      return category.id === catId;
    }).title;

    navigation.setOptions({
      title: categoryTitle,
    });
  }, [catId, navigation]);
```

useLayoutEffect

애니메이션이 실행되는 동안 부수 효과를 설정하거나 실행할 때 사용할 수 있다

컴포넌트가 렌더링 되기 전에 부수효과를 실행.

effect 함수를 컴포넌트 함수 실행과 동시에 실행.

React Native Text에는 경계선 스타일을 적용할 수 없다.

네비게이터 중첩기능도 지원한다.
