@ Polifill of filter, deep copy & shallow copy?
@ Filter :-
-->// Online Javascript Editor for free
// Write, Edit and Run your Javascript code using JS Online Compiler


const users = [
  { name: 'Alice', age: 15 },
  { name: 'Bob', age: 19 },
  { name: 'Charlie', age: 25 },
  { name: 'David', age: 30 },
  { name: 'Eve', age: 35 },
  { name: 'Frank', age: 40 } ]
console.log(customFilter(users, item=>item.age > 20) === users.filter(item=>item.age>20))

function customFilter(data, condition){
let result = []
for(let i=0; i< data.length; i++){
// console.log("qwert", condition(data[i],i, data))
	if(condition(data[i],i, data)){
		result.push(data[i])
	}
}
	return result;
}

<img width="1366" height="538" alt="image" src="https://github.com/user-attachments/assets/dd8f2c6e-91a9-4334-b6bb-913ce272e16e" />

1. For map:-
<img width="1366" height="461" alt="image" src="https://github.com/user-attachments/assets/07791aaf-626e-4abb-8238-2bc4e6833374" />
<img width="812" height="512" alt="image" src="https://github.com/user-attachments/assets/e0da0c02-2e58-4005-8ba5-442384d0f886" />


2. For Filter:-
<img width="1366" height="543" alt="image" src="https://github.com/user-attachments/assets/67fbaf98-b313-45f9-ab08-d6c82ac8bc9b" />
<img width="824" height="493" alt="image" src="https://github.com/user-attachments/assets/0a0430a8-4359-4a52-97e9-50bf9e902c5b" />

3. For Reducer:-
See from a video lecture.
We can anything as argument as callback or condition.

@React Polifill:-
1. useState:-
   
   <img width="818" height="507" alt="image" src="https://github.com/user-attachments/assets/136fb0be-d584-4682-8d81-37a512658775" />
   <img width="843" height="458" alt="image" src="https://github.com/user-attachments/assets/88e36a4a-8c8f-432d-9d0d-a7e384c53978" />



@ Currying Polifill:-

<img width="1366" height="537" alt="image" src="https://github.com/user-attachments/assets/d98462e7-9e0d-4e3b-9cff-e727dd36d161" />

@ Closure Polifill
@ Promises and its attributes.
@. All Status code of API:
400
401
402
403
etc
5. Two-way Binding in Angular or js
6. Access token, refresh-token, expire time
7. 

@ Show second highest count character in a sentence

@ SHow button add, start, reset

on add, add a bar in row
on start, start filling it with green color
 and at one time only three bars should be filling the bar
one bar should take 2 sec to fill


@ What Client side Rendering (CSR), Server side rendering (SSR), Static side rendering ( SSR), React Server component (RSR)?

-->
<img width="823" height="405" alt="image" src="https://github.com/user-attachments/assets/96377e21-c9de-48c9-9560-feae0534b006" />
<img width="771" height="248" alt="image" src="https://github.com/user-attachments/assets/810dcefd-f2f5-4070-af83-43e201d2722c" />

--> Server side rendering:

<img width="884" height="414" alt="image" src="https://github.com/user-attachments/assets/11f127d2-0654-4645-9ca1-192e5e7438a0" />
<img width="888" height="305" alt="image" src="https://github.com/user-attachments/assets/80e3483b-c87a-43f6-b085-cc0604a520a9" />
<img width="682" height="322" alt="image" src="https://github.com/user-attachments/assets/cde57717-9fa2-4575-82b7-5e9f3d9d14cd" />
<img width="890" height="474" alt="image" src="https://github.com/user-attachments/assets/3752a3e1-4f03-4925-aa6d-2815e1c40e47" />
<img width="739" height="258" alt="image" src="https://github.com/user-attachments/assets/011a8c5b-d50c-433c-b934-f5aaa64fe6f0" />

Here, Concept of Hydration comes into picture.

<img width="882" height="413" alt="image" src="https://github.com/user-attachments/assets/fe2ce23c-691a-4c0c-a21a-55b00c10ffd6" />
<img width="854" height="295" alt="image" src="https://github.com/user-attachments/assets/27a8df8d-9e31-4795-9be8-f79b52978de1" />
<img width="889" height="517" alt="image" src="https://github.com/user-attachments/assets/cd88ec11-cab1-45bf-9482-97ccaca9b5ab" />





@ How to find web vital for a production app? what to do achieve them?
@ object declared as const can be edited
@ React hook form and Formic, controlled & uncontrolled components
@ how virtual DOM compared with Real DOM?
@ Code spiltting
@ How handle authentication react app, eg- login
@ what side-efect in react, how to handle it?
@ useState and useReducer? in detail


