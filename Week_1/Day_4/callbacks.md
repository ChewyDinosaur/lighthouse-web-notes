# Callbacks

## Callbacks....

... are a Design pattern

... Are just functions

...that we use in response to an event

### Imperative Coding

You, as the coder, are telling the computer HOW to do what you want it to do.

```js
for (var i = 0; i < list.length; i++) {
  console.log(list[i]);
}
```

### Declarative Coding

You, as the coder, telling the computer WHAT you want it to do.

```js
list.forEach(function(item) {
  console.log(item);
});

setTimeout(function() {
  console.log("Kaboom");
}, 10000);

list.forEach(function(item) {
  console.log(item * 2);
});
```

### Pseudocode

We want a function called backwards()

We will call it like this: backwards(list, callback)

It should:

* Return the list, reversed (aka backwards), or whatever I decide to tell the callback to do
* I need a list of something Given the list, I will do the following to reverse it: I can take each element of the list, and make it the first element of a new list

[Example code fro the lecture](https://gist.github.com/donburks/f4015adc098b045ba2fb2e979ce302a5)