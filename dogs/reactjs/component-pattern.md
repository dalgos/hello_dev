# React Component pattern

## Container component

- 동작을 관리합니다.
- Presentation & Container Component를 모두 렌더링할 수 있습니다.
- API를 호출하거나 그 데이터를 주로 조작합니다.
- 이벤트 핸들러를 정의합니다.
- 주로 클래스로 작성됩니다.
- 마크업을 포함하지 않도록 합니다.

> Presentation Component의 교체만으로 손쉽게 화면을 변경할 수 있습니다. 데이터 조작 로직은 그대로 활용할 수 있죠.

```javascript

import Card from '../Components/Card'

export default class CardContainer extends React.Component {
  state = {
    userName: '',
    userAge: '',
  }
  componentWillMount() {
    this.getUserInfo()
      .then(({ data }) => this.setState({userName: data.userName, userAge: data.userAge}))
  }
  getUserInfo() {
    return axios.get('/userInfo')
  }
  render() {
    return (
      <Card
        name={this.props.userName}
        age={this.props.userAge}
      />
    )
  }
}

```

## Presentation component

- 시각적인 요소를 렌더링하는 컴포넌트입니다.
- 마크업과 다른 Presentation component를 렌더링할 수 있습니다.
- 사용되는 props는 부모로부터 전달받을 수 있습니다.
- state를 사용하지 않도록 작성합니다.
- functional component로 작성합니다.

> 전달하는 props interface 만 맞춘다면 다른 데이터를 활용하는 Container 에서도 재사용이 가능합니다.

```javascript

import Name from './Name'

export default Card = props => {
  return (
    <div>
      <Name text={props.name} />
      <div>{props.age}<div>
    </div>
  );
}

```