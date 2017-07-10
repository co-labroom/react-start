## Using State Correctly
#### Do Not Modify State Directly
```
this.state.comment = 'Hello';
```

Instead, use setState():
```
// Correct
this.setState({comment: 'Hello'});
```

#### State Updates May Be Asynchronous
For example, this code may fail to update the counter:
```
// Wrong
this.setState({
  counter: this.state.counter + this.props.increment,
});
```

```
// Correct
this.setState((prevState, props) => ({
  counter: prevState.counter + props.increment
}));
```

#### State Updates are Merged

#### The Data Flows Down
If you imagine a component tree as a waterfall of props, each component's state is like an additional water source that joins it at an arbitrary point but also flows down.
