**Задание 1 – Создать объект counter всеми возможными способами**

`const counter = {
name: 1,
name2: 2,
}
const counter2 = new Object()
const counter3 = Object.create()
const counter4 = Object.assign({}, counter)`

`function Counter (value, value2) { 
this.name = value,
this.name2 =  value2
}`

`const counter5 = new Counter (value, value2)`

---
**Задание 2 – Скопировать объект counter всеми возможными способами**

`const counterCopy = Object.assign({}, counter)`

`const counterCopy2 = {}
for (let key in counter) { counterCopy2[key] = counter[key]; }`

`const counterCopy3 = {...counter}`

`const counterCopy4 = JSON.parse(JSON.stringify(counter))`

---
**Задание 3 – Создать функцию makeCounter всеми описанными и возможными способами**

`function makeCounter () {
}`

`let makeCounter2 = function () {
} `

`let makeCounter3 = () => {
}`

`let makeCounter4 = function counter () {  
}`

---
**Бонус Задание 1 – Написать функцию глубокого сравнения двух объектов:**

`const obj1 = { 
here: { 
  is: "on", 
  other: "3" }, 
object: "Y" };`

`const obj2 = { 
here: { 
  is: "on", 
  other: "2" }, 
object: "Y" };`

`const deepEqual = (obj1, obj2) => {   
if (obj1 === null || obj2 === null || typeof obj1 !== 'object' || typeof obj2 !== 'object') { return false }   
let keysObj1 = Object.keys(obj1);   
let keysObj2 = Object.keys(obj2);   
  if (keysObj1.length !== keysObj2.length) { return false }   
  for (let i = 0; i < keysObj1.length; i++) {   
        if (keysObj2.includes(keysObj2[i]) === false) { return false }   
        if (typeof obj1[keysObj1[i]] === "object") { return deepEqual(obj1[keysObj1[i]], obj2[keysObj1[i]]) }  
        if (obj1[keysObj1[i]] !== obj2[keysObj2[i]]) { return false }   
            }   
             return true   
                 };`

---
**Бонус Задание 2 – Развернуть строку в обратном направлении при помощи методов массивов:**

`function reverseStr(str) {
  return str.split("").reverse().join("")
}`
