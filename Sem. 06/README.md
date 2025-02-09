
# Масиви (с фиксирана дължина)

**Масивът** е наредена последователност от елементи от един тип. Отделен елемент на масива се достъпва посредством името на масива, последвано от поредния номер (индекс) на елемента в квадратни скоби



## Инициализация на масиви

   ```c++
    int arr[6]; // Създава масив от 6 елемента, всеки от които е цяло число.
    int arr2[] = {0, 1, 2, 3, 4, 5}; // Създава масив от 6 елемента.
    int arr3[6] = {1,2,3}; //Останалите елементи се запълват с defaut-на стойност. 
    int arr[]; //грешка
    int arr[4] = {1, 2, 3, 4, 5} // грешка
```

  Задължително големината на масива трябва да е константа, чиято стойност е ясна преди да се компилира програмата

   ```c++
	int n;
	cin >> n;
	int arr[n]; //грешка!
```

   ```c++
	const int SIZE = 4;
	int arr[SIZE]; //ok!
```

## Достъп на елемент
	В масивите имаме константен достъп до всеки един елемент.
Достъпът става посредством индекси. Индексацията започва от 0. (защо?)

   ```c++
   int arr[] = {1, 2, 400, 4, 5}
    arr[3] = 44; //Присвоява на елементът на индекс 3 стойността 44.
					       // [1, 2, 400, 44, 5]
    cout << arr[2]; //Отпечатва на стандартния изход елементът на индекс 2 (400)
   
```
arr не е самият масив, а указател към първия елемент.
   ```c++
   int arr[] = {1, 2, 400, 4, 5}
	cout << arr; //ще се отпечата АДРЕСА на масива, но не и самия масив.
```

Достъпът до елемент става, чрез смятането адреса му:

Адресът на arr[i] е: arr + i * sizeof(type of array)

i е брой "отмествания" надясно.





## Подаване на масиви във функции
   ```c++
    #include <iostream>
    using namespace std;
    void print(const int arr[], int len)
    {
	    for(int i = 0; i < len; i++)
	    {
	        cout << arr[i] << " ";
	    }
	}
	void increment(int[] arr, unsigned size)
	{
		for(unsigned i = 0; i < size; i++)
			arr[i]++;
	}
	int main()
	{
	    const int SIZE = 4;
	    int arr[SIZE] {1,2,3,4};
    
        increment(arr, SIZE);
	    print(arr,SIZE);
    
	    return 0;
    }
```
 Масивите се подават във функциите по адрес! 
 Т.е промените, които се правят върху масива във функцията, ще се отразят върху подадения като параметър масив!
## Примери

 - Отпечатване на масив
 - Линейно търсене в масив
 -  Решето на Ератостен
 - Двоично търсене
 - Обръщане на масив

<h3>Задачи</h3>

**Задача 1:** Да се напише функция, която приема масив и връща дали е палиндром.

*Вход: [1 2 3 2 1], Изход: true*

**Задача 2** Да се напише функция, която приема масив и връща най-малкото общо кратно на числата в масива.

*Вход: [9 18 6 12], Изход: 36*


**Задача 3** Да се напише функция, която приема масив и връща най-големият общ делител на числата в масива.

*Вход: [9 18 6 12], Изход: 3*

**Задача 4 :** Да се напише функция, която приема масив и връща дали е конкатенация на два масива, които са палиндроми.

*Вход: [1 2 3 2 1 4 5 5 4], Изход: true*

*Вход: [1 2 3 4 5], Изход: false*

*Вход: [1 2 3 2 1], Изход: true*


**Задача 5 :** Въвежда се число N (N <= 1000) и N цели числа (елементи на масив).
Да се отпечатат броя на инверсиите в масива.

Инверсия ще наричаме двойка индекси (i,j), където i < j  и arr[i] > arr[j]

*Вход: 6 5 4 3 2 10  Изход: 15* //в масива [5 4 3 2 1 0]  има 15 инверсии.

*Вход: 5 10 11 12 13 14 15, Изход: 0*


**Задача 6:** 
От даден масив от  сортирани последнователни числа са премахнати някои числа.
Напишете фунцкия, която приема такъв масив и връща най-малкото премахнато число.

Решението ви трябва да работи с **логартмична сложност** ( а не с лиейно минаване през масива). 

*Вход: [5 6 7 9 10 12 13], Изход: 8* //премахнатите числа са 8 и 11.

*Вход: [10 12 13 14 16], Изход: 11* //премахнатите числа са 11 и 16.

Модифицирайте функцията, за да отпечатване и най-голямото премахнато число
