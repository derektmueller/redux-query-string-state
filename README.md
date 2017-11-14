
Redux middleware for synchronizing the URL query string with Redux state. Redux state keys can be mapped to query string parameters. When the Redux state updates, the state is JSON and url encoded and added to the URL query string. On page load, the Redux state is hydrated from the state encoded in the URL query string.

## Usage

```
import { combineReducers, createStore, applyMiddleware } from 'redux'
import reducers from 'reducers';
import UrlState from 'middleware/urlState';

const urlState = new UrlState(['exampleReducer1']);

const reducers = combineReducers({
  exampleReducer1: () => {},
  exampleReducer2: () => {}
});

const store = createStore(
  reducers,
  urlState.getPreloadedState(),
  applyMiddleware(urlState.getMiddleware()));
```


## Development

```
npm install
```

## Testing

```
npm run-script test
```
