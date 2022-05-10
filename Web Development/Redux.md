![ecc2a110ef91faf140e1721bab9dd206.png](../_resources/ecc2a110ef91faf140e1721bab9dd206.png)

We put states in the Redux Store and whenever a component requires it, can just use it from there

What is Redux


 **Redux** is a pattern and Library for managing and updating **Application State**, using events called **Action**. It serves as a Centralized store for state that needs to be used accross the entire Application, with rules ensuring that the state can only be updated in a **Predictable** fashion.

Redux Main Topics : 

![8f0b21a3e77d46727105780d732d92f7.png](../_resources/8f0b21a3e77d46727105780d732d92f7.png)

1. **Action** : What to do - see useReducer()
   {
      type: 'Increment',
      payload: num
   }
2. **Reducer** : How to do => useReducer Hook => (state, action)
3. **Store** : Centralized => Object which holds the state of the Application
4. **createStore** : How to create store
5. **dispatch(action)** : see useReducer()
6. **getState()** : get current value of the state.


1.1 **Action Creator** : 
```js
export const incNum = (num)=>{
   return {
      type: 'Increment',
      payload: num
   }
}
```

(oldState, Action) &rarr; **Reducer** &rarr; newState
![322b7a3abb333f50280f5decc75a229e.png](../_resources/322b7a3abb333f50280f5decc75a229e.png)

![c4267a5c5f9f02a10015f32d84531948.png](../_resources/c4267a5c5f9f02a10015f32d84531948.png)


**Redux Store** brings togerher state, action & Reducer.

We will only have a single store in a Redux App

Every Redux Store has a **single root** Reducer function

```js
import {createStore} from 'redux';

const store = createStore(rootReducers);
```

### Redux Principles

1. Single Source of Truth : Global 



![695c2fcf5c64dfb4f2876d3c5c319396.png](../_resources/695c2fcf5c64dfb4f2876d3c5c319396.png)


Pure function : same input same o/p


Jitna man kare utna reduces banao lekin rootReduer ka andar sabko dal do

