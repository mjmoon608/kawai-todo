# Kawai To Do

Kawai To Do App made with React Native

android emulator reload 단축키: R+R

## 3 Coding the UI part One

`<StatusBar barStyle="light-content" />`

- AOS : 시간나오는 상태표시줄 뜸 -> default 상태
- IOS : 시간나오는 상태표시줄 글씨가 흰색으로 변경

`<StatusBar barStyle="dark-content" />`

- AOS : 시간나오는 상태표시줄 안뜸
- IOS : 시간나오는 상태표시줄 글씨가 검은색으로 변경 -> default 상태

`const { height, width} = Demensions.get("window")`

- 응용 프로그램 창의 너비와 높이를 얻을 수 있습니다.
- https://reactnative.dev/docs/dimensions

- StyleSheet 에서 `borderRadius: 10` 는 네모난 모서리를 둥글게 바꿔줌
  - <b>완전 동그란 원을 만들때는 borderRadius는 항상 width, height의 절반이어야 함.</b>

```
borderTopLeftRadius: 10,
borderTopRightRadius: 10,
```

- 이런식으로 한 부분씩 따로따로도 설정 할 수 있음. 해당 코드는 상단의 좌 우 모서리 둥글게 바꾸는 것.

- 쉐도우 효과는 플래폼마다 약간 다름. IOS, AOS 마다 말하는 것인듯.

  - 이렇게 플래폼마다 다를 때는 platform-specific code 를 해야함. -> 타겟을 안드로이드로 할 건지 애플로 할껀지 설정하는 것.
  - IOS의 경우 사용해야 하는 것.

  ```
  shadowColor: "rgb(50,50,50)",
  shadowOpacity: 0.5,
  shadowRadius: 5,
  shadowOffset: {
      height: -1,
      width: 0,
  }
  - shadowOffset 에서 height, width의 양수, 음수 값으로 어디방향으로 얼만큼 그림자를 만들지 설정 함.
  ```

  - AOS의 경우 elevation 이라는 걸 사용해야함. 이는 0부터 5까지 있음. 숫자가 클수록 쉐도우가 커짐
  - 안드로이드의 경우 좀 더 제한적임

  ```
  elevation: 5
  ```

- 안드로이드, 아이폰 등 각 플래폼마다 다르게 설정하는 법.

```
...Platform.select({
      ios: {
        shadowColor: "rgb(50,50,50)",
        shadowOpacity: 0.5,
        shadowRadius: 5,
        shadowOffset: {
          height: -1,
          width: 0,
        },
      },
      android: {
        elevation: 3,
      },
    }),
```

## 4 Coding the UI part Two - Input and To Do Components

- TextInput 설정
  - `returnKeyType={"done"}` 을 하게되면 핸드폰 키보드의 엔터키(?)를 done 으로 바꾸게 됨.
  - `autoCorrect={false}` 을 하게되면 자동수정 없앰.

```
<TextInput
            style={styles.input}
            placeholder={"New To Do List"}
            value={newToDo}
            onChangeText={this._controlNewToDo}
            placeholderTextColor={"#999"}
            returnKeyType={"done"}
            autoCorrect={false}
/>
```

## 5 Conding the UI part Three - To Do Component

- ScrollView 안에 styles를 패스하는 방법.

```
<ScrollView contentContainerStyle={styles.toDos}>
    <ToDo />
</ScrollView>
```
