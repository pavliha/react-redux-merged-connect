# react-redux-merged-connect

utility that merges mapStateToProps and mapDispatchToProps to single function


### Example usage

```js
import { Component } from 'react'
import { shape, func, string } from 'prop-types'
import connect from 'react-redux-merged-connect'
import { actions } from 'src/state'

class Example extends Component {

  logout = () => {
    const { redux } = this.props
    redux.logoutUser()
  }

  render() {
    const { redux } = this.props
  }
}

Example.propTypes = {
  redux: shape({
    url: string,
    logoutUser: func,
  }),
}

const redux = state => ({
  url: state.ui.home.url,
  logoutUser: actions.auth.logout,
})

export default connect(redux)(Example)

```
