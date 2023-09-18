```
1) Почему массивы в JS являются "неправильными" и совмещают в себе несколько структур данных? Какие ?
Массив совмещает в себе такие структуры данных, как стеки и очереди. 


2) Привязать контекст объекта к функции logger

function logger() {
    console.log(`I output only external context: ${this.item}`);
}

const obj = { item: "some value" };

logger.call(obj)

logger.apply(obj)

const loggerObj = logger.bind(obj)
loggerObj()


Бонус задание: Реализовать bind()

function logger() {
    console.log(`I output only external context: ${this.item}`);
}

const obj = { item: "some value" };

Function.prototype.myBind = function (obj, ...args1) {
  let fn = this;
  return function (...args2) {
    fn.apply(obj, ...args1.concat(args2));
  };
};

const loggerObj = logger.myBind(obj)
loggerObj()