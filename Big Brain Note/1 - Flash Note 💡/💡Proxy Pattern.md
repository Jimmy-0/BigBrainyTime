- Determine the behavior whenever we're interacting with the object.
```js
const tempProxy = new Proxy(person, {
	get: (obj, prop) => { 
		console.log(`The value of ${prop} is ${obj[prop]}`); 
	}, 
	set: (obj, prop, value) => { 
		if (prop === "age" && typeof value !== "number"){
			console.log(`Please enter a valid number`)
		}
		console.log(`Changed ${prop} from ${obj[prop]} to ${value}`); 
		obj[prop] = value;
	},
});

```
- In the proxy handler, we can define specific behavior for interaction.
> `get` : access a property , will return the value that you trying to get
> `set` : modify a property
- A proxy can be useful to add **validation**.
- JavaScript provides a built-in object called `Reflect`, which makes it easier for us to manipulate the target object when working with proxies.
	- The methods on the `Reflect` object have the same name as the methods on the `handler` object.



 ```js
const tempProxy = new Proxy(person, {
	get: (obj, prop) => { 
		console.log(`The value of ${prop} is ${Reflect.get(obj,prop)}`); 
	}, 
	set: (obj, prop, value) => { 
		if (prop === "age" && typeof value !== "number"){
			console.log(`Please enter a valid number`)
		}
		console.log(`Changed ${prop} from ${obj[prop]} to ${value}`); 
		Reflect.set(obj,prop,value);
	},
});

```

## Tradeoffs
Proxies are a powerful way to add control over the behavior of an object. 

A proxy can have various use-cases: validation, formatting, notifications, or debugging.

Overusing the `Proxy` object or performing heavy operations on each `handler` method invocation can easily affect the performance of your application negatively.
