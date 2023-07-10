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


![image](https://github.com/Raju7646/FSDA_Asignment_PROJECT/assets/109983697/9d16f59c-743b-4362-9162-2d4921869c48)

![image](https://github.com/Raju7646/FSDA_Asignment_PROJECT/assets/109983697/dbb10660-b639-4c8f-b239-069f1afe8ba5)




task 2 


with call_duration as 
(
    select caller as phone_number ,sum(duration) as duration from calls group by caller
    union all
    select callee  as phone_number, sum(duration) as duration from calls group by callee
)
select name from phones P left outer join call_duration CD on P.phone_number=CD.phone_number
group by name
having sum(duration)>10
order by name;


output:-
name
anna
jack

<img width="604" alt="image" src="https://github.com/Raju7646/FSDA_Asignment_PROJECT/assets/109983697/8a1e39d5-7f4d-461c-9c0f-3f56d603106f">














