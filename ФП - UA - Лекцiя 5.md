20230930202918      #учу/ФП  
___ 
- "Функцiональне програмування" - "Функциональное программирование" (ФП) 
- [[ФП - Лекция 5]]
- -->  [[ФП - UA - Лекцiя 6]]
- <--  [[ФП - UA - Лекцiя 4]]
___ 
## Тема: Haskell - лінива установка 
### "Лінива установка" Haskell - 1 
- Haskell-on-line-інтерпретатор - https://replit.com/languages/haskell 
	- Haskell online editor, IDE, compiler, interpreter, і REPL 
	- Code, collaborate, compile, run, share, and deploy Haskell і більше online з вашого браузера 
	- Кодувати, співпрацювати, компілювати, запускати, ділитися та розгорнути Haskell та багато іншого онлайн з вашого браузера

	```haskell
	main = putStrLn (c) 
	a = "kurly"
	b = " - murly !!!"
	-- c = a + b
	```

### Біглий повтор 
- Незалежність від порядку

```Haskell
main = add 40 2  -- вызов
add x y = x + y   -- определение
```

- Не можна змінювати (немає змінних)

```Haskell
z = 1          -- ок
z = 2          -- ошибка
q q = \q -> q  -- ок
```

- Рекурсiя на C

```C
long factorial (int n)
{
 long res = 1; 
 while (n > 1)
   res *= n--;
 return res;
}
```
- Рекурсiя на Haskell

```Haskell
factorial n = if n > 1
   then n * factorial (n-1)
   else 1
```

- Запис у рядок

```Haskell
factorial n = if n > 1 then n * factorial (n-1) else 1
```
### "Ленивая установка" Haskell - 2 

### "Лінива установка" Haskell - 2 
- https://www.jdoodle.com/execute-haskell-online/ - Online Haskell Compiler IDE 
- Приклад - Online Haskell Compiler IDE

```Haskell
addMe :: Integer -> Integer -> Integer
addMe x y = x + y
main :: IO ()
main =  do
putStr "Sum of x + y = "
print(addMe 10 25)  -- 35
```

- Умова 1

```Haskell
a=10
-- a=9
addMe :: Integer -> Integer -> Integer    -- можно и без...
addMe x y = x + y
b=25
main :: IO ()
main =  do
putStr "Sum of x + y = "
print(addMe a b)  -- 35
```

- Умова 2

```Haskell
addMe :: Integer -> Integer -> Integer
addMe x y = x + y
main :: IO ()
main =  do
putStr "Sum of x + y = "
print(addMe 10 (addMe 0 25))  -- 35
```

- Факторiал

```Haskell
factorial n = if n > 1 then n * factorial (n-1) else 1
n=5  
main :: IO ()
main =  do
putStr "factorial = "
print(factorial n)    -- 120
```

- Версії ghc. Баттони: "Екзек'ют", "Завантажування", "Виїжджання", "Весь екран" 
- Виводимо "Здрасте!"

```Haskell
module Main where  -- пишем что этот файл является исполняемым. С этого файла начинается компиляция 
main :: IO()  -- создаём такую функцию, которая относится к типу данных IO - ввод-вывод
main = print "Hello World!!!" -- выводит
main = putStrLn "Hello World!!!" -- выводит
```

- Двох чи 2 рази - ВОНО не любить... :-) 

```Haskell
module Main where  -- пишем что этот файл является исполняемым. С этого файла начинается компиляция 
main1 :: IO()  -- создаём такую функцию, которая относится к типу данных IO - ввод-вывод
main1 = print "Hello World 1 !!!" -- выводит
main :: IO()  -- создаём такую функцию, которая относится к типу данных IO - ввод-вывод
main = putStrLn "Hello World 2 !!!" -- выводит
```

- ВОНО любить щось тільки одне... :-) 

```Haskell
-- module Main where  -- пишем что этот файл является исполняемым. С этого файла начинается компиляция 
-- main1 :: IO ()  -- создаём такую функцию, которая относится к типу данных IO - ввод-вывод
main1 = print "Hello World 1 !!!" -- выводит
-- main :: IO ()  -- создаём такую функцию, которая относится к типу данных IO - ввод-вывод
-- main = putStrLn "Hello World 2 !!!" -- выводит
main2 = main1
main3 = main2
main4 = main3
main = main4
```

- Два перші рядки – корисні для програміста. Щоб розуміти, де виконується файл і до чого відноситься функція main. 
- Немає циклів та змінних. Приклад із факторіалом.

```Haskell
module Main where
factorial  x | x < 2  = 1
factorial x = x * factorial (x-1)
main :: IO () 
main = print $ factorial 6 -- 720
```

- Варіант запису

```Haskell
-- module Main where
-- main :: IO () 
main = print $ factorial 6 -- 720
factorial  x | x < 2  = 1
factorial x = x * factorial (x-1)
```

- Корисно вказувати тип даних

```Haskell
module Main where
factorial :: Int -> Int
factorial  x | x < 2  = 1
factorial x = x * factorial (x-1)
main :: IO () 
main = print $ factorial 6 -- 720
```

- Змінних немає Константа це функція

```Haskell
value :: Int
value = 5      -- функция
main :: IO () 
main = print value
```

- Приклад лінивості

```Haskell
func :: Double -> Double
func  x = 777
main :: IO ()
main = print $ func (5/0)  -- 777
-- main = print (5/0)  -- Infinity
```

- Списки та "лінивий список" 

```Haskell
main :: IO ()
-- main = print $ take 5 [0..]  --  [0,1,2,3,4]
main = print [0..6]  -- [0,1,2,3,4,5,6]
```

___ 
## Додаткові зауваження
- Відеоролик: "Що це за мова програмування Haskell такий_Душкін пояснить"
- 5 програмних типів Haskell 
	- Модулі 
	- Функції 
	- Типи даних 
	- Класи типів 
	- Примірники класів 
- Ядро (чисте типізоване Л-обчислення) + обв'язування (бібліотеки) 
	- Чистий – всі функції в ньому є математичними 
	- Типізований - статична типізація - кожна програмна сутність має певний тип під час компіляції 
	- Детермінований - чисті математичні функції не мають побічних ефектів
___ 
- -->  [[ФП - UA - Лекцiя 6]]
- <--  [[ФП - UA - Лекцiя 4]]
___ 
