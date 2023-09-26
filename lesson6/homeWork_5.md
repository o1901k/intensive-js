```
1)
let promiseTwo = new Promise((resolve, reject) => {
   resolve("a");
});

promiseTwo
.then((res) => {
   return res + "b"; // “ab”
})
.then((res) => {
   return res + "с"; // “abc”
})
.finally((res) => {
   return res + "!!!!!!!"; // ничего не принимает и не возвращает
})
.catch((res) => {
   return res + "d"; // не выполнится (т.к. resolve)
})
.then((res) => {
   console.log(res); // “abc”
});

2)
function doSmth() {
   return Promise.resolve("123");
}

doSmth()
.then(function (a) {
   console.log("1", a); // “1”, “123”
   return a;
})
.then(function (b) {
   console.log("2", b); // “2”, “123”
   return Promise.reject("321");
})
.catch(function (err) {
   console.log("3", err); // “3”, “321”
})
.then(function (c) {
   console.log("4", c);  // “4”, undefined
return c;
});

3) Напишите функцию, которая будет проходить через массив целых чисел и выводить индекс каждого элемента с задержкой в 3 секунды.
Входные данные: [10, 12, 15, 21]

let array = [10, 12, 15, 21];
for (let i = 0; i < array.length; i++) {
  setTimeout(function() {
    console.log(`The index of the number ${array[i]} is ` + i);
  }, 3000);
}


4) Прочитать про Top Level Await (можно ли использовать await вне функции async)
Глобальный await может использоваться за пределами асинхронной функции. Он превращении модули в подобие асинхронных функций. Модули, которые импортируют ресурсы, запускают выполнение кода только после получения ресурсов и их подготовки к использованию.

БОНУС ЗАДАНИЕ 
/* Необходимо реализовать функцию fetchUrl, которая будет использоваться следующим образом.
Внутри fetchUrl можно использовать условный метод fetch, который просто возвращает
Promise с содержимым страницы или вызывает reject */
fetchUrl('https://google/com&#39;)
.then(...)
.catch(...) // сatch должен сработать только после 5 неудачных попыток
получить содержимое страницы внутри fetchUrl

let numberErr = 1;

function fetchUrl (url) {
return Promise.resolve()
  .then(() => fetch(url))
  .catch(() => {
    if (numberErr < 6) {
 //console.log(numberErr);
    numberErr += 1;
    fetchUrl(url)} 
else {
//console.log('Fetch failed 5 times')
Promis.reject("Fetch failed 5 times")}
  });
}
fetchUrl("https://google/com&#39")
