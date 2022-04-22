# Javascript basics

- Let : Variable values
- const: Constant values

## Arrow function

```javascript
const myFunction = (param) => {
    ...
}
```
Is equivalent to 

```javascript
function myFunction(param){
    ...
}
```

Arrow function will not change the context at runtime so no need of 'this' keyword into arrow function

## Exports and Imports

#### person.js

```javascript
const person = {
    return 'max';
}

export default person;
```

#### utility.js

```javascript

export const clean = () =>{
    ...
}

export const baseData = 10;

```


1. Import the default exported. We can give any name like person or man.

```javascript
import person from './person.js';
```

2. It is called named import. we need to give exact name as given at the time of export. We can import more then one exported value into one statement by sperate it in comma.

```javascript
import {clean} from './utility.js';
```
3. Here we import all the exorted values.

```javascript
import * as util from './utility.js';
```
