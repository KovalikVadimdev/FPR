20230930203708       #учу/ФП  
___ 
- "Функцiональне програмування" - "Функциональное 
- программирование" (ФП) 
- [[ФП - Лекция 8]]
- -->  [[ФП - UA - Лекцiя 9]]
- <--  [[ФП - UA - Лекцiя 7]]
___
## Тема: "Функціональне програмування на Python - 1"
- "Функциональное программирование на Python" - (2:00:11) - https://www.youtube.com/watch?v=3Dmi4b8MkMM
- Типи мов програмування: Імперативні, функціональні, логічні (Пролог) 
- Об'єктно-орієнтовані – частина структурних – підвид імперативних мов

```Python
>>> def fnk (x):
	return x+1
>>> fnk (1)
2
>>> fnk (7)
8
>>> fnk(12345)
12346
>>> 
```

- Чисте ФП дозволяє замінити за допомогою рекурсії цикли. Нічого нікуди не присвоюється. Приклад – прогресія:

```Python
>>> def progression(start, stop, step):
	if start >= stop:
		return
	else:
		print(start)
		progression(start + step, stop, step)
>>> progression (0, 9, 1)
0
1
2
3
4
5
6
7
8
>>> 
```

- Все, що з циклами, можна зробити на рекурсіях. все що з рекурсіями – можна зробити на циклах. Імперативні та функціональні мови алгоритмічно рівноправні (рівноможливі). 
- До речі 1:

```Python
>>> fnk(fnk(1))
3
>>> fnk(fnk(fnk(1)))
4
>>> 
```

- До речі  2: 

```Python
>>> def fnk2 (x):
	return fnk(fnk(fnk(x)))
>>> fnk2(1)
4
>>> fnk(fnk(1))
3
>>> fnk2(fnk2(1))
7
>>> 
```

- Черепашка 

```Python
import turtle as t
def go_snowy(length):
    if length < 5:
	    t.forward(length)
    else:
            go_snowy(length / 3)
            t.left(60)
            go_snowy(length / 3)
            t.right(120)
            go_snowy(length / 3)
            t.left(60)
            go_snowy(length / 3)
go_snowy(100)
```

- Дод. примочки з управління черепашкою

```Python
t.speed(100)
t.right(120)
go_snowy(100)
t.right(120)
go_snowy(100)
```

- Фрактал "Сніжинка Коха" 
- Покращена версія програми. Послідовне промальовування трьох сніжинок.

```Python
import turtle as t
def go_snowy(length):
    if length < 5:
	    t.forward(length)
    else:
            go_snowy(length / 3)
            t.left(60)
            go_snowy(length / 3)
            t.right(120)
            go_snowy(length / 3)
            t.left(60)
            go_snowy(length / 3)
t.speed(300)
go_snowy(300)
t.right(120)
go_snowy(300)
t.right(120)
go_snowy(300)
go_snowy(300)
t.right(120)
go_snowy(300)
t.right(120)
go_snowy(300)
go_snowy(300)
t.right(120)
go_snowy(300)
t.right(120)
go_snowy(300)
```

- У Python цикл for не є імперативним 
- Робота з кортежами значень. Функція може приймати та повертати кортеж значень (вектор значень).

```Python
>>> def f(a,b,c):
	return a+b, b+c
>>> x,y = f(1,2,3)
>>> print(x)
3
>>> print(y)
5
>>> 
```

___ 
## Додаткові зауваження 
- генератор, генеративна функція. Приклад – функція progression Видає список значень. Наперед невідомого розміру. Список генерується не весь, а "при потребі" 
- progression при step=0 – зациклюється. 
- відеоролик (вказаний як джерело) - 45 - 50 хвилин ...

___ 
- -->  [[ФП - UA - Лекцiя 9]]
- <--   [[ФП - UA - Лекцiя 7]]
___ 
