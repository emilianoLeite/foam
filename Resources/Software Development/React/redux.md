# Redux

## [Don't lie to the compiler](https://phryneas.de/redux-typescript-no-discriminating-union)
Don't supply custom union types to your reducers because that will always be a lie. It is impossible to have a complete list of actions that your reducers will receive: `redux-internal`, `middlewares`, etc will dispatch their own actions, which are then passed through all reducers.
