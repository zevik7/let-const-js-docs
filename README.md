
![enter image description here](http://thaunguyen.com/blog/wp-content/uploads/2018/02/let.jpeg)
# Let, const keyword in ES6
## What is it?
- New features came out with ES6
- Can be used for variables declaration like var keyword
## What is difference between let, var, const keyword?
## Scope
### 1. Var
- `var` declarations are globally scope or function scope
	```
	{
		var globalScope = 'Global scope';
	}
	console.log(globalScope); // Log 'Global scope'
	
	function VarFunc() {
	  var funcScope = "Function scope";
	  console.log(funcScope) // Log 'Function scope'
	}
	
	console.log(funcScope); // Uncaught ReferenceError: funcScope is not defined
	```
- `var` can be re-declared and updated
	```
	var varVariable = 'Hello'
	var varVariable = 'Hi'
	console.log(varVariable) // Log 'Hi'
	```
- Problem with `var`
	```
	   var test = "no problem";
	    if (true) {
	        var test = "there is a problem"; 
	    }
	    
	    console.log(test) // Log "there is a problem"
	```

### 2. Let
- `let`declarations are block scope. A block is a chunk of code bounded by {}.
	```
	if (true) {
	  var letScope = 1;
	  {
		  console.log(letScope)
		  var letScope = 2;
	  }
	}

	console.log(letScope); // Uncaught ReferenceError: letScope is not defined
	```
- `let` can be updated, but you cannot re-declare it
	```
	let letVariable = 'Hello'
	let letVariable = 'Hi'
	// Uncaught SyntaxError: Identifier 'letVariable' has already been declared"
	```
### 3. Const
 - `const` declarations are block scope like `let` 
 - `const` cannot be updated or re-declared it
	 ```
	 const constVariable = 1
	 const constVariable = 2
	 // Uncaught SyntaxError: Identifier 'constVariable' has already been declared"
	 ```
  - `const` must be initialized during declaration
	```
	const a
	// Uncaught SyntaxError: Missing initializer in const declaration
	```
## Hosting
- Variables and function declarations are moved to the top of their scope before execution.
- `var`, `let`, `const` are hoisted
### 1. Var
- Can be used before initialized
- Default value is `undefined`
	```
	console.log(varHoisted) // Log undefined
	var varHoisted
	```
### 2.  Let, const
- Unlike `var`, the `let`, `const` keyword is not initialized, you will get a error if you try to use `let`, `const` variable before declaration
	```
	console.log(letHoisted) // Uncaught ReferenceError: letHoisted is not defined
	let Hoisted = 123
	```


## A comparison table
![Var, Let and Const. No doubt, one of the more basic… | by Rick Glascock |  Medium](https://miro.medium.com/max/1400/1*yj0O5G2RRrYK_d9qkEqQQg.png)
Image from: miro.medium.com

## Reference document:
- Freecodecamp.org
- Geeksforgeeks.org
- Mozilla.org
