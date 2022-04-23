# Working with 'State' (v-48)

To use state hook we need to import it

```js

import React, { useState } from 'react';

```

When we call useState Hook method to set a value like

```javascript

const [title, setTitle] = useState(props.title)
// title is value
// setTitle is a function to set title

```

It will return an array. Into that array, first variable i.e. index 0, is a variable value, which is set and second variable i.e. index 1, is a setter for updating the value of state.

[ExpenseItem.js](https://github.com/pervez8ktt/react-complete-guide-code-1/blob/04-react-state-events/code/01-working-with-state/src/components/Expenses/ExpenseItem.js)

```javascript
import React, { useState } from 'react';

import ExpenseDate from './ExpenseDate';
import Card from '../UI/Card';
import './ExpenseItem.css';

const ExpenseItem = (props) => {
  // function clickHandler() {}

  //Declare states
  const [title, setTitle] = useState(props.title);

    // title is value
    // setTitle is a function to set title

  console.log('ExpenseItem evaluated by React');
  
  //Define event handling function
  const clickHandler = () => {
    setTitle('Updated!');
    console.log(title);
  };

  return (
    <Card className='expense-item'>
      <ExpenseDate date={props.date} />
      <div className='expense-item__description'>
        <h2>{title}</h2>
        <div className='expense-item__price'>${props.amount}</div>
      </div>
      {/*

        set on click event 

      */}
      <button onClick={clickHandler}>Change Title</button>
    </Card>
  );
}

export default ExpenseItem;

```

