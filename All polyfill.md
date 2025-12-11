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



@ Currying Polifill
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

@ How to iterate through a number in react?



