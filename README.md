## Scope, hoisting and compartmentalization

### Answer the following:
In you own words, explain the concepts of scope, hoisting, compartmentalization.

A: Scope is the degree to which a variable or function can be called and whether it is local or global. Hoisting is when javascript automatically reorders variable declarations to the top and variable calls below them. Compartmentalization is where variable declarations and calls are placed within the document and can have local variables 'compartmentalized' within functions.

### Provide examples for all three, below:

#### Scope:

(function(){
  "use strict";

  var x = "I'm a local variable";
  //console.log(y)

  function scopeThis(){
    var y = "I'm a global variable";
    console.log(x);
  }
  scopeThis();
})();

#### Hoisting:

(function(){
  "use strict";

  function warmUp() {
    console.log(x);
    console.log(foo());

    var x = "variable hosting!";

    function foo() {
      return "function hoisting";
    }
  }
  warmUp();
})();

#### Compartmentalization:

(function() {
  "use strict";
  var multiply = 2 * 8;

  function duplicate() {
    let multiply = 2 * 10;
  };

  duplicate();

  console.log( "multiply", multiply );
  console.assert( multiply == 16, "Test failed. How can we isolate duplication()" );
})();
