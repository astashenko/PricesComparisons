# Сравнительный отчет оценки стоимости транспортных средств, выполненной Компанией 1 и аналитическим агентством ***

## Установка

```bash
git clone https://github.com/astashenko/PricesComparisons.git
```

---
## Использование

Проект создан для выявления различий в оценке стоимости транспортных средств,  выполненной Компанией 1 и аналитическим агентством ***

- Исходные тексты программ находятся в папке **src**
  
- Директория **src/data** предназначена для создания .plk файлов, инициализации функций доступа к данным


####  Назначение отдельных веток:
*main* - стабильная версия

*develop* - для разработки

*preprod* - ветка перед merge в main


# Отчет по предоставленным данным аналитическим агентством «Компания 2»

Предметом данной работы являлось сравнение средних цен транспортных средств, предоставленных двумя организациями: Компанией 1 и Аналитическим агентством ***, далее по тексту Компания 2, а также качество и степень обогащения данных по VIN кодам  «Компания 2». 

## Исходные данные

В аналитическое агенство «Компания 2» для тестирования был направлен файл, содержащий 100 значений VIN кодов. Из них один VIN «Z6FDXXEECDH*» был задублирован. Еще один VIN «X96231073N28*» отсутствует в базе данных DWH, поэтому считается отправленным ошибочно и при дальнейшем анализе не учитывался. 

Таким образом, тестирование проводилось на 98 транспортных средствах, по 29-ти из которых была предоставлена оценка стоимости от Компании 1.

На рис. 1 показан перечень марок с их количеством, который был направлен аналитическому агенству «Компания 2» в качестве тестовой выборки.
 
 <img src='data/img_report/Number of Vehicles.png'> 

**Рисунок 1 Количество представленных марок**  

## Анализ обогащения данных

Обогащенная информация представлена по всем 98 VIN кодам, которые были направлены аналитическому агенству «Компания 2» для обогащения. В табл. 1 приведен перечень атрибутов полученного обогащения с процентным значением их заполнения. На рис. 2 также представлена информация по проценту заполнения.


**Таблица 1 Предоставленные данные аналитическим агенством «Компания 2»**

| Показатель                               | Количество незаполненных значений | Процент заполнения |
| ---------------------------------------- | --------------------------------- | ------------------ |
| VIN                                      | 0                                 | 100.00             |
| Марка                                    | 0                                 | 100.00             |
| Модель                                   | 0                                 | 100.00             |
| Поколение                                | 1                                 | 98.98              |
| Тип кузова                               | 0                                 | 100.00             |
| Год выпуска                              | 0                                 | 100.00             |
| Тип топлива                              | 0                                 | 100.00             |
| Объём двигателя, л,                      | 0                                 | 100.00             |
| Мощность, л.с.                           | 0                                 | 100.00             |
| Тип КПП                                  | 0                                 | 100.00             |
| Тип привода                              | 0                                 | 100.00             |
| Цена                                     | 0                                 | 100.00             |
| В залоге или нет (1 - в залоге, 0 - нет) | 0                                 | 100.00             |
| Дата последней регистрации               | 15                                | 84.69              |
| Номер владельца последней регистрации    | 15                                | 84.69              |
| Тип владельца последней регистрации      | 11                                | 88.78              |
| ИНН владельца последней регистрации      | 44                                | 55.10              |
| Регион последней регистрации             | 11                                | 88.78              |
| Дата предыдущей регистрации              | 98                                | 0.00               |
| Номер владельца предыдущей регистрации   | 98                                | 0.00               |
| Тип владельца предыдущей регистрации     | 98                                | 0.00               |
| ИНН владельца предыдущей регистрации     | 98                                | 0.00               |
| Регион предыдущей регистрации            | 98                                | 0.00               |
| Дата первой регистрации                  | 15                                | 84.69              |
| Номер владельца первой регистрации       | 15                                | 84.69              |
| Тип владельца первой регистрации         | 15                                | 84.69              |
| ИНН владельца первой регистрации         | 46                                | 53.06              |
| Регион первой регистрации                | 15                                | 84.69              |
 
 
 <img src='data/img_report/Степень обогащения данных.png'> 

**Рисунок 2 "Степень обогащения данных"**

Отсутствие данных в пяти столбцах о дате предыдущей регистрации, номере владельца предыдущей регистрации, типе владельца предыдущей регистрации, ИНН владельца предыдущей регистрации и регионе предыдущей регистрации, скорее всего, связано с отсутствием предыдущих владельцев, а не с непредставлением сведений о таковом. 

В остальном, процент обогащения данными о самом транспортном средстве составляет 100 процентов, а по данным о регистрации транспортного средства находится в пределах от 84 до 88 процентов. 

Анализ правильности обогащенной информации проводился по атрибутам Марка, Модель и Год выпуска. Данные для сравнения были получены из таблицы базы данных DWH.NEW_LEASOBJECT. Совпали 98 из 98 значений, что является 100% правильным обогащением. 
 
## Сравнительный анализ оценки стоимости 

Сравнительный анализ оценки стоимости проводился по 29 различным транспортным средствам. На рис. 3 представлен перечень марок таких транспортных средств. На рис. 4 — их распределение по годам выпуска. 
 
 <img src='data/img_report/Количество марок автомобилей.png'> 

**Рисунок 3 Марки автомобилей, участвующих в сравнительном анализе стоимости**
 
 <img src='data/img_report/Количество ТС по годам.png'> 

**Рисунок 4 Года выпуска автомобилей, участвующих в сравнительном анализе стоимости**

Стоимость транспортных средств, участвующих в сравнении, по оценке Компании 1 варьировалась в диапазоне от 968 000 до 10 100 000 рублей. На рис. 5 показана стоимость каждого автомобиля по оценке «Компания 1» и «Компания 2». В табл. 2 представлены статистические данные об оценке стоимости транспортных средств. 
 
  <img src='data/img_report/стоимость оценочная.png'> 

**Рисунок 5 Оценочная стоимость автомобилей**

**Таблица 2 Статистические данные о стоимости**

|                                             | «Компания 1»  | Аналитическое агентство «Компания 2» | Разница (Diff) |
| ------------------------------------------- | ------------- | ------------------------------------ | -------------- |
| Среднее значение стоимости, руб.            | 3 324 387     | 3 242 763                            | 81 624         |
| Среднеквадратическое отклонение, руб. (std) | 2 288 479     | 1 883 458                            | 892 199        |

 
Анализировались две средние разницы в стоимости транспортных средств: абсолютная

$\overline{Diff} = \frac{1}{N} * \sum_{i=1}^{N}Diff_i$

и относительная   

$\overline{Relative} = \frac{1}{N} * \sum_{i=1}^{N}Relative_i$

где $Diff_i$  — разница в стоимости i-того транспортного средства,   
$Relative_i$ — относительная разница в стоимости $i$-того транспортного средства,  
$N$ — количество транспортных средств. 

$Diff_i= C_{i,company1} – C_{i,company2}$ ,

$Relative_i=  (C_{i,company1}  - C_{i,company2})/С_{i,company1} *100$%,

где $C_{i,company2}$ —стоимость $i$ -того транспортного средства, предоставленная «Компанией 2», 
$C_{i,company1}$ —стоимость i-того транспортного средства, предоставленная «Компанией 1».

На рис. 6 изображено распределение абсолютной и относительной разностей стоимости в оценках

  <img src='data/img_report/Распределение разности.png'> 

**Рисунок 6 Распределение разности стоимости в оценках**

На рис. 7 изображены графики Квантиль-квантиль (Q-Q plot), показывающие, насколько близки распределения абсолютной и относительной разности стоимости с t-distribution со степенями свободы (df) 28. 

  <img src='data/img_report/Q-Q plot.png'> 

**Рисунок 7 Q-Q plot**


Из графиков видно, что распределение разности оценок стоимости сильно отклоняется от $t$-распределения из-за небольшой тестовой выборки и большого разброса в стоимости транспортных средств. Наблюдается заметная асимметрия справа (right-skewed distribution). 

Распределение относительной разности стоимости заметно ближе к $t$-распределению. Поэтому исследование на различие в оценках стоимости проводился только на относительной разнице.

 
Для анализа использовался $t$-test. В качестве нулевой гипотезы было равенство нулю средней относительной разницы в оценках стоимости. В качестве альтернативной гипотезы — средняя относительная разница стоимости, предоставленная Аналитическим агентством «Компания 2» и «Компанией 1» различна. Двусторонний  $t$-тест был проведен с уровнем значимости α=0.1. 

То есть,  

$H0: \overline{Relative} = 0$  
$H1: \overline{Relative} \not= 0$

Полученные значения приведены в табл.3.

**Таблица 3 Расcчитанные значения $t$-test**

|                                          |         |
| ---------------------------------------- | ------- |
| Средняя относительная разность оценки, % | -3.02   |
| Среднеквадратическое отклонение ($std$), % | 20.21   |
| Значение $t$-статистики                    | -0.7915 |
| $p$-value                                  | 0.4353  |


Рассчитанное значение $p$-value (0.4353) больше установленного уровня значимости $α=0.1$, что не дает достаточно оснований опровергнуть гипотезу равенства нулю средней относительной разницы в оценках стоимости. 

## Заключение:

Процент обогащения данными о самом транспортном средстве (Марка, Модель, Тип кузова, Год выпуска и т.п.) составляет **100** процентов, по данным о регистрации транспортного средства находится в пределах от **84** до **88** процентов. Правильный процент определения атрибутов Марка, Модель и Год выпуска составляет **100%**.

Статистически достоверных доказательств различиЙ относительной оценки стоимости транспортных средств при уровне значимости $α=0.1$, предоставленных компаниями «Компания 2» и «Компанией 1», **не обнаружены**. 

