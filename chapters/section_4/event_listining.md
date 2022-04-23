# Listening to events (v-46)

[ExpenseItem.js](https://github.com/pervez8ktt/react-complete-guide-code-1/blob/04-react-state-events/code/01-working-with-state/src/components/Expenses/ExpenseItem.js)

```javascript
import React, { useState } from 'react';

import ExpenseDate from './ExpenseDate';
import Card from '../UI/Card';
import './ExpenseItem.css';

const ExpenseItem = (props) => {
  // function clickHandler() {}
  const [title, setTitle] = useState(props.title);
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

#### Caution!!!
- Do not write onClick={clickHandler()}
- Means clickHandler with (). Because when JSX compile, it will call 'clickHandler' event directly