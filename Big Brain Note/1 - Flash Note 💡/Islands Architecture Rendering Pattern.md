# Aim to reduce the volume of JavaScript shipped through “islands” of interactivity that can be independent delivered on top of otherwise static HTML.

# Island
- static island: pure non-interactive HTML, no hydration needed
- dynamic island: A combination of HTML and scripts capable of rehydrating themselves after rendering.
- Most modern JavaScript frameworks also support [isomorphic rendering](https://en.wikipedia.org/wiki/Isomorphic_JavaScript), which allows you to use the same code to render elements on the server and client.
  
  ## to implement a scheduling approach for hydrating components.
- use `requestIdleCallback()`
- Static isomorphic rendering and scheduling of component level partial hydration can be built into a framework to support Islands architecture.
# Framework
### Marko
- To improve server rendering performance.
- Islands architecture -:> combining streaming rendering with automatic partial hydration
	- HTML and other static assets are streamed to the client as soon as they are ready. 
	- Automatic partial hydration allows interactive components to hydrate themselves.
	
### Astro 
- A static site builder that can generate lightweight static HTML pages from UI components built in other frameworks such as React, Preact, Svelte, Vue, and others
### Eleventy + Preact
