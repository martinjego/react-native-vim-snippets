# Vim React Native Snippets

Requires [UltiSnips](https://github.com/SirVer/ultisnips).

## Installation

Using [vim-plug](https://github.com/junegunn/vim-plug):

```vim

" React Native code snippets
Plug 'martinjego/vim-react-native-snippets'

" Ultisnips
Plug 'SirVer/ultisnips'

" Trigger configuration (Optional)
let g:UltiSnipsExpandTrigger="<tab>"
let g:UltiSnipsJumpForwardTrigger="<tab>"
let g:UltiSnipsJumpBackwardTrigger="<C-z>"
```

## Usage
In a JavaScript or JSX file, type a trigger name while in Insert mode, then press Ultisnips trigger key. In my case I have it mapped to `<tab>`.

For example, let's say we have `ListItem.js`

In Insert mode

```javascript
rnredux<tab>
```

Will expand to

```javascript
import React, { Component } from 'react';
import { View, Text, Stylesheet } from 'react-native';
import PropTypes from 'prop-types';
import { connect } from 'react-redux';
import styles from './Screen';

class Screen extends Component {
	static propTypes = {
		children: PropTypes.string,
	};

	constructor(props) {
		super(props);
	}

	render() {
		return (
			<View style={styles.container}>
				<Text>Screen</Text>
			</View>
		);
	}
}

function mapStateToProps(state) {
	return {};
}

export default connect(mapStateToProps)($1);

const styles = StyleSheet.create({
  container: 1,
})
```

## Snippets

#### Skeleton

| Trigger  | Content |
| -------: | ------- |
| `rnredux→`  | React Native Redux Class Component |
| `rnclass→`   | React Native Class Component |

#### Lifecycle

| Trigger  | Content |
| -------: | ------- |
| `cwm→`   | `componentWillMount() {...}` |
| `cdm→`   | `componentDidMount() {...}` |
| `cwrp→`  | `componentWillReceiveProps(nextProps) {...}` |
| `scup→`  | `shouldComponentUpdate(nextProps, nextState) {...}` |
| `cwup→`  | `componentWillUpdate(nextProps, nextState) {...}` |
| `cdup→`  | `componentDidUpdate(prevProps, prevState) {...}` |
| `cwu→`   | `componentWillUnmount() {...}` |
| `ren→`   | `render() {...}` |


#### PropTypes

| Trigger    | Content |
| -------:   | ------- |
| `pt→`      | `propTypes {...}` |
| `pt.a→`    | `PropTypes.array` |
| `pt.b→`    | `PropTypes.bool` |
| `pt.f→`    | `PropTypes.func` |
| `pt.n→`    | `PropTypes.number` |
| `pt.o→`    | `PropTypes.object` |
| `pt.s→`    | `PropTypes.string` |
| `pt.no→`   | `PropTypes.node` |
| `pt.e→`    | `PropTypes.element` |
| `pt.io→`   | `PropTypes.instanceOf` |
| `pt.one→`  | `PropTypes.oneOf` |
| `pt.onet→` | `PropTypes.oneOfType (Union)` |
| `pt.ao→`   | `PropTypes.arrayOf (Instances)` |
| `pt.oo→`   | `PropTypes.objectOf` |
| `pt.sh→`   | `PropTypes.shape` |
| `ir→`      | `isRequired` |

#### Others

| Trigger  | Content |
| -------: | ------- |
| `props→` | `this.props` |
| `state→` | `this.state` |
| `set→`   | `this.setState(...)` |
