# FSDA_Asignment_PROJECT
# TASK 1

create database snowflake_PROJECT1
create table shopping_history(
    product varchar not null,
    quantity integer not null,
    unit_price integer not null
);

insert into shopping_history values    
('apple',5,10),
('banana',7,12),
('mango',2,25),
('apple',7,5),
('banana',3,7),
('mango',4,9),
('apple',7,11),
('cherry',6,2),
('papaya',4,13),
('cherry',7,17);

select * from shopping_history

select distinct product,sum(total_price)As TOTAL_PRICE from (select product,quantity*unit_price as total_price from shopping_history)group by product;

PRODUCT	TOTAL_PRICE
apple	162
banana	105
mango	86
cherry	131
papaya	52










