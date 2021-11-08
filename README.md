1. Не объявляй неиспользуемые переменные.

❌ плохо:
```
let x = 0;
let y = 1; // Переменная не используется

function getX() {
    return x + 1;
}
 ```

✅ хорошо:
```
let x = 0;

function getX() {
    return x + 1;
}
```

2. Если переменная не будет переназначаться, то используй const для ее объявления.

❌ плохо:
```
var a = 1;
var b = 2;

var count = 1;
if (true) {
  count += 1;
}
 ```

✅ хорошо:
```

const a = 1;
const b = 2;

let count = 1;
if (true) {
  count += 1;
}
```

3. При использовании конструкции if .. else располагайте else на одной строке со скобкой закрывающей блок if. ​

❌ плохо:
```
if (test) {
 ​thing1();
 ​thing2();
}
else {
 ​thing3();
}
​
```

✅ хорошо:
```
if (test) {
 ​thing1();
 ​thing2();
} else {
 ​thing3();
}
```

4. Пиши каждую пару ключ свойство с новой строки.

❌ плохо:
```
const obj0 = { foo: "foo", bar: "bar", baz: "baz" };

const obj1 = {
 ​foo: "foo", bar: "bar", baz: "baz"
};

const obj2 = {
 ​foo: "foo", bar: "bar",
 ​baz: "baz"
};
```

✅ хорошо:
```
const obj1 = {
 ​foo: "foo",
 ​bar: "bar",
 ​baz: "baz"
};
```

5. Для доступа к свойствам объекта используйте точечную запись.

❌ плохо:
```
const luke = {
  jedi: true,
  age: 28,
};

const isJedi = luke['jedi'];
```

✅ хорошо:
```
const isJedi = luke.jedi;
```

6. Не объявляй функцию внутри цикла.

❌ плохо:
```
for (let i=10; i; i--) {
  (function() { return i; })();
}

while(i) {
  const a = function() { return i; };
  a();
}
```

✅ хорошо:
```
const a = function() {};

for (let i=10; i; i--) {
  a();
}
```

7. Используйте стрелочные функции для передачи коллбеков.

❌ плохо:
```
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});
```

✅ хорошо:
```
[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});
```

8. Называй функции-конструкторы с большой буквы.

❌ плохо:
```
const colleague = new person();
const friend = new person.acquaintance();
```

✅ хорошо:
```
const colleague = new Person();
const friend = new person.Acquaintance();
```

9. При смешивании операторов заключай их в скобки. Единственным исключением являются стандартные арифметические операторы: +, - и **, так как их приоритет широко понят. Рекомендуется заключать в скобки / и *, потому что их приоритет может быть неоднозначным, когда они смешаны.

Это позволит избежать ошибок. Также код станет более читабельным

❌ плохо:
```
const foo = a && b < 0 || c > 0 || d + 1 === 0;
const bar = a ** b - 5 % d;

if (a || b && c) {
  return d;
}

const bar = a + b / c * d;
```

✅ хорошо:
```
const foo = (a && b < 0) || c > 0 || (d + 1 === 0);

const bar = a ** b - (5 % d);

if (a || (b && c)) {
  return d;
}

const bar = a + (b / c) * d
```

10. В комментариях после // или /* должен быть пробел.

❌ плохо:
```
//is current tab
const active = true;

/**
 *make() returns a new element
 *based on the passed-in tag name
 */
function make(tag) {

  // ...

  return element;
}
```

✅ хорошо:
```
// is current tab
const active = true;


/**
 * make() returns a new element
 * based on the passed-in tag name
 */
function make(tag) {

  // ...

  return element;
}
```