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




4. Crital Css, Atomic Css
2.Optmization in react app?-> lazy load amd more
why should not use MUI? How to optimize?
1. how should be the folder structure of app?
Design Pattern?
3. Pasing data from child to parrent
button in parent component, when clicks call function in child component. Data to be shown in parent component?

SEACRH for the photos of question by Prabhat?



   

