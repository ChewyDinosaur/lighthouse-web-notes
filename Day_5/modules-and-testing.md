# Week 1 Day 5 - Modules and Testing
REPO: https://github.com/NimaBoscarino/modules-testing-notes

I recommend reading into [Sindre Sorhus](https://sindresorhus.com/), the reigning monarch of Open Source module development.

Useful links:
1. [npm - the package registry](https://www.npmjs.com)  
2. [Sindre Sorhus - Why make modules??](https://github.com/sindresorhus/ama/issues/10#issuecomment-117766328)
3. [Sindre Sorhus AMA](https://blog.sindresorhus.com/answering-anything-678ce5623798)

Let's start with a little bit of vocab...

API: Application Programming Interface
- how programs talk to each other
- allows stuff to talk to other stuff
    - stuff: people maybe?
    - stuff: programs maybe?
- allows you to talk to an already existing program and implement that stuff into YOUR code

## Modularization
The pattern with modularization will be...

1. Do a bunch of work somewhere
2. Come up with a nice "API"
    - a nice interface to use the work
3. Import that API into my own stuff
    - "require"
4. Use the API!

This facilitates *cleanliness* and *reusability*.

Generally we want to make modules that are concise and to-the-point! Check out Sindre Sorhus' posts (linked at the top!) to read about their philosophy on making tons of teeny modules.

## Creating and using modules

In Node, every file is a *module*. That means that every file (or script) has access to these things:
- module
    - a big object!
- exports
    - one of the properties in module. A.k.a. `module.exports`
- require
    - a function that lets us import what *other* modules *export*

The format for this is...

**One thing exports**

``` js
var usefulData = 12 // wow super useful!
function bestFunction() {
    return "Wow!"
}

module.exports = {
    usefulData: usefulData,
    bestFunction: bestFunction
}
```

**Another things requires!**
``` js
var importedThings = require('./path/to/file')

console.log(importedThings.usefulData) // 12
console.log(importedThings.bestFunction()) // "Wow!"
```

See the `hiphop` folder for some examples of exporting and requiring.

## Function Contract
As we use other people's code, we have to agree on certain things. For example, what is the return value of the function? What are the inputs? What are the side effects of the function, if any? Always read the documentation for the code that you import to make sure that you're using the API correctly.

# Cyclical Require
Someone asked a neat question about having two modules requiring each other, so I put together a little demo of it. It works, it's just a little tricky to understand what's going on. I recommend playing around with `aJob.js` and `experience.js` in the `cyclicalRequire` folder. 


# NPM: The Node Package Manager
NPM is both the online registry of modules, and the command line tool that lets us manage the packages used by our projects (a.k.a. dependencies!).

Useful commands include:
- `npm init`
    - creates a package.json file where we list out the dependencies
- `npm install <packagename>`
    - adds the package (and it's dependencies to our node_modules folder, plus puts the package as a dependency in our package.json)
- `npm uninstall <packagename>`
    - does the opposite of `npm install <thing>`

### HEADS UP!
To install **EVERYTHING** that is listed in a package.json file, we can simply run `npm install`.

When we install a package (module), we can use it in our project by going: `var thing = require('thingName')`. Note that we don't need to provide a path!

## Testing

We took a look at unit testing with Mocha. Mocha is a test runner that we can install as a **dev dependency**. We write test descriptions and assertions, and then use Mocha to check to see if all our tests pass! Check out the `hiphop` folder for examples of using Mocha for writing and using tests.

To run the demos make sure that you run `npm install` to install all of the required modules!

Enjoy! - Nima Boscarino