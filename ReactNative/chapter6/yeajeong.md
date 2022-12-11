## imageUrl 사용법

```
<Image source={{ uri: imageUrl }} style={styles.image} />
```

##Platform.OS

- platform에 따른 스타일링 하기
```
overflow: Platform.OS === "android" ? "hidden" : "visible",
```

## Pressable


```javascript
      <Pressable
        android_ripple={{ color: "#ccc" }}
        style={({ pressed }) => (pressed ? styles.buttonPressed : null)}
        onPress={pressHandler}
      >
```

pressable은 자동적으로 pressed라는 인자가 있는데, 스타일링 할때 위처럼 pressed 됐을때의 스타일을 설정할 수 있다.



## Screen들끼리 상호작용하기
- screen들은 navigation에서 넘겨주는 navigaton 인자와 route 인자를 받을 수 있다.
- 그 인자들을 이용해 서로 상호작용한다.

```javascript

//MealDetailScreen.js

const MealDetailScreen = ({ route, navigation }) => {
  const { mealId } = route.params;

  const selectedMeal = MEALS.find(meal => meal.id === mealId);

  const headerButtonPressHandler = () => {
    console.log("pressed!");
  };
...
}
``` javascript
//MealItem.js

...
  const pressHandler = () => {
    navigation.navigate("MealDetail", { mealId: id });
  };
  
...

```

- 이런식으로 인자로 넘긴 mealId를 route.params로 받는다.

- 중간에 screen을 사용하지 않고 컴포넌트로 소통해야 할 때가 있는데, 그럴때는

```
const navigation = useNavigation();
``` 

- 위처럼 리액트 네이티브 에서 제공하는 훅을 사용해야 한다. 리액트 네이티브 훅을 사용하면 어느 페이지에서든지 접근할 수 있기때문.



## Navigation
- Stack Navigator
- Drawer Navigator
- Tab Navigator

- Navigation을 중첩할 수 있다. 중첩할 Navigator를 따로 만들어두고 Screen에서 연동할 컴포넌트에 해당 Navigator를 리턴하는 부분을 넣으면 된다. 
- 그러면 그 스크린에 네비게이터가 추가된다
``` javascript
   <Stack.Screen
            name="Drawer"
            component={DrawerNavigator}
            options={{ headerShown: false }}
></Stack.Screen>
```
- 각 네비게이터 마다 option요소가 조금씩 다르다.
