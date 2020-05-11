
# Oracle BigDataSQL-HIVE

<br>

**A Customer Purchase Order History**



<br>
1. Connect to Database
````
<copy>
. oraenv
</copy>
````
````
<copy>
sqlplus apphdfs/apphdfs@orclpdb
</copy>
````
2. List purchase order history of customer 
````
<copy>
select * from orders_ext_hive o INNER JOIN order_items_ext_hive oi on o.order_id=oi.order_id 
INNER JOIN customer_hive_ext c on c.customer_id=o.customer_id inner join 
products_ext_hive p on oi.product_id=p.product_id where c.FULL_NAME='Dale Hughes';
</copy>
````
![](./Images/IMG4.PNG " ")


<br>

**Customers windows shopping  history ( through Online)**




1. Connect to **Database**
````
<copy>
.oraenv
</copy>
````
````
<copy>
sqlplus apphdfs/apphdfs@orclpdb
</copy>
````
2. List customers with **window shopping** history
````
<copy>
select * from orders_ext_hive o INNER JOIN customer_hive_ext c on o.customer_id=c.customer_id inner join stores_ext_hive s on s.store_id=o.store_id;
</copy>
````
![](./Images/IMG5.PNG)


<br>

**Customer who ordered some specific products**


1. Connect to **Database**
````
<copy>
.oraenv
</copy>
````
````
<copy>
sqlplus apphdfs/apphdfs@orclpdb
</copy>
````

2. List customers who ordered **specific products** 
````
<copy>
select * from orders_ext_hive o INNER JOIN order_items_ext_hive oi on o.order_id=oi.order_id 
INNER JOIN customer_hive_ext c on c.customer_id=o.customer_id inner join 
products_ext_hive p on oi.product_id=p.product_id where p.product_id=19;

</copy>
````

![](./Images/IMG6.PNG)
