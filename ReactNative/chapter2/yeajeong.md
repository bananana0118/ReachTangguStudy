## ReactNative Bind 에 대해서

객체 지향 프로그래밍에서 OOP의 this 를 이용하기 위해 bind가 필요

```jsx
var obj = {  
    prop: 'Hello',
    sayHello: function() {
        console.log( this.prop );
    }
};
 
obj.sayHello(); //"Hello"

//const reference = obj.sayHello(obj);
//reference(); // "undefined"

const reference = obj.sayHello.bind(obj);

reference(); // "Hello"
```

- 변수에 담길때 this와의 관계가 상실되서 undefined가 뜰 때, 필요한게 바인딩이다.
- onClick = {this.handleClick.bind(this)} 이런식으로 하면
- 이벤트가 발생했을때 해당 this를 가리킴
- bind를 하면 함수내의 this가 바인딩된 객체를 가리킨다.
- const reference = obj.sayHello.bind(obj);
- 즉 윗 문장은 obj.sayHello가 가리키는 객체가 obj이로 하는것

### 리액트에서의 바인딩이란

- React에서 컴포넌트에 이벤트 메서드를 연결하는 방법이다.

```jsx
onClickButton = () => {
        this.setState(() => ({ hidden: true }));
      }

<button onClick={this.onClickButton}>숨기기</button> 
```

- 위처럼 사용하면 현재의 이벤트에  화살표함수가 자동으로 바인딩 시켜줘서 bind 함수를 쓸 필요가 없다.

### DimensionAPI

- 기기의 너비와 높이를 받을 수 있다.
- dimensions.get(’screen’).get 은 상태표시줄과 스테이터스 바를 포함한 사이즈
- dimensions.get(’window’).get 은 상태표시줄 등등을 제외한 사이즈다.

### 화면방향에 따라 동적으로 설정하기

- 디멘션 api로는 앱 실행중 화면이 돌아갈때 함수가 재실행 되지 않으므로 hook을 사용해서 동적으로 설정할 수 있는게 좋다.
- useWindowDimensions
- const {width, height} = useWindowDimensions();
- 기기가 회전할 때마다 use훅이 재사용되고 동적으로 높이를 설정할 수 있게 된다.

### 스타일 병함

 <View style = {[styles.rootContainer, { marginTop:marginTopDistance} ]}> </View>

이런식으로 배열을 이용하여 다중 스타일을 적용할 수 있다.

### FlatList - 화면에 보이는 부분만 렌더링하게 도와주는 scrollView

```jsx
<FlatList data = {guessRounds} renderItem = {(itemData) ⇒ <Text>{itemData.item}</Text>}> 

<keyExtractor={(item)⇒item}

</FlatList>
```

FlatList의 Data란에 데이터 배열이 들어가면, renderItem에 자동으로 하나씩 들어간다.

keyExtractor도 마찬가지로 FlatList에서 key값을 자동으로 설정할 수 있는데 , 이를이용해 쉽게 사용할 수 있다.
