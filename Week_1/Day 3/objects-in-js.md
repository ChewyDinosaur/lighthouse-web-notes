
## Objects

> What is an object?

A structure that contains data, and the methods to act on that data

Every object has methods to get and set the data on the object

```javascript
var don = {
  name: "Don Burks",
  email: "don@lighthouselabs.ca",
  admin: true,
  password: "fluffybunny"
};
```
We can have "getter" methods, which retrieve a value stored in a property. For example:

`console.log(don.admin); //true`

We can also have "setter" methods, which change the value stored in a property. For example:

`don.password = "rutabaga";`

Setter methods can also create new properties on an object. 

`don.tired = true;`

### this

This was our introduction to `this`. We looked at a function that we created in a property on one of our objects, and unpacked what the keyword `this` was going to refer to. We defined `this` as:

> `this` is a variable that is a local variable inside of a function. Created automatically by JavaScript, it is a reference to the object that invoked the function.

```javascript
function() { 
  console.log(this.name + " says, 'Hello'");
}
```

## Secrets to Programming

Programming is a language. It isn't math. Because it's a language, programming is us explaining a solution to a computer in a language it understands. This means that we as humans have to understand the solution first. If we don't know how we as humans would solve the problem, we cannot tell the computer how to do it. 

Also, the secret to programming is LSD:

* Logic
* Syntax
* Data

### Logic

 - Am I telling the computer to do the operations in a logical order that will produce a successful outcome?

### Syntax

  - Am I using the correct methods, and the correct operations that match my logic?

### Data

  - Do I have access to the data I expect, in the format I expect?