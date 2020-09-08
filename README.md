# SourceX

A Redux inspired state management library, based on a Rx-flavoured subscriber model.

> ⚠️ Warning! Don't use in production! None or all of the API's might change. Strictly playground exercise material.

# Example usage

All the code is in `index.html`.

### Define your reducers

```
const user = (state = { name: "Jon Doe" }, action) => {
  switch (action.type) {
    case 'UPDATE_NAME':
      return { ...state, name: action.payload.name }
    default:
      return state
  }
}

const page = (state = { title: "Default" }, action) => {
  switch (action.type) {
    case 'UPDATE_TITLE':
      return { ...state, title: action.payload.title }
    default:
      return state
  }
}

createReducers(user, page)
```

### Subscribe to changes
```
onStateUpdate(state => {
  console.log('Got a notification about a state update. New value: ', state)
})
```

### Dispatch updates
```
dispatch({ type: 'UPDATE_NAME', payload: { name: 'Jo du Plessis' } })
dispatch({ type: 'UPDATE_TITLE', payload: { title: 'The beginning...' } })
```
