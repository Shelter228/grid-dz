# Макет "Святого Грааля" с использованием сетки

Теперь, когда вы сделали свой макет "Святого Грааля" адаптивным, мы предлагаем вам немного усложнить его, добавив некоторые функции. Возможно, вы обнаружите, что это немного сложнее, чем вы ожидали. Вас даже может побудить использовать Flexbox. Но ради этого практического задания попробуйте посмотреть, сможете ли вы разобраться, как воссоздать этот макет, используя только сетку. Не стесняйтесь добавлять свой контент или стили!

### Подсказки

- Для этого упражнения вам нужно добавить некоторые блоки объявлений CSS в файл style.css. Посмотрите HTML, чтобы узнать, какие селекторы и комбинаторы вы можете использовать.
- Рассматривайте макет по одной секции за раз.
- Вам не нужно добавлять или изменять что-либо в HTML, но будет полезно изучить отношения родительских и дочерних элементов.
- Как и с Flexbox, вы можете легко центрировать элемент, сделав его сеткой.
- Не беспокойтесь о том, что изображение-заполнитель будет растягиваться при изменении размера окна браузера. Об этом будет рассказано в уроках по адаптивной верстке.

## Желаемый результат

![desired outcome](./desired-outcome.png)

Если вы используете инструменты из урока "Продвинутые свойства сетки", вы должны сможете автоматически подгонять ваши карточки статей при изменении размера окна браузера:

![desired outcome stretched](./desired-outcome-stretched.png)

### Проверка
- Элемент-контейнер имеет два столбца.
- Второй столбец контейнера в 4 раза больше первого.
- У элемента-контейнера есть расстояние 4px.
- У элемента header два столбца.
- `ul` внутри элемента menu содержит другую сетку.
- `ul` внутри элемента nav содержит другую сетку.
- Элемент sidebar имеет расстояние 50px.
- Текстовые элементы в боковой панели центрированы с помощью сетки.
- Элемент article должен устанавливать столбцы сетки с использованием `repeat` вместе с свойствами `auto-fit` и `minmax`.
- Столбцы статьи должны иметь минимальное значение 250px и максимальное значение 1fr.
- У элемента article есть расстояние 15px.
- Карточные элементы внутри контейнера article имеют высоту 200px.
- Заголовок и подвал занимают оба столбца.
- Боковая панель занимает только первый столбец.
- Элементы nav и article занимают только второй столбец.
* {
  margin: 0;
  padding: 0;
}

.container {
  text-align: center;
  display: grid;
  grid-template-columns: 1 fr 2fr;
}

.container div {
  padding: 15px;
  font-size: 32px;
  font-family: Helvetica;
  font-weight: bold;
  color: white;
}

.header {
  background-color: #393f4d;
  display: grid;
  grid-template-columns: repeat(4, 300px);
  align-items: center;
}
.logo {
  display: grid;
  justify-self: start;
}
.menu ul,
.menu li {
  font-size: 16px;
  display: grid;
  grid-template-columns: repeat(4, 200px);
  margin: 0 0 0 170px;
}

.sidebar {
  background-color: #C50208;
  display: grid;
  gap: 50px 0;
  display: grid;
  grid-template-columns: repeat(1, 300px);
  align-items: center;
}

.sidebar .photo {
  background-color: white;
  color: black;
  font-size: 12px;
  font-weight: normal;
  border-radius: 10px;
  display: grid;
}


.sidebar .side-content {
  background-color: white;
  color: black;
  font-size: 16px;
  font-weight: normal;
  display: grid;
  grid-template-rows: repeat(1, 150px);
  align-items: center;
}
.photo {
  display: grid;
  grid-template-rows: repeat(1, 150px);
  align-items: center;
}
.side-content {
  display: grid;
}
.nav {
  background-color: #C50208;
  display: grid;
  gap: 30px;
}

.nav ul li {
  font-size: 16px;
  text-transform: uppercase;
  display: grid;
  grid-template-columns: repeat(3, 300px);
  gap: 20px 30px;
}

.article {
  background-color: #bccbde;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  align-items: center;
  gap: 10px;
}

.article p {
  font-size: 18px;
  font-family: sans-serif;
  color: white;
  text-align: left;
  display: grid;
  text-align: left;
  max-width: 200px;
}

.article .card {
  background-color: #FFFFFF;
  color: black;
  text-align: center;
  height: 200px;
}

.card p {
  color: black;
  font-weight: normal;
  font-size: 14px;
}

.card .title {
  font-size: 18px;
  text-align: center;
}

.footer {
  background-color: #393f4d;
}

.footer p {
  font-size: 13px;
  font-weight: normal;
}
