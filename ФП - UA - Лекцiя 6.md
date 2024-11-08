20230930203148      #учу/ФП  
___ 
- "Функцiональне програмування" - "Функциональное программирование" (ФП) 
- [[ФП - Лекция 6]]
- -->  [[ФП - UA - Лекцiя 7]]
- <--  [[ФП - UA - Лекцiя 5]]
___
## Тема: Haskell - базовий синтаксис 
### Типи даних 
-  https://www.jdoodle.com/execute-haskell-online/  -  Online Haskell Compiler IDE 

```Haskell
--  20221001 -- 13:44 
-- module MAIN where
module Main where
{-          -- многострочный коммент
-- Типы данных:
  Int         -- (ограниченное число)
  Integer     -- 5 (целые) бесконечное неограниченное 
  Float
  Double      -- 5,14 (вещественные)
  Char        -- 'a'
  String      -- 'mumburu' Определение: String = [Char] (синоним на "список Char")
  Bool        -- True | False
-}
-- String = [Char] -- error ...
a = 1313131214141151615615114315672873248273454576547645163246734263457656879098045634564546
main :: IO()
-- main = print "Hello World !!!"  
main = print a
--
```

### Умови. 
- Перевірка умов. Є 5 варіантів синтаксису. 
#### ПЕРШИЙ варiант 
- Умова **рівно**

```Haskell
--  20221001 -- 14:18 
module Main where

func :: Int -> String
func x = if x == 5
-- func x = if (==) x 5
  then "Hello"
  else "World !!!"
  
main :: IO()
main = print $ func 5  
-- main = print $ func 8
{-
main = do
print $ func 5
print $ func 8
-}
--
```

- Умова **не рівно**

```Haskell
--  20221001 -- 20:22 
module Main where
{-
==
/=
<
>
<=
>=
-}
func :: Int -> String
func x = if x /= 5
  then "Hello"
  else "World !!!"
  
main :: IO()
main = print $ func 5  
--
```

#### ДРУГИЙ варiант 
- У синтаксисі Haskell є 5 варіантів принципів завдання умови

```Haskell
--  20221001 -- 20:34 
func :: Int -> String
func x = case x of
  5 -> "Hello"         -- отступ важен
  10 -> "World !!!"    -- ставятся стрелочки
  20 -> "OK !!!"
  oterwise -> "Something more ..." -- другие, не указанные определения
--
```
- 
```haskell
module Main where

func :: Int -> String
func x = case x of 5 -> "Hello"; 10 -> "World !!!"; 20 -> "OK !!!"; oterwise -> "Something more ..." 

main :: IO()
main = do
print $ func 5
print $ func 10
print $ func 20
print $ func 8
```

- ... з новим шаблоном...

```Haskell
--  20221006 -- 15:46 
module Main where

func :: Int -> String
func x = case x of 5 -> "Hello"; 10 -> "World !!!"; 20 -> "OK !!!"; oterwise -> "Something more ..." 

main :: IO()
main = do
print $ func 5
print $ func 10
print $ func 20
print $ func 8
--
```

- сам OBSIDIAN-шаблон:

```Haskell
--  {{date:YYYYMMDD}} -- {{time:HH:mm}} 

--
```

- Виведення кількох принтів у **case x of** (аналогічна функції switch(x) у С-подібних мовах))

```Haskell
--  20221001 -- 20:43 
main = do
print $ func 5
print $ func 10
print $ func 20
print $ func 40
--
```

- "... case x of " аналогічна функції **switch(x)** у С-подібних мовах

```C
# 20221001 -- 20:54 
switch(x) {
  case 5 printf("Hello"); break;
  case 10 printf("World !!!"); break;
  case 20 printf("OK !!!"); break;
  ...
}
# 
```

#### ТРЕТIЙ варiант 
- Те саме, але інший синтаксис:

```Haskell
--  20221001 -- 21:03 
func x
  | x == 5 = "Hello"
  | x == 10 = "World !!!"
  | x == 20 = "OK !!!"
  | otherwise = "Something more ..."
--
```

- Сшивка в один рядок - ПРАЦЮЄ

```Haskell
--  20221006 -- 15:56 
func x   | x == 5 = "Hello" | x == 10 = "World !!!" | x == 20 = "OK !!!" | otherwise = "Something more ..."
--
```

#### ЧЕТВЕРТИЙ варiант 
- Аналогiчно, але з  **if**

```Haskell
--  20221001 -- 21:13 
{-# LANGUAGE MultiWayIf #-} -- зависит от версии ?
module Main where

func :: Int -> String
func x
  | x == 5 = "Hello"
  | x == 10 = "World !!!"
  | x == 20 = "OK !!!"
  | otherwise = "Something more ..."

main :: IO()
main = do
print $ func 5
print $ func 10
print $ func 20
print $ func 40
-- main = print $ func 5  
--
```

#### П'ЯТИЙ варіант

```Haskell
--  20221001 -- 21:39 
func :: Int -> String
func 5 = "Hello"
func 10 = "World !!!"
func 20 = "OK !!!"
func _ = "Something more ..."  
--
```

- Знак "підкреслення" - не має значення який аргумент. Компілятор попередить, що після його перевірки інше ігнорується 
 
```Haskell
--  20221001 -- 21:49 
func :: Int -> String
func _ = "Something more ..."
func 5 = "Hello"
func 10 = "World !!!"
func 20 = "OK !!!"
--
```

___ 
## Додаткові зауваження
- ... у ролiку - до 12 хвилини. 
___ 
- -->  [[ФП - UA - Лекцiя 7]]
- <--  [[ФП - UA - Лекцiя 5]] 
___ 
