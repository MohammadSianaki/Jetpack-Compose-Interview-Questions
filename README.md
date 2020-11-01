# Jetpack-Compose Interview Questions

### 1. What is Composable function?
Composable functions are Kotlin functions that are marked with the `@Composable` annotation. This annotation informs the Compose compiler that this function is intended to convert data into UI.

### 2. What is Recomposition?
When the app’state changes, the composable functions are called again with the new data. This causes the UI elements to be redrawn--this process is called recomposition.

### 3. What is a `Modifier`?
Modifier parameters tell a UI element how to lay out, display, or behave within its parent layout, You can think of them as  a decoration pattern.

### 4. What is an `Ambient`?
Compose passes data through the composition tree explicitly through means of parameters to composable functions. This is often times the simplest and best way to have data flow through the tree. But this can be cumbersome for certain types of data that are required by many components. For these cases, `Ambient`s can be used as an implicit way to have data flow through a composition.


### 5. What is the difference between a `Stateful Composable` and a `Stateless Composable`?
A stateful composable is a composable that owns a piece of state that it can change over time.
A stateless composable is a composable that cannot directly change any state.


### 6. What is State Hoisting?
In Composable functions, state that can be useful to calling functions should be exposed because it's the only way it can be consumed or controlled—this process is called state hoisting. State hoisting is the way to make a component stateless.

### 7. What is `remember` compoable and when we should use it?
`remember` is a helper composable function that only recompute the memoized value when one of the keys to rembemer has changed. This optimization helps to avoid expensive calculations on every recomposition.<br/>
- ##### Values remembered in composition are forgotten as soon as their calling composable is removed from the tree.
- ##### They will also be re-initialized if the calling composable moves in the tree. You can cause this in the LazyColumnFor by removing items at the top.

### 8. Why Composable functions should be side-effects free?

- Composable functions can execute in any order.
- Composable functions can execute in parallel.
- Recomposition skips as many composable functions and lambdas as possible.
- Recomposition is optimistic and may be canceled.
- A composable function might be run quite frequently, as often as every frame of an animation.


### 9. Hwo to restore state acress process death or configuration change?
If you work with immutable objects, use `saveInstanceState` Composable, if you work with mutable objects use `rememberSavedInstanceState` Composable


