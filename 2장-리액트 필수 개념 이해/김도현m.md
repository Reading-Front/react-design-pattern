## 2.2 프롭이 있는 컴포넌트 만들기

> 하지만 관 리하기 쉬운 컴포넌트를 만들고자 한다면 프롭 속성은 가능하면 5~6개를 넘지 않는 것이 좋
> 습니다

- 5~6개의 기준은 무엇일까 ?

## 2.6 많이 사용되는 리액트 훅

- useEffect의 dependency를 비워두게 되면, 린트 에러가 발생하기 때문에 아래와 같이 처리해주어야 한다.

- dependency를 비워두는 것을 엄격하게 관리해야만 할까?

```tsx
// 올바른 코드 예시
function Counter() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `You clicked ${count} times`;
    // eslint-disable-next-line react-hooks/exhaustive-deps
  }, []);
}
```

- useCallback, useMemo 꼭 필요할까? 에 대한 의문

  - dependency가 생기게 되면서 더 관리해야 하는 코드가 늘어날 수 있다.

- Context API vs Zustand

  - Context API를 사용하게 되면, 불필요한 렌더링을 방지하기 위해 값을 사용하는 곳과 값을 분리해주어야 한다.

  - 또한, Context API가 복잡해 질수록 불필요한 렌더링을 유발할 수 있기 때문에, Context 를 분리를 해주어야 하는데

  - 그 결과 특정 컴포넌트를 감싸는 Context 가 너무 많아질 수 있다는 문제도 있다.

  - 이러한 점들을 고려해볼 때 전역상태가 아닌 상태들이더라도, 여러 컴포넌트에 사용되는 상태라면 Zustand를 사용하는게 더 생산성있는 방법이지 않을까 하는 생각
