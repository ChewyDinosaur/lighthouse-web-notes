# The Dev Workflow

## Important Mindsets

### The Growth Mindset

Potential Skill -> Realized Skill

1. You must practice to turn your potential skill into realized skill
1. With practice, your small potential skill can become a great realized skill

### The Design Mindset

#### Convergence

* What you want to accomplish
* What you'll create to make that happen
* Make stuff
* Reflect
* Repeat

##### Divergence

* Exploration
* Start small, get gradually bigger
* What over How

### Creative (Sticks & Carrots)

* Carrots and Sticks work the opposite of how you think they should. They produce a focusing effect that can blind you to important signals and possible ways to address problems.
* As you're going, listen to your own motivations, and develop the ones that produce good results.

# Problem Solving

### Requirements

Join an array together in one comma-separated string.

* joinList([]) -> ""
* joinList(["one"]) -> "one"
* joinList(["one", "two"]) -> "one, two"

### Design

```js
// (String[]) -> String
function joinList(strings){
  if(strings.length === 0){
    /* TODO: Return an empty string */
  } else if(strings.length === 1){
    /* TODO: Return the first string */
  } else {
    /* TODO: Return the strings comma-separated */
  }
}

console.log("joinList([])", joinList([]));
console.log("joinList(['one'])", joinList(['one']));
console.log("joinList(['one', 'two'])", joinList(['one', 'two']));
```

### Implementation (and Experimentation)

Here, we implement our design, always focusing on what our code does, and running it as frequently as possible.

We may get to a spot where we reach the end of our abilities. At that point, we can use exploration to try a few things. Here, we create another file to test our techniques:

```js
// iterating.wtf.js
var conceptList = ["gists", "types", "operators", "iteration", "problem solving"];

var output = "";

conceptList.forEach(function(value, index){
  output += value + "(" + index + ")";
});

console.log(output);
```

### Debugging

```js
function joinList(concepts){
  if(concepts.length === 0){
    /* Return an empty string */
    return "";
  } else if(concepts.length === 1){
    /* Return the first string */
    return concepts[0];
  } else {
    /* TODO: Return the strings comma-separated */
    var output = "";
    concepts.forEach(function(concept, index){
      output += concept + ", ";
    });
    return output;
  }
}
```

This version does most of what we want it to do, but it has some problems. In debugging, we answer two important questions:

* What is happening?
* What do we want to happen?

### Refactoring

At this point, we clear up the code for readability and performance. WHATEVER CHANGE WE MAKE, WE MUST TEST TO SEE THAT IT STILL WORKS AS INTENDED!

```js
function joinList(concepts){
  var output = "";
  concepts.forEach(function(concept, index){
    output += concept;
    if(index < concepts.length - 1){
      output += ", ";
    }
  });
  return output;
}
```

### Theme & Variation

```js
function joinList(concepts){
  var output = "";
  concepts.forEach(function(concept, index){
    output += ", ";
    output += concept;
  })
  return output.substr(2);
}
function joinList(concepts){
  if(concepts.length === 0) return "";

  if(concepts.length === 1) return concepts[0];

  return concepts[0] + ", " + joinList(concepts.slice(1));
}
function joinList(concepts){
  if(concepts.length === 0) return "";

  function iterate(subArray, agg){
    if(subArray.length === 0) return agg;
    return iterate(subArray.slice(1), agg + ", " + subArray[0]);
  }

  return iterate(concepts.slice(1), concepts[0]);
}
function joinList(concepts){
  if(concepts.length === 0) return "";
  return concepts.reduce(function(agg, concept){
    return agg + ", " + concept;
  });
}
```