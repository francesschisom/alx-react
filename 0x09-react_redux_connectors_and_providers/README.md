# 0x09. React Redux Connectors and Providers
Overview
The connect() function connects a React component to a Redux store.

It provides its connected component with the pieces of the data it needs from the store, and the functions it can use to dispatch actions to the store.

It does not modify the component class passed to it; instead, it returns a new, connected component class that wraps the component you passed in.

function connect(mapStateToProps?, mapDispatchToProps?, mergeProps?, options?)

The mapStateToProps and mapDispatchToProps deals with your Redux store’s state and dispatch, respectively. state and dispatch will be supplied to your mapStateToProps or mapDispatchToProps functions as the first argument.

The returns of mapStateToProps and mapDispatchToProps are referred to internally as stateProps and dispatchProps, respectively. They will be supplied to mergeProps, if defined, as the first and the second argument, where the third argument will be ownProps. The combined result, commonly referred to as mergedProps, will then be supplied to your connected component.

connect() Parameters
connect accepts four different parameters, all optional. By convention, they are called:

mapStateToProps?: Function
mapDispatchToProps?: Function | Object
mergeProps?: Function
options?: Object
mapStateToProps?: (state, ownProps?) => Object
If a mapStateToProps function is specified, the new wrapper component will subscribe to Redux store updates. This means that any time the store is updated, mapStateToProps will be called. The results of mapStateToProps must be a plain object, which will be merged into the wrapped component’s props. If you don't want to subscribe to store updates, pass null or undefined in place of mapStateToProps.

Parameters
state: Object
ownProps?: Object
A mapStateToProps function takes a maximum of two parameters. The number of declared function parameters (a.k.a. arity) affects when it will be called. This also determines whether the function will receive ownProps. See notes here.
