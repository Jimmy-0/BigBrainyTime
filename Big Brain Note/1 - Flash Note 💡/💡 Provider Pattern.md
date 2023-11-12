- We want to make available data to many (if not all) components in an application.
  -  We can pass data to components using `props`
	  > This might cause `prop drilling`
- We make data available to multiple components. Rather than passing that data down each layer through props, we can wrap all components in a `Provider`.
- A Provider is a higher order component provided to us by the `Context` object. We can create a Context object, using the `createContext` method that React provides for us.
- The Provider pattern is very useful for sharing global data. 
	- A common usecase for the provider pattern is sharing a theme UI state with many components.

- ![[jspat-48_jxmuyy.webm]]
- The example above shows that, it is very messy 
  >> It would be nice if we could skip all the layers that doesn't need the data.
- ![[jspat-49_ksvtl8.webm]]![[Screenshot 2023-11-12 at 14.06.02.png]]