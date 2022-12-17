# Section8

## 개발 흐름

### 흐름

1. 모든 스크린 생성 후, 핵심이 되는 네비게이션 로직 짜기
2. 단계별로 스타일 추가
3. 네비게이션 옵션에 구성을 추가, 개선하는 식

---

### 개발

1. 폴더구조 세팅, Navigation 라이브러리 설치 및 필요한 Navigation 의존성 추가
2. Navigator 설정과 Main, Optional 로 쓸 라우터 설계 , Nesting 고려
3. 화면과 화면을 연결
4. Navigator 스타일링
5. Home 으로 가서 간단한 줄글로 컴포넌트 설계  후, 조각조각 컴포넌트 분리해감
6. 하드 코딩된 부분이 있다면 동적으로 propr 설정
7. 더미데이터 설정 및 출력 테스트
8. FlatList Item, Item Data, Key Extractor 들 더미데이터로 렌더링 관련 로직 설정
9. 분리한 컴포넌트 조각 스타일링
10. Prassable 추가해서 Opacity를 통해 피드백 되도록 함, onPress 구조 및 함수 생성
11. Pressable에 사용될 Handler 추가
12. 생성한 컴포넌트들을 모두 연동, 다음 스크린도 같은 작업 반복
- Screen의 Presentation 속성을 이용해 어떤 방식으로 보여줄지 설정
13. 생성한 화면에 버튼 추가, 커스텀버튼 생성,
14. 버튼을 이용한 조건부 렌더링 설정
15. 뒤로가기 로직 설정
16. 상태관리 설정
17. 상태에 따른 컴포넌트 조건부 렌더링과 데이터 없을때의 안내문 설정
---

### 유용한 코드
```javascript
const confirmHandler = () => {
    navigation.goBack();
  };
  }
 ```
 
 ```javascript
 //ManageExpense.js
const ManageExpense = ({ route, navigation }) => {

  //화면을 전환할 땐 navigation 파라미터를 params 를 받을땐 route 파라미터를 이용하자.
  const editedExpenseId = route.params?.expenseId;

  const isEditing = !!editedExpenseId;
 //boolean으로 바꿀수 있는 방법 undefined면 false가 나온다.

  useLayoutEffect(() => {

    // 처음에 깜빡거리는 걸 막기위해 useLayouytEffect해줘야함
    navigation.setOptions({
      title: isEditing ? "Edit Expense" : "Add Expense",
    });
  }, [navigation, isEditing]);

  const deleteExpenseHandler = () => {
    navigation.goBack();
  };
  const cancelHandler = () => {
    navigation.goBack();
  };
  const confirmHandler = () => {
    navigation.goBack();
  };

return ... 
}
 ```
 
 ```javascript
 //ExpenseList.js
//자동으로 data 의 itemData를 받을 수 있다.
//래퍼객체로 받음

//d이렇게 프로퍼티로 보낼때, 보내는 데이터의 속성 네임이 같으니까 알아서 객체 구조 분해 할당해서 받아간다
//수동으로 설정할 수도 있지만, 표준 js 꿀팁 >< 
const renderExpenseItem = itemData => {
  return <ExpenseItem {...itemData.item}></ExpenseItem>;
};

 ```
 
 
 
 


