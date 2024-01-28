# zomoto
 --1 what is  total  amount  each  customer spend on zomoto?

 --select sum(p.price) as total_price,s.userid from product p join sales s on p.product_id=s.product_id
 --group by s.userid 

 --2. how many days has  each customer visited zomato?

-- select userid, count(distinct created_date)as visited_date from sales group by userid

--3. what was the first product purchesed by each customer?
select * from 
(select * ,rank() over (partition by userid order by created_date)as rnk from sales)a
where rnk=1


