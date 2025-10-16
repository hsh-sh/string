# 💬 Методы строк в JavaScript

В JavaScript строки — это последовательности символов.  
С ними можно выполнять множество операций: получать символы, искать, заменять, обрезать, объединять и т.д.  
Ниже — подробное руководство по самым важным методам.

---

## 🔹 charAt(index)

Возвращает *символ по указанному индексу*.  
Если индекс выходит за пределы строки — возвращает пустую строку "".
```j

const str = "Hello";
console.log(str.charAt(1)); // "e"
console.log(str.charAt(10)); // ""

📘 Что делает: достаёт букву по номеру.
⚠ Индексация начинается с 0.


---

```
🔹 at(index)

```

Похож на charAt(), но поддерживает отрицательные индексы, считая с конца.

const str = "Hello";
console.log(str.at(1));   // "e"
console.log(str.at(-1));  // "o"

📘 Что делает: возвращает символ по индексу, даже если он отрицательный.
💡 Удобно, чтобы взять последний символ: str.at(-1).


---

```
🔹 toString()
```

Преобразует значение (например, число или объект) в строку.

const num = 123;
console.log(num.toString()); // "123"

📘 Что делает: превращает любой тип данных в строку.
💡 Часто используется перед объединением чисел с текстом.


---

```
🔹 concat(str1, str2, …)
```

Объединяет (склеивает) несколько строк в одну.

const str1 = "Hello";
const str2 = "World";
console.log(str1.concat(" ", str2)); // "Hello World"

📘 Что делает: соединяет строки.
💡 То же самое можно сделать с помощью +:

"Hello" + " " + "World";


---

```
🔹 trim()
```

Удаляет пробелы в начале и в конце строки.

const text = "   Hi there!   ";
console.log(text.trim()); // "Hi there!"

📘 Что делает: очищает строку от лишних пробелов.
🧹 Есть также:

trimStart() — убирает пробелы только в начале;

trimEnd() — убирает пробелы только в конце.



---

```
🔹 includes(substring)
```

Проверяет, содержится ли подстрока в строке.
Возвращает true или false.

const str = "JavaScript";
console.log(str.includes("Script")); // true
console.log(str.includes("script")); // false

📘 Что делает: ищет слово или часть текста.
⚠ Чувствителен к регистру.


---

```
🔹 indexOf(substring[, start])
```

Возвращает индекс первого вхождения подстроки.
Если не найдено — возвращает -1.

const str = "banana";
console.log(str.indexOf("a"));    // 1
console.log(str.indexOf("a", 2)); // 3

📘 Что делает: ищет слева направо.
💡 Второй аргумент задаёт, с какого места начинать поиск.


---

```
🔹 lastIndexOf(substring[, start])
```

Возвращает индекс последнего вхождения подстроки.

const str = "banana";
console.log(str.lastIndexOf("a")); // 5

📘 Что делает: ищет справа налево.
💡 Полезно, если нужно найти последнюю букву.


---

```
🔹 replace(что, наЧто)
```

Заменяет первое найденное совпадение.

const str = "apple apple";
console.log(str.replace("apple", "orange")); 
// "orange apple"

📘 Что делает: заменяет только первое совпадение.
💡 Чтобы заменить все — используй replaceAll() или регулярное выражение с /g.


---

```
🔹 replaceAll(что, наЧто)
```

Заменяет все совпадения.

const str = "apple apple apple";
console.log(str.replaceAll("apple", "orange")); 
// "orange orange orange"

📘 Что делает: заменяет каждое найденное совпадение.
✨ Поддерживается в новых версиях JavaScript (ES2021+).


---

```
🔹 substring(start, end)
```

Возвращает часть строки между индексами.
Если end не указан — берёт до конца строки.

const str = "JavaScript";
console.log(str.substring(0, 4)); // "Java"
console.log(str.substring(4));    // "Script"

📘 Что делает: вырезает часть строки.
💡 Если start > end, они поменяются местами:

str.substring(4, 0); // "Java"


---

```
🔹 slice(start, end)
```

Похож на substring(), но поддерживает отрицательные индексы.

const str = "JavaScript";
console.log(str.slice(0, 4));  // "Java"
console.log(str.slice(-6));    // "Script"

📘 Что делает: вырезает часть строки, можно с конца.
💡 Очень удобно использовать с отрицательными индексами.


---

```
🔹 split(разделитель)
```

Разделяет строку на массив подстрок по разделителю.

const fruits = "apple,banana,orange";
console.log(fruits.split(",")); 
// ["apple", "banana", "orange"]

console.log("hello".split("")); 
// ["h", "e", "l", "l", "o"]

📘 Что делает: превращает строку в массив.
💡 Если не указать разделитель, вернёт массив с одной строкой:

"hello".split(); // ["hello"]


---

🧠 Примеры в действии

let text = "Hello World";

// ⿡ Получить 1-й символ
console.log(text.charAt(0)); // "H"

// ⿢ Проверить, есть ли "World"
console.log(text.includes("World")); // true

// ⿣ Узнать индекс слова "World"
console.log(text.indexOf("World")); // 6

// ⿤ Заменить слово
console.log(text.replace("World", "Shukrona")); // "Hello Shukrona"

// ⿥ Удалить пробелы
console.log("   Hi!   ".trim()); // "Hi!"

// ⿦ Вырезать часть строки
console.log(text.slice(0, 5)); // "Hello"

// ⿧ Разделить строку по пробелу
console.log(text.split(" ")); // ["Hello", "World"]


---


✨ Итог

🧩 Эти методы помогают:

Извлекать символы (charAt, at);

Проверять и искать текст (includes, indexOf, lastIndexOf);

Заменять текст (replace, replaceAll);

Удалять лишние пробелы (trim);

Разделять и объединять строки (split, concat);

Вырезать части текста (slice, substring);

Преобразовывать значения в строки (toString).
