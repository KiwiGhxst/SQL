<h2>📊 SQL: Задачи для тестирования и анализа данных</h2>

<table>
  <thead>
    <tr>
      <th>№</th>
      <th>Условие</th>
      <th>SQL-запрос</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Выведите информацию обо всех продуктах</td>
      <td><code>SELECT * FROM products;</code></td>
    </tr>
    <tr>
      <td>2</td>
      <td>Продукты от Apple в категории Phones</td>
      <td><code>SELECT * FROM products WHERE manufacturer = 'Apple' AND category = 'Phones';</code></td>
    </tr>
    <tr>
      <td>3</td>
      <td>Названия и цены товаров, содержащих "sa"</td>
      <td><code>SELECT name, price FROM products WHERE name ILIKE '%sa%';</code></td>
    </tr>
    <tr>
      <td>4</td>
      <td>Товары в диапазоне цен от 100 до 1000</td>
      <td><code>SELECT name, price FROM products WHERE price BETWEEN 100 AND 1000;</code></td>
    </tr>
    <tr>
      <td>5</td>
      <td>Сумма товаров Samsung</td>
      <td><code>SELECT SUM(price) AS "SAMSUNG TOTAL PRICE" FROM products WHERE manufacturer = 'Samsung';</code></td>
    </tr>
    <tr>
      <td>6</td>
      <td>Сортировка товаров по убыванию цены</td>
      <td><code>SELECT name, price FROM products ORDER BY price DESC;</code></td>
    </tr>
    <tr>
      <td>7</td>
      <td>Уникальные производители</td>
      <td><code>SELECT DISTINCT manufacturer FROM products;</code></td>
    </tr>
    <tr>
      <td>8</td>
      <td>Первые 2 уникальные категории</td>
      <td><code>SELECT DISTINCT category FROM products LIMIT 2;</code></td>
    </tr>
    <tr>
      <td>9</td>
      <td>Товары длиной 12 символов, начинающиеся с A</td>
      <td><code>SELECT name FROM products WHERE LENGTH(name) = 12 AND name LIKE 'A%';</code></td>
    </tr>
    <tr>
      <td>10</td>
      <td>Средняя цена товаров</td>
      <td><code>SELECT AVG(price) AS "PRODUCTS AVG PRICE" FROM products;</code></td>
    </tr>
    <tr>
      <td>11</td>
      <td>Производитель IN (Samsung, Huawei)</td>
      <td><code>SELECT name, description FROM products WHERE manufacturer IN ('Samsung', 'Huawei');</code></td>
    </tr>
    <tr>
      <td>12</td>
      <td>UNION: названия продуктов и номера заказов</td>
      <td><code>SELECT name FROM products UNION SELECT order_number FROM orders;</code></td>
    </tr>
    <tr>
      <td>13</td>
      <td>HAVING: товары в категориях 15 шт</td>
      <td><code>SELECT category, COUNT(*) FROM products GROUP BY category HAVING COUNT(*) 15;</code></td>
    </tr>
    <tr>
      <td>14</td>
      <td>CASE: сообщение в зависимости от компании</td>
      <td><code>SELECT manufacturer, category, price, name, CASE manufacturer
  WHEN 'Apple' THEN 'Это продукт компании Apple'
  WHEN 'Samsung' THEN 'Это продукт компании Samsung'
  WHEN 'Huawei' THEN 'Это продукт компании Huawei'
  WHEN 'Xiaomi' THEN 'Это продукт компании Xiaomi'
  ELSE 'Другая компания'
END AS comment FROM products;</code></td>
    </tr>
    <tr>
      <td>15</td>
      <td>Логин пользователя, номера заказов и суммы</td>
      <td><code>SELECT users.login, orders.order_number, orders.total_price FROM users JOIN orders ON users.id = orders.user_id;</code></td>
    </tr>
    <tr>
      <td>16</td>
      <td>Номера заказов, названия товаров, количество</td>
      <td><code>SELECT order_items.order_id, products.name, order_items.quantity FROM order_items JOIN products ON order_items.product_id = products.id;</code></td>
    </tr>
    <tr>
      <td>17</td>
      <td>Пользователи и заказы (в т.ч. без заказов)</td>
      <td><code>SELECT users.login, orders.order_number FROM users LEFT JOIN orders ON users.id = orders.user_id;</code></td>
    </tr>
    <tr>
      <td>18</td>
      <td>Оплаченные заказы и товары (в т.ч. без связки)</td>
      <td><code>SELECT order_items_paid.order_id, products.name FROM products RIGHT JOIN order_items_paid ON products.id = order_items_paid.product_id;</code></td>
    </tr>
    <tr>
      <td>19</td>
      <td>Товары дороже Samsung Active 5</td>
      <td><code>SELECT name, price FROM products WHERE price(SELECT price FROM products WHERE name = 'Samsung Active 5');</code></td>
    </tr>
    <tr>
      <td>20</td>
      <td>Выведите 5 самых дешевых товаров</td>
      <td><code>SELECT name, price FROM products ORDER BY price ASC LIMIT 5;</code></td>
    </tr>
    <tr>
      <td>21</td>
      <td>Проверьте товары без описания</td>
      <td><code>SELECT * FROM products WHERE description IS NULL;</code></td>
    </tr>
    <tr>
      <td>22</td>
      <td>Подсчитайте количество товаров в каждой категории</td>
      <td><code>SELECT category, COUNT(*) FROM products GROUP BY category;</code></td>
    </tr>
    <tr>
      <td>23</td>
      <td>Найдите товары с дублирующимися названиями</td>
      <td><code>SELECT name, COUNT(*) FROM products GROUP BY name HAVING COUNT(*)1;</code></td>
    </tr>
    <tr>
      <td>24</td>
      <td>Показать товары, добавленные за последние 7 дней</td>
      <td><code>SELECT * FROM products WHERE created_at = NOW() - INTERVAL'7 days';</code></td>
    </tr>
  </tbody>
</table>
