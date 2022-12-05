### FlatList - 화면에 보이는 부분만 렌더링하게 도와주는 scrollView

```jsx
<FlatList data = {guessRounds} renderItem = {(itemData) ⇒ <Text>{itemData.item}</Text>}> 

<keyExtractor={(item)⇒item}

</FlatList>
```

FlatList의 Data란에 데이터 배열이 들어가면, renderItem에 자동으로 하나씩 들어간다.

keyExtractor도 마찬가지로 FlatList에서 key값을 자동으로 설정할 수 있는데 , 이를이용해 쉽게 사용할 수 있다.
