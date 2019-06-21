---
title: "PostgreSQL"
date: 2019-06-20T23:43:31Z
categories: ["SQL"]
draft: true
---

#### **Joins**
* inner Join

	``` sql
	select prices.*, quantity.quantity from prices inner join quantity on  prices.Product = quantity.Product;
	```
* left outer join\

	``` sql
	select prices.*, quantity.quantity from prices left outer join quantity on prices.product = quantity.product;
	```
* right outer join

	``` sql
	select prices.*, quantity.quantity from prices right outer join quantity on prices.product = quantity.product;
	```
* full outer join

	``` sql
	select prices.*, quantity.quantity from prices full outer join quantity on prices.product = quantity.product;
	```

* Cases
	``` sql
	SELECT OrderID, Quantity,
	CASE
	    WHEN Quantity > 30 THEN "The quantity is greater than 30"
	    WHEN Quantity = 30 THEN "The quantity is 30"
	    ELSE "The quantity is under 30"
	END AS QuantityText
	FROM OrderDetails;
	```
	``` 
	-- Output --
	OrderID  |  Quantity  | QuantityTest   |
	123      |     43     | The quantity is greater than 30  |
	
	``` 
	 
	 
	