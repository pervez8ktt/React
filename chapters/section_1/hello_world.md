# Hello World

[Git Example](https://github.com/pervez8ktt/react-complete-guide-code-1/tree/03-react-basics-working-with-components/code/01-starting-setup)

#### [index.js](https://github.com/pervez8ktt/react-complete-guide-code-1/blob/03-react-basics-working-with-components/code/01-starting-setup/src/index.js)

```javascript

import ReactDOM from 'react-dom';

import './index.css';
import App from './App';

//Note 1
ReactDOM.render(<App />, document.getElementById('root'));

```


- Note 1: Root element is at [/public/index.html](https://github.com/pervez8ktt/react-complete-guide-code-1/blob/03-react-basics-working-with-components/code/01-starting-setup/public/index.html)


#### [App.js](https://github.com/pervez8ktt/react-complete-guide-code-1/blob/03-react-basics-working-with-components/code/01-starting-setup/src/App.js)

```javascript

function App() {
  return (
    <div>
      <h2>Let's get started!</h2>
    </div>
  );
}

export default App;


```

## JSX (Javascript XML)

JSX is a code which is used into component for build HTML

## Component

The component is just a JS Function