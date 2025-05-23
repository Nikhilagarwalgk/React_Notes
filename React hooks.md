React Basics:-

Hooks allow us to "hook" into React features such as state and lifecycle methods. Hooks were added to React in version 16.8.

1. useState
   --> The React useState Hook allows us to track state in a function component. State generally refers to data or properties that need to           be tracking in an application.

   ![image](https://github.com/user-attachments/assets/abaf4bb7-8c84-4b0a-bf32-2e96cc85d52f)

   For updating state object and array:-
   How to change nested object or array?
      1. Add new data
      2. Remove old data
      3. Update old data
      4. Find and update old data
   https://react.dev/reference/react/useState#updating-objects-and-arrays-in-state
   https://react.dev/learn/updating-arrays-in-state

For Array state:- https://react.dev/learn/updating-arrays-in-state

@ What is State Lifting in React?
-->State lifting in React refers to moving state up to the closest common ancestor of two or more components that need to share or coordinate the same piece of data. This is a common pattern when child components need to:
1. Share state, or
2.Send data back up to the parent. 
   You "lift" the state up to a parent component, and pass it down via props.

   ![image](https://github.com/user-attachments/assets/11283077-2586-4bad-9171-dd289f2fff67)
   ![image](https://github.com/user-attachments/assets/f9edae53-ebbf-4ad4-b9c1-576884d78dd2)

------------------------------------------------------xxxx---------------------------------------------------------------------------

1. Where we store data in redux?
   
  --> When you use Redux in a web application: The Redux store is held in JavaScript memory, meaning:
   1. It's stored in the RAM while the app is open in the browser.(In browser memory, that global space)
   2. It disappears if the user refreshes the page or closes the tab (unless you explicitly persist it).

   ![image](https://github.com/user-attachments/assets/579c1b7c-712c-442a-bcab-9979333ae66e)

   ![image](https://github.com/user-attachments/assets/5507e738-f372-4cea-9c13-18691df71bb3)

At first in window global staorage, after we add persist, it store in local storage.

2. How much storage we have in window/browser storage?

   ---> ![image](https://github.com/user-attachments/assets/c46869e2-d2d8-4fef-84d3-228a0aea72e7)

   ![image](https://github.com/user-attachments/assets/adf2381e-8d6b-4b3c-b3bb-60f678592297)

   ![image](https://github.com/user-attachments/assets/50bbe571-1818-40bf-b118-8903b5011f78)

   ![image](https://github.com/user-attachments/assets/b3722ce9-7c71-4617-9d17-43f3bd14b711)




4. Critial CSS?
   
   ---> Critical CSS means:👉 Only load the CSS that is needed to show the part of the webpage that you first see (before scrolling).
   The basic idea behind critical CSS is to isolate the smallest set of styles needed to start rendering useful content and inline that CSS into the first HTML request. That way, everything the page needs to start rendering is in the first request, making your site as fast as possible.This is especially important if you are focused on the mobile web, where high latency and slow bandwidth are common.

   ( High Latency means more time between the request and the response. )
   These techniques make it possible to render a page under one second, even under bad network conditions.

   Note:- Keep it under 14KB.
When inlining your CSS into the HTML, aim for your total size to be under 14KB. This guideline is based on fitting everything in the first network TCP roundtrip.


6. Atomic CSS?

--> Atomic CSS is a CSS architecture and methodology that focuses on using small, single-purpose utility classes to style elements. Each class typically corresponds to one specific style rule, like margin, padding, text color, or display properties. This approach contrasts with traditional CSS, which often uses longer, descriptive class names tied to components or sections.

🔹 Key Concepts of Atomic CSS:- 

   - Utility-first: Classes do one thing only (e.g., mt-4 = margin-top: 1rem).
   - Composable: Combine multiple atomic classes to style an element.
   - Low specificity: Since there's less nesting or overriding, conflicts are minimized.
   - Avoids custom CSS: Most styling is done directly in HTML using pre-defined classes.


![image](https://github.com/user-attachments/assets/bcd9da45-53b5-4534-bcb3-20223d437b94)

![image](https://github.com/user-attachments/assets/ee1b2fce-e34a-4a93-8560-346bcfd116e9)

** Popular Atomic CSS Frameworks:- 
 
   1.Tailwind CSS – The most widely used utility-first CSS framework.

   2. Windi CSS – Tailwind-compatible, with performance optimizations.

   3. Tachyons – One of the earliest atomic CSS libraries.

   4. Basscss – Lightweight and responsive atomic CSS toolkit.

   ![image](https://github.com/user-attachments/assets/e4f578a4-8d9e-4949-8a41-a9738a8e8c9d)




7. Critical Rendering Path (CRP)?

   ---> Refer for more details https://developer.mozilla.org/en-US/docs/Web/Performance/Guides/Critical_rendering_path.
   The Critical Rendering Path (CRP) is the sequence of steps the browser takes to convert your HTML, CSS, and JavaScript into pixels on     the screen.It affects how fast your webpage visually loads and becomes usable. while the data is downloaded from web, In parsing, first, it converts bytes to characters & then into tokens & then into nodes & then finally into the DOM tree. 

   ![image](https://github.com/user-attachments/assets/e58f5e7b-f6a2-4f83-be21-6374a2a80014)

   ![image](https://github.com/user-attachments/assets/dc8e6a63-4694-41f8-ac5a-df5cae817886)

   📌 Why is this important?
   
 - Until CSS and JS are fully loaded and processed, the page cannot be shown.
 - Large or slow-loading files will block rendering, causing slow load times.
 - Optimizing CRP makes your site feel fast and responsive.

   🧰 Key Concepts Related to CRP:-
   
   ✅ 1. Render-Blocking Resources.
   
      - Files like CSS or synchronous JS that stop the page from showing until they’re done loading.
      - Fix: Minimize, defer, or async-load them.
        
   ✅ 2. Critical CSS.
   
      - The minimum CSS needed to render the visible part of the page.
      - Inline it to speed up the first paint.
   
   ✅ 3. First Paint / First Contentful Paint (FCP)
   
      - Time when something first appears on the screen (e.g., text or image).

   ✅ 4. Largest Contentful Paint (LCP)
   
      - Time when the largest visible item (like a banner image or heading) is fully loaded.
  
        NOTE:- https://web.dev/learn/performance/understanding-the-critical-path




         
   
9. Tree Shaking?
10. DOM and CSSOM (CSS Object Model) ? -->  DOM + CSSOM → Render Tree

   --> The Document Object Model (DOM) connects web pages to scripts or programming languages by representing the structure of a document—such as the HTML representing a web page—in memory. The DOM represents a document with a logical tree. Each branch of the tree ends in a node, and each node contains objects. DOM methods allow programmatic access to the tree. With them, you can change the document's structure, style, or content.

    --> ![image](https://github.com/user-attachments/assets/29386767-2596-43f0-aa2d-58931d321a7d)

   --> The CSS Object Model is a set of APIs allowing the manipulation of CSS from JavaScript. It is much like the DOM, but for the CSS rather than the HTML. It allows users to read and modify CSS style dynamically.


11. what is defer and async attributes in JS?

--> In JavaScript, the defer attribute is used with the <script> tag in HTML. It tells the browser to download the script in the background while continuing to parse the HTML, and then execute the script only after the HTML document has been fully parsed.

![image](https://github.com/user-attachments/assets/70bc0cdb-606b-4022-9d52-c2786ca539e6)

![image](https://github.com/user-attachments/assets/c7dff9d8-eca3-431f-9a80-e50970c5f70c)

---> In React, you typically don’t need to use defer manually because:

   1. React applications are usually built with bundlers like Webpack, Vite, or Create React App, which automatically optimize the script loading.
      
   2. The final bundled JavaScript file is usually already injected with the defer attribute by tools like index.html generated by CRA or Vite.

---> The async attribute is used in JavaScript to load and execute external scripts asynchronously, meaning the browser can download and execute the script as soon as it’s ready, without waiting for the HTML parsing to finish.

![image](https://github.com/user-attachments/assets/c507d898-612f-48ec-888b-b276cc585e0e)

![image](https://github.com/user-attachments/assets/ad1f7a42-a203-4c0f-92e6-ae7eb0952bd1)

![image](https://github.com/user-attachments/assets/deb9b803-03ca-4000-bb03-7b215ac63336)

📌 When to Use async
   Use async when:

   1. The script is independent and doesn’t rely on the DOM or other scripts.Example: analytics, ads, or trackers.

🚫 When not to use async
   Avoid async if:

   1. Your script depends on DOM elements being available.

   2. The script depends on another script's output.

📜 What Happens by Default with <script src="...">

![image](https://github.com/user-attachments/assets/5601fac6-b188-47ad-b571-df7db9f1af3a)

![image](https://github.com/user-attachments/assets/04319cbe-c82a-4579-9e20-cc1124f118cb)

NOTE:- there are more such attribute as module and async module.

![image](https://github.com/user-attachments/assets/55f91f82-e9ac-4044-a547-95866adcce81)

12. what is HTML parsing? JS parsing?

--> HTML parsing is the process the browser uses to read and understand the HTML code, converting it into a structured format the browser can display — called the DOM (Document Object Model).

🔄 Parsing Process Step-by-Step:-

1. HTML Download Begins. The browser starts reading the HTML file from top to bottom.

2. Tokenization - The HTML text is broken into tokens (like tags, attributes, and content).

3.Tree Construction - These tokens are used to build the DOM Tree, which is a live representation of the page structure in memory.

4. Handling Other Resources While parsing HTML, the browser might:

 - Request CSS, images, and fonts

`- Encounter JavaScript and pause parsing (unless defer or async is used)

5.Render - Once the DOM and CSSOM (for styles) are ready, the browser renders the page on the screen

   ![image](https://github.com/user-attachments/assets/8bd424fc-4120-447a-933b-28898addc3cd)


2.Optmization in react app?-> lazy load amd more
why should not use MUI? How to optimize?
1. how should be the folder structure of app?
Design Pattern?
3. Pasing data from child to parrent
button in parent component, when clicks call function in child component. Data to be shown in parent component?
4. what is Visual Formatting Model, it happens during layout formation in CRP?

SEACRH for the photos of question by Prabhat?

@ what is different btw utility function Vs hooks?
@ How useEffect work behind the seen? make using js?
@ Web hooks?
@ Difference web hook and web socket?
@ Difference between redux and context api in term of memory and update?



   

