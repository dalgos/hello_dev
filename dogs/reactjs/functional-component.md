# Functional Component pattern

stateless 컴포넌트를 작성하고자 할때 사용하는 기본적인 패턴입니다.

```javascript

export default props =>
  <div>
    {props.context}
  </div>

```

state를 가지고 있지 않으며, react의 내장 메서드를 사용하지 않습니다. props를 통해 전달된 속성이 변경될 경우 새로 그려지며, `presentation component`의 기본 형태입니다.