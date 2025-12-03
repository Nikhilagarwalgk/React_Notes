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


