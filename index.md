Starting Raect Notes

@ What is React Fiber?

--> React Fiber was introduced in React 16, which was released in September 2017.
Key Details:-

React Fiber is a complete rewrite of React's core reconciliation algorithm (the process that determines what changes need to be made to the
DOM).
The main goals of Fiber were:-

1. Incremental rendering - the ability to split rendering work into chunks and spread it out over multiple frames
2. Ability to pause, abort, or reuse work as new updates come in
3. Ability to assign priority to different types of updates
4. New concurrency primitives (which later evolved into Concurrent Mode features in React 18)

Before Fiber, React used a "stack reconciler" that was synchronous and couldn't be interrupted once it started. This could cause performance
issues with large component trees.

@ Here, 1. What is Fiber?

--> A "fiber" is a JavaScript object that represents a unit of work. Each fiber corresponds to a React element and contains information about
the component, its input (props), and its output.

2. Key Architecture Changes:-

Before (Stack Reconciler)   |	After (Fiber)
Synchronous, blocking       |	Asynchronous, can be interrupted
All-or-nothing updates	    | Incremental rendering
No priority system	        | Priority-based updates
Single call stack           |	Linked list of fibers

3. Important Concepts?

--> Two Phases of Rendering
1. Render/Reconciliation Phase (interruptible): React builds the fiber tree, determines changes. No side effects here.
2. Commit Phase (not interruptible): React applies changes to the DOM. Side effects run here.

4. Double Buffering?

React maintains two fiber trees:
1. Current tree: What's currently rendered on screen
2. Work-in-progress tree: Being built during updates
Once complete, they swap (similar to double buffering in graphics).

@5. Priority Levels? 

--> Fiber introduced update priorities:
eg:- Immediate → User blocking → Normal → Low → Idle
For example, a user typing in an input gets higher priority than a data fetch updating a list.

<img width="823" height="263" alt="image" src="https://github.com/user-attachments/assets/76601c91-5e76-43cc-b749-b7bb1bacd443" />

@. Why It Matters?

-->Better perceived performance: High-priority updates (like animations, user input) aren't blocked by low-priority work
Smoother UI: Long renders can be broken up across frames (targeting 60fps)
Foundation for modern features: Suspense, Concurrent Mode, useTransition, useDeferredValue all build on Fiber

@. What is ForwardRef?
-->

<img width="876" height="145" alt="image" src="https://github.com/user-attachments/assets/1a72567a-7d8d-4285-bff5-6fdb7db9a755" />

<img width="901" height="411" alt="image" src="https://github.com/user-attachments/assets/a5d40bc4-38ba-4094-a528-9c91d2eea431" />

@ What is useImperativeHandle ? 

--> useImperativeHandle is used with forwardRef to customize what the parent can access via the ref. Instead of exposing the entire DOM element, you can expose only specific methods.

@Why is it needed?

1. Control what the parent can do with the ref
2. Expose custom methods instead of raw DOM access
3. Encapsulation - hide internal implementation details

   <img width="868" height="352" alt="image" src="https://github.com/user-attachments/assets/05afe13e-5fda-4007-84a3-1c0ff622313f" />

   <img width="884" height="248" alt="image" src="https://github.com/user-attachments/assets/c8f236f3-b445-4afb-b5c3-fe75fb2c5e01" />

   <img width="885" height="291" alt="image" src="https://github.com/user-attachments/assets/07375359-0e5b-464a-9e1a-4a3965dbb16f" />

@ What is useLayoutEffect?

--> useLayoutEffect is similar to useEffect, but it fires synchronously after all DOM mutations and before the browser paints the screen.
When to use:

1. When you need to measure DOM elements (width, height, position)
2. When you need to make visual changes that must happen before the user sees the screen
3. Preventing visual flickering

   <img width="867" height="461" alt="image" src="https://github.com/user-attachments/assets/1c5cc0cd-86fd-4958-a36b-b04943de9334" />

   <img width="937" height="471" alt="image" src="https://github.com/user-attachments/assets/d6247c9a-2f4b-4135-ada1-1879a179d857" />

@ What is useTransition hook?

--> useTransition is used to mark state updates as non-urgent/low priority, allowing the UI to remain responsive during expensive updates.
When to use:

1. Large list filtering/searching
2. Tab switching with heavy content
3. Any state update that causes slow re-renders

   <img width="844" height="413" alt="image" src="https://github.com/user-attachments/assets/7162efb1-fbf8-4c67-8d04-79eac4e7bfed" />

   <img width="882" height="265" alt="image" src="https://github.com/user-attachments/assets/668109c5-7d0d-4b54-8b6f-26a6a644793b" />

@ what is Code Splitting in React?

-->Code splitting is a technique to split your JavaScript bundle into smaller chunks that load on demand, improving initial load time

<img width="912" height="348" alt="image" src="https://github.com/user-attachments/assets/5d6ff0d2-96dc-4dc1-80a0-73d3a93b65dc" />

<img width="893" height="449" alt="image" src="https://github.com/user-attachments/assets/d20bf184-5ea2-43b1-acfe-54d6ff46e9ae" />

@ What is Suspense?

--> Suspense lets you show a fallback UI while waiting for something to load (lazy components, data fetching).

<img width="894" height="246" alt="image" src="https://github.com/user-attachments/assets/9f013e2e-1837-4386-90af-b13a946e918b" />

<img width="882" height="375" alt="image" src="https://github.com/user-attachments/assets/64713bc9-cc8e-4f79-8786-9c895cd7e20b" />

<img width="853" height="458" alt="image" src="https://github.com/user-attachments/assets/c842062a-ac60-40fc-9b0c-76b9a48a48ed" />

@ what is Error Boundary?

--> Error Boundaries catch JavaScript errors in child components and display a fallback UI instead of crashing the app.

<img width="876" height="463" alt="image" src="https://github.com/user-attachments/assets/29aeec56-cada-48b8-b24f-604c44334c09" />

<img width="910" height="416" alt="image" src="https://github.com/user-attachments/assets/141a45be-45de-4cf3-b364-7fe4784fa233" />

<img width="878" height="234" alt="image" src="https://github.com/user-attachments/assets/ca52cf74-ef0d-4702-a72a-60636a7ed6a5" />

@ If we use Error boundary + suspense?

<img width="939" height="294" alt="image" src="https://github.com/user-attachments/assets/63eaef22-35ad-48a6-ad5c-2c67006f7425" />

@ Difference between them?

<img width="899" height="301" alt="image" src="https://github.com/user-attachments/assets/095c6a9e-669c-4e49-a5ec-57451a625c0e" />

@What kind of error does Error Boundary catch and what not?

--> <img width="899" height="404" alt="image" src="https://github.com/user-attachments/assets/9f75df60-973a-48e8-aefe-d8d57395e59f" />

<img width="883" height="465" alt="image" src="https://github.com/user-attachments/assets/7bb38cda-825c-4352-af49-89ebc39c65c6" />

<img width="911" height="336" alt="image" src="https://github.com/user-attachments/assets/c108a882-4ca7-4a85-a73a-02d485b620ce" />

@ To catch those error uncaught by Error Boundaries is catched by Try and catch.
<img width="864" height="376" alt="image" src="https://github.com/user-attachments/assets/6dbc7e68-501c-4861-8b94-08b58de4cec9" />

@ To handle different kinds of error that Error boundary doesn't catch is?
-->
<img width="907" height="389" alt="image" src="https://github.com/user-attachments/assets/01b2d963-27fd-440f-976c-5215d6d1cdc4" />

<img width="904" height="310" alt="image" src="https://github.com/user-attachments/assets/4f9764c7-a46e-4c0a-9e75-6a52460476db" />

@ What is Tree Shaking in JavaScript/React?

--> Tree shaking is a dead code elimination technique that removes unused code from your final bundle, reducing its size.

<img width="889" height="297" alt="image" src="https://github.com/user-attachments/assets/dde6152a-1688-4db4-8edd-01c732d7060e" />

@ Requirements for Tree Shaking

--> <img width="861" height="455" alt="image" src="https://github.com/user-attachments/assets/f10831c2-5ce7-4f1b-9f6f-eda693312747" />

<img width="875" height="246" alt="image" src="https://github.com/user-attachments/assets/64f8900f-aa76-43fd-8651-0a5518dc044a" />

<img width="873" height="332" alt="image" src="https://github.com/user-attachments/assets/77e00e73-b7e1-4b83-90da-2ff6a3367dbb" />

NOTE:- Tree shaking happens automatically in production builds with modern bundlers (Webpack, Rollup, Vite) - you just need to write your code in a tree-shakeable way!

@ What is Concurrent Rendering in React?

--> Concurrent Rendering is a feature introduced in React 18 that allows React to interrupt, pause, and resume rendering to keep the UI responsive.

<img width="915" height="347" alt="image" src="https://github.com/user-attachments/assets/17cc9020-86f2-4843-ad60-0dcc44bc4153" />

<img width="841" height="468" alt="image" src="https://github.com/user-attachments/assets/d283e5d8-3263-4eb2-9253-8259b9e306a7" />

So, here it uses useTransition hook for non-urgent update.  

@ What is useDeferredValue in React?

--> useDeferredValue is a React 18 hook that lets you defer updating a part of the UI to keep it responsive. It creates a "deferred" version of a value that lags behind the original.

Basic Syntax:-
const deferredValue = useDeferredValue(value);
 - Input: Any value (string, number, object, etc.)
 - Output: A deferred copy that may lag behind during updates

<img width="840" height="383" alt="image" src="https://github.com/user-attachments/assets/112bcc11-f9f4-4860-a70d-e9b5d6a9c999" />




















   
   



   










