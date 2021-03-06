# decliner.js
### Мини-библиотека для склонения исчисляемых русских слов
![decliner logo](https://drive.google.com/uc?export=view&id=0B7lALWrgWMxpcWd0ZHhGNWxWVGs)

### Установка
Несколько вариантов установки библиотеки:
+ Склонировать репозиторий: ```git clone https://github.com/nmihalyov/decliner.git```
+ Скачать .zip архив (зелёная кнопка "Clone or download" на главной странице библиотеки)
+ Загрузка с помощью пакетных менеджеров:
  - NPM: ```npm i decliner --save-dev```
  - Bower: ```bower i decliner -D```
  - Yarn: ```yarn add decliner -D```

Далее просто включите библиотеку в ваш проект:
```html
<script src="%path%/decliner/dist/decliner.js"></script>
```
или её минифицированную версию
```html
<script src="%path%/decliner/dist/decliner.min.js"></script>
```
(где ```%path%``` - путь от корня проекта до папки в которую устанавливается пакет (или распаковвывается архив))

### Использование
Для начала работы необходимо создать массив из трёх строк (вариантов склонения) в строгом порядке: 1 %предмет%, 2 %предмета%, 5 %предметов%

Например  
```javascript
var rubles = ['рубль', 'рубля', 'рублей'];
```

Используя этот массив можно вызвать метод ```decline()``` в аргумент, которой передать необходимое число:
```javascript
rubles.decline(105); // "рублей"
```

Этот метод также имеет второй параметр (по-умолчанию ```false```). Если в него передать ```true```, то число, передаваемое в кач-ве первого аргумента будет подставлено в строку через пробел:
```javascript
rubles.decline(105, true); // "105 рублей"
```

Упрощённая форма для многократного обращения:
```javascript
var rublesDecline = function (n) {
  return rubles.decline(n, true);
}

rublesDecline(123); // "123 рубля"
```

### Дополнительная информация
**decliner.js** умеет работать и с отрицательными значениями:
```javascript
rublesDecline(-50); // "-50 рублей"
```

И с вещественными числами:
```javascript
rublesDecline(-0.4); // "-0.4 рубля"
```

В случае какой-либо ошибки при работе с библиотекой, эта ошибка выведется в консоль с описанием

Благодарность можно выразить поставив этому репозиторию звезду, а также зайдя в другие репозитории моего аккаунта

Контакты для связи:  
почта - nikita.mihalyov@gmail.com  
telegram - https://telegram.me/nmihalyov