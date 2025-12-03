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




   










