# JavaScript or ECMAScript
## Tips & Tricks
### Destructuring a Function Arguments
Let's say you have an object `myFriend` that you are passing to a function and you only need to use its first name and last name, `firstName` and `lastName`. You can **destructure the function parameter** to trim off the unnecessary properties.

```javaScript
const myFriend = {
    firstName: 'Ryan',
    lastName: 'Gosling',
    favoriteColor: 'blue',
    height: '180 cm',
    // and a bunch more properties
};

const sayHiTo = ({firstName, lastName}) => {
    console.log(`Hi ${firstName} ${lastName}! I hope you're doing great!`);
};

sayHiTo(myFriend);
```
---
### Destructuring Deep Down into Function Arguments
What if you have a more complex object and you want to drill deep down to its properties?
```javascript
const johnDoe = {
    name: {
        first: 'John',
        last: 'Doe'
    },
    company: {
        name: 'GitHub',
        address: {
            city: 'Quezon'
        }
    }
}
```
Instead of doing:
```javascript
const urgePersonToWork = (person) => {
    console.log(`${person.name.first}, you need to go to ${person.company.address.city} City now.`);
}
```

You can do this instead:
```javascript
const urgePersonToWorkDestructure = (
    {
        name: { first },
        company: { 
            address: {city}
        }
    }) => {
    console.log(`${first}, you need to go to ${city} City now.`);
}
```

---

## Workflow
### Copying Formatted JSON
```javascript
// Where 2 is number of spaces per indent
copy(JSON.stringify(obj, null, 2));
```
