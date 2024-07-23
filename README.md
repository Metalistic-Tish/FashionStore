# FashionStore
Women's Clothing Store

Here is a table that I created for a fake women's clothing store.
I came up with some different queries so feel free to take a look and play around with it if you're interested.
Thanks.

CREATE TABLE FashionStore (
    item_size TEXT,
    item_category TEXT,
    item_color TEXT,
    price DECIMAL(10, 2),
    stock_quantity INTEGER,
    average_rating DECIMAL(3, 2)
);

INSERT INTO FashionStore (item_size, item_category, item_color, price, stock_quantity, average_rating)
VALUES
    ('16', 'Pants', 'Black', 29.99, 60, 4.4),
    ('16', 'Pants', 'Purple', 29.99, 42, 4.4),
    ('16', 'Pants', 'Red', 29.99, 16, 4.4),
    ('14', 'Pants', 'Black', 29.99, 32, 4.4),
    ('14', 'Pants', 'Purple', 29.99, 64, 4.4),
    ('14', 'Pants', 'Red', 29.99, 18, 4.4),
    ('12', 'Pants', 'Black', 29.99, 45, 4.4),
    ('12', 'Pants', 'Purple', 29.99, 52, 4.4),
    ('12', 'Pants', 'Red', 29.99, 60, 4.4),
    ('10', 'Pants', 'Black', 29.99, 60, 4.4),
    ('10', 'Pants', 'Purple', 29.99, 60, 4.4),
    ('10', 'Pants', 'Red', 29.99, 60, 4.4),
    ('9', 'Pants', 'Black', 29.99, 60, 4.4),
    ('9', 'Pants', 'Purple', 29.99, 60, 4.4),
    ('9', 'Pants', 'Red', 29.99, 60, 4.4),
    ('7', 'Pants', 'Black', 29.99, 60, 4.4),
    ('7', 'Pants', 'Purple', 29.99, 60, 4.4),
    ('7', 'Pants', 'Red', 29.99, 60, 4.4),
    ('XXL', 'Blouse', 'Black', 29.99, 60, 4.6),
    ('XXL', 'Blouse', 'White', 29.99, 42, 4.6),
    ('XXL', 'Blouse', 'Red', 29.99, 16, 4.6),
    ('XXL', 'Blouse', 'Lilac', 29.99, 60, 4.6),
    ('XXL', 'Blouse', 'Burgundy', 29.99, 42, 4.6),
    ('XXL', 'Blouse', 'Blue', 29.99, 16, 4.6),
    ('XXL', 'Blouse', 'Gray', 29.99, 16, 4.6),
    ('XL', 'Blouse', 'Black', 29.99, 60, 4.6),
    ('XL', 'Blouse', 'White', 29.99, 42, 4.6),
    ('XL', 'Blouse', 'Red', 29.99, 16, 4.6),
    ('XL', 'Blouse', 'Lilac', 29.99, 60, 4.6),
    ('XL', 'Blouse', 'Burgundy', 29.99, 42, 4.6),
    ('XL', 'Blouse', 'Blue', 29.99, 16, 4.6),
    ('XL', 'Blouse', 'Gray', 29.99, 16, 4.6), 
    ('L', 'Blouse', 'Black', 29.99, 60, 4.6),
    ('L', 'Blouse', 'White', 29.99, 42, 4.6),
    ('L', 'Blouse', 'Red', 29.99, 16, 4.6),
    ('L', 'Blouse', 'Lilac', 29.99, 60, 4.6),
    ('L', 'Blouse', 'Burgundy', 29.99, 42, 4.6),
    ('L', 'Blouse', 'Blue', 29.99, 16, 4.6),
    ('L', 'Blouse', 'Gray', 29.99, 16, 4.6),
    ('M', 'Blouse', 'Black', 29.99, 60, 4.6),
    ('M', 'Blouse', 'White', 29.99, 42, 4.6),
    ('M', 'Blouse', 'Red', 29.99, 16, 4.6),
    ('M', 'Blouse', 'Lilac', 29.99, 60, 4.6),
    ('M', 'Blouse', 'Burgundy', 29.99, 42, 4.6),
    ('M', 'Blouse', 'Blue', 29.99, 16, 4.6),
    ('M', 'Blouse', 'Gray', 29.99, 16, 4.6),
    ('S', 'Blouse', 'Black', 29.99, 60, 4.6),
    ('S', 'Blouse', 'White', 29.99, 42, 4.6),
    ('S', 'Blouse', 'Red', 29.99, 16, 4.6),
    ('S', 'Blouse', 'Lilac', 29.99, 60, 4.6),
    ('S', 'Blouse', 'Burgundy', 29.99, 42, 4.6),
    ('S', 'Blouse', 'Blue', 29.99, 16, 4.6),
    ('S', 'Blouse', 'Gray', 29.99, 16, 4.6),
    ('XS', 'Blouse', 'Black', 29.99, 60, 4.6),
    ('XS', 'Blouse', 'White', 29.99, 42, 4.6),
    ('XS', 'Blouse', 'Red', 29.99, 16, 4.6),
    ('XS', 'Blouse', 'Lilac', 29.99, 60, 4.6),
    ('XS', 'Blouse', 'Burgundy', 29.99, 42, 4.6),
    ('XS', 'Blouse', 'Blue', 29.99, 16, 4.6),
    ('XS', 'Blouse', 'Gray', 29.99, 16, 4.6);



*** Does the store have any Purple pants in a size 12 available in store? If so, how much do they cost?

    SELECT *
FROM FashionStore
WHERE item_category = 'Pants' AND item_color = 'Purple' AND item_size = '12';



*** Does your store have any items that are either size 16 or XXL in stock?

SELECT *
FROM FashionStore
WHERE item_size = '16' OR item_size = 'XXL';



*** Which item has the highest average rating and what is the rating?

SELECT item_category, MAX(average_rating)
FROM FashionStore
GROUP BY item_category;



*** What is the total amount of in stock pants and in stock blouses (Separate categories)?

SELECT item_category, SUM(stock_quantity) AS Total_Stock_Quantity
FROM FashionStore
WHERE item_category IN ('Pants', 'Blouse')
GROUP BY item_category;

