# tasktest
Тестовое задание состоит из трех частей. По первой части необходимо подробно описать решение, по второй и третьей частям – написать код. При проверке будем смотреть на стиль кода, документирование, знание API, оптимизацию по нагрузке. Результат надо запушить в публичный репозиторий на гитхабе.

/*****************************************************************************/

1а) Дано: интернет магазин на "1с-битрикс: Бизнес", каталог, корзина и оформление заказа реализованы нативными компонентами (catalog, sale.basket.basker, sale.order.full). 
Задача:  реализовать акцию "Каждый N товар за X рублей". У акции должны быть настройки, где выставляется период активности акции, параметры N и X

- Изучение документации для выявление обновлений в правилах работы с корзиной. Если акцию можно реализовать через «Правила работы с корзиной», то настраиваются правила.
- Если акцию нельзя реализовать через правила работы с корзиной, то создается компонент и модуль для вынесения настроек в админ-панель.
В компоненте делаем обработку массива товаров на странице корзины:
	1. проверяем актуальна ли акция исходя из настроек активности в модуле.
	Если актуальна:
	2. получаем общее количество товаров в корзине.
	3. вычисляем, в зависимости от настроек, количество товаров со скидкой (общее количество товаров / N)
	4. сортируем массив товаров в корзине по цене
	5. устанавливаем цены X для N товаров путем перебора в цикле массива и умножения количества товара по позиции на цену Х. 
	Если по позиции количество товаров меньше или равно N (остатку от N), то позиции присваивается цена X и общая сумма по позиции N*X
	Если по позиции количество товаров больше N (остатку от N), то итоговая сумма по позиции уменьшается на N*X
	6. Пересчитываем общую итоговую сумму по всем позициям
		
/*****************************************************************************/		

2а) У пользователя есть отложенные товары в корзине. Необходимо сделать почтовую рассылку по пользователям "Добрый день, #Имя_Фамилия# В вашем вишлисте хранятся товары #список_товаров#.", в списке указать все товары, отложенные за последние тридцать дней. При этом нужно проверить, чтобы в список не попали изделия, которые присутствуют в заказах пользователя за последний месяц. Скрипт должен быть оформлен для выполнения из консоли по крону. Пошаговое выполнение приветствуется, но необязательно.

См. директорию bitrix

/*****************************************************************************/		

3) Сверстай контрол оценки и показа рейтинга. Практически все наши контролы должны быть очень гибкими к окружающему пространству, должны уметь располагаться на любом фоне и при желании легко менять свой "скин". Обрати внимание, что контрол должен не только выставлять оценку, но и показывать текущую. 

См. верстку index.html + css/style.scss
Верстка на основе Compass SCSS. Для изменения скинов необходимо прописать другие цвета (можно сделать смену скинов через JS/jQuery).
