# Class Component pattern

Class component can contain state, use reactjs native methods.

```javascript

import React from 'react'
import PropTypes from 'prop-types'

export default class MyContainer extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0,
    }
    this.clickHandler = this.clickHandler.bind(this)
  }
  componetWillReceiveProps(nextProps) {
    // do something...
  }
  clickHandler(evt) {
    evt.preventDefault();
    console.log(evt);
  }
  render() {
    return (
      <div>
        {this.props.context}
        <span>{this.state.count}</span>
        <a href='javascript: void(0);' onClick={this.clickHandler}>Click Me!</a>
      </div>
    );
  }
}

MyContainer.defaultProps = {
  context: ''
};

MyContainer.propTypes = {
  context: PropTypes.string.isRequired
};

```

no-constructor pattern with `babel-preset-stage-0`

```javascript

import React from 'react'
import PropTypes from 'prop-types'

export default class MyContainer extends React.Component {
  state = {
    count: 0
  }
  static defaultProps = {
    context: ''
  }
  static propTypes = {
    context: PropTypes.string
  }
  componetWillReceiveProps(nextProps) {
    // do something...
  }
  clickHandler = evt => {
    evt.preventDefault()
    console.log(evt)
  }
  render() {
    return (
      <div>
        {this.props.context}
        <span>{this.state.count}</span>
        <a href='javascript: void(0);' onClick={this.clickHandler}>Click Me!</a>
      </div>
    );
  }
}

```