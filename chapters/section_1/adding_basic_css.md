# Adding basic CSS (v-34)

- Add new css file into component folder and import it into component JS file.

```javascript

import './ExpenseItem.css'

```

- Then add classes into JSX with 'className'

```javascript
<div className='expenseItem'></div>
```

# Outputing dynamic data (v-35)

- Outputing JS data or expressiong into JSX

```javascript
<div>{JS Expression}</div>
```

# Passing Data via 'Props' (v-36)

- Adding Attribute:

```javascript
<ExpenseItem expenseData={expense.data} title={expense.title}></ExpenseItem>
```

- Using Props:

```javascript
<div>{props.title}</div>
```

# Adding Normal JS (V-37)

# Buildinng wrapper component

- Creat Wrapper Componet

[Card.js](https://github.com/pervez8ktt/react-complete-guide-code-1/blob/03-react-basics-working-with-components/code/10-the-concept-of-composition/src/components/Card.js)

```javascript

import './Card.css';

function Card(props) {
  const classes = 'card ' + props.className;
  
  return <div className={classes}>{props.children}</div>;
}

export default Card;

```

- Use wrapper component

[Expenses.js](https://github.com/pervez8ktt/react-complete-guide-code-1/blob/03-react-basics-working-with-components/code/10-the-concept-of-composition/src/components/Expenses.js)

```javascript

import ExpenseItem from './ExpenseItem';
import Card from './Card';
import './Expenses.css';

function Expenses(props) {
  return (
    <Card className="expenses">
      ....
      
      Write some Html code

      ....

    </Card>
  );
}

export default Expenses;

```