# HOC(Higer-Order-Component)

컴포넌트를 입력받아서 조작을 거친 상위 컴포넌트를 반환하는 형태를 의미합니다. 클래스로 작성된 React Component는 `extends`를 이용한 상속이 불가능함으로 아주 요긴하게 사용할 수 있는 개념입니다.

## 기본패턴

```javascript
export default component => enhancedComponent
```

예를 들어 특정 props를 다수의 component에 전달하고자 하는 경우 아래와 같이 작성이 가능합니다.

```javascript
export default WrappedComponent => props => <WrappedComponent {...props} someProp='Hello!' />
```

기본 WrappedComponent를 입력받아 functional component로 반환하는데, 그 반환값은 최초 입력해준 WrappedComponent에 `someProp`이라는 특정 props을 전달한 WrappedComponent를 반환하게 되는 구조입니다.

## Class Component 반환하기

state를 가져야 하고 그 state를 하위 component에 전달하기 위한 목적으로 사용하고자 할땐 class component로 반환하여 이용하면 됩니다.

```javascript
export default WrappedComponent => class extends React.Component {
  state = {
    data: null,
  }
  get withDearName() {
    return `Dear ${this.props.name}`;
  }
  componentWillMount() {
    fetch('/some').then(res => this.setState({ data: res.data }))
  }
  render() {
    return <WrappedComponent {...this.props} data={this.state.data} name={this.withDearName} />
  }
}
```

이런 형태로 활용이 가능합니다. 상속이 안되는 React 환경에서 다양한 component의 재사용성을 높일 수 있는 패턴입니다.