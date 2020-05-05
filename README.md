# Kawai To Do

Kawai To Do App made with React Native

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

```
borderTopLeftRadius: 10,
borderTopRightRadius: 10,
```

- 이런식으로 한 부분씩 따로따로도 설정 할 수 있음. 해당 코드는 상단의 좌 우 모서리 둥글게 바꾸는 것.
