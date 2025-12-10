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

For map:-
<img width="1366" height="461" alt="image" src="https://github.com/user-attachments/assets/07791aaf-626e-4abb-8238-2bc4e6833374" />

