# What are *Side Effects* & Introducing *useEffect* (v-110)



![What is effect?](../../images/what_is_effect.png)

**useEffect** manages other things, which is not used to react the screen like:

- call http reaquest
- Manage timmer
- Save data into local storage

**useEffect** takes two arguments

![Handling use effect](../../images/handling_use_effect.png)

# Using the useEffect() Hook (v-111)

[App.js](https://github.com/pervez8ktt/react-complete-guide-code-1/blob/10-side-effects-reducers-context-api/code/02-using-the-useeffect-hook/src/App.js)

```js

import React, { useState, useEffect } from 'react';

import Login from './components/Login/Login';
import Home from './components/Home/Home';
import MainHeader from './components/MainHeader/MainHeader';

function App() {
  const [isLoggedIn, setIsLoggedIn] = useState(false);

  useEffect(() => {
    const storedUserLoggedInInformation = localStorage.getItem('isLoggedIn');

    if (storedUserLoggedInInformation === '1') {
      setIsLoggedIn(true);
    }
  }, []);

  const loginHandler = (email, password) => {
    // We should of course check email and password
    // But it's just a dummy/ demo anyways
    localStorage.setItem('isLoggedIn', '1');
    setIsLoggedIn(true);
  };

  const logoutHandler = () => {
    localStorage.removeItem('isLoggedIn');
    setIsLoggedIn(false);
  };

  return (
    <React.Fragment>
      <MainHeader isAuthenticated={isLoggedIn} onLogout={logoutHandler} />
      <main>
        {!isLoggedIn && <Login onLogin={loginHandler} />}
        {isLoggedIn && <Home onLogout={logoutHandler} />}
      </main>
    </React.Fragment>
  );
}

export default App;

```

The above code demostrate the simple login feature. For manage the login state we used '*local storage*'.

```js
localStorage.setItem('isLoggedIn', '1');
```

here we set isLoggedIn into localStorage.

Now as we know whenever we change any state, the whole component re-run.

So if we put 

```js
localStorage.setItem('isLoggedIn', '1');
```

code outside the **useEffect**, It will result the infinit loop.

Here **useEffect** run only once because we used empty dependency, and will never change.

If we make any change on dependency, **useEffect** will run again.