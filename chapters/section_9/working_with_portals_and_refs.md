# Working with Portals (v-105)

Portals are used to re-structure the html into the react. For example in fragment

```js
<React.Fragment>

    <MyModel/>
    <MyAnyBody/>

</React.Fragment>

```

output of above JSX will be

```js
<div>

    <some model div/>
    <some other divs/>

</div>
```

as we know the model will work fine but still this is not a good structure.

So if we want to port react component to another place, we use <b>portals</b>

For this we use below steps

#### public/index.html
```html

<body>
    <div id="newPort"></div>
    <div id="root"></div>
</body>
```

#### component/PortalComponent.js

```js
import ReactDOM from 'rect-dom';

const PortedComponent = props =>{
    return <div> Ported </div>
}

export default PortedComponent;

```

#### component/MainComponent.js

```js

import ReactDom from 'react-dom';

const MainComponent = props => {
    return <>
            <div>Some things from Main component</div>
            {
                ReactDOM.createPortal(<PortalComponent/>, document.getElementById('newPort'))
            }
            </>
}

export default MainComponent;

```

# Working with 'Refs' (v-106)

Refs is used to get html dom into react variable. It is recommended that we should not update html dom directly, but it is ok if we just want to get the value.
To setup the connection, we need to use another react hook i.e. ** useRef **

```js

import React, {useState, useRef} from 'react';

const MainComponent = (props) => {
    const inputName = useRef('');

    const onSubmit = () => {

        e.preventDefault();
        console.info(inputName.current.value);

    }

    return <>
        <input id='userName'
                type='text'
                ref={inputName} />
        <input type='submit' onClick={onSubmit} />

        </>
}

```

# Controlled vs Un Controlled components (v-107)