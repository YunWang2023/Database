# Database
## week3
### Exercise 2 (I checked with DataGrip)
#### Kysymys 1
select* from goal;

<img width="706" alt="Kysymys 1" src="https://github.com/user-attachments/assets/45cd2df1-dd52-4a3a-bdd9-354f157a7213">

#### Kysymys 2
select name, type from airport where iso_country = 'FI';

<img width="518" alt="Kysymys 2" src="https://github.com/user-attachments/assets/3805a650-5294-4399-a9b6-9995563a5e23">

#### Kysymys 3
elect name from airport where iso_country = 'FI' order by name;

<img width="591" alt="Kysymys 3" src="https://github.com/user-attachments/assets/057793cc-4bd1-4542-b57b-874d4d4b69e4">

#### Kysymys 4
select name, type from airport where iso_country = 'FI' order by type, name;

<img width="638" alt="Kysymys 4" src="https://github.com/user-attachments/assets/ae63bac3-b45a-4594-bd09-307857deb8e2">

#### Kysymys 5
select name from country where name like 'F%'; 

<img width="466" alt="Kysymys 5" src="https://github.com/user-attachments/assets/85138cc3-e30a-451f-b7b6-30f9e7fc64d2">

#### Kysymys 6
select name from country where name like '%F%';

<img width="453" alt="Kysymys 6" src="https://github.com/user-attachments/assets/e8513656-440a-42db-af43-9a3b3b56f4fe">

#### Kysymys 7
select location from game where screen_name = 'Vesa' ;

<img width="521" alt="Kysymys 7" src="https://github.com/user-attachments/assets/bac42cdf-34a7-4ca5-b632-79590e772247">

#### Kysymys 8
select co2_consumed from game where screen_name = 'Ilkka';

<img width="544" alt="Kysymys 8" src="https://github.com/user-attachments/assets/83ffa49c-9b58-476b-a8e7-1be472bd1840">

#### Kysymys 9
select distinct co2_budget from game; 

<img width="420" alt="Kysymys 9" src="https://github.com/user-attachments/assets/d3f3bfec-261a-4576-a427-a065f2e47dc7">

#### Kysymys 10
SELECT screen_name, co2_budget, co2_consumed, @co2_left := (co2_budget - co2_consumed) AS co2_left FROM game WHERE screen_name = 'Ilkka';

<img width="1130" alt="Kysymys 10" src="https://github.com/user-attachments/assets/c7d6332a-bf52-4b85-a292-6d25ede93627">


## week3
### Exercise 3 (I checked with DataGrip)
#### Kysymys 1
select country.name as "country name", airport.name as "airport name"
from airport, country
where airport.iso_country = country.iso_country and country.name = 'Iceland';

<img width="706" alt="Kysymys 1" src="https://github.com/user-attachments/assets/c7b7448e-44ea-4c22-bafd-0cbf0d468e4f">

#### Kysymys 2
select airport.name as "airport name"
from airport, country
where airport.iso_country = country.iso_country and country.name
    = 'France' and airport.type = 'large_airport';
    
<img width="600" alt="Kysymys 2" src="https://github.com/user-attachments/assets/dcef1581-868b-4825-abf4-f279745bb13d">

#### Kysymys 3
select country.name as country_name, airport.name as airport_name
from airport, country
where airport.iso_country = country.iso_country and country.continent = 'AN'

<img width="693" alt="Kysymys 3" src="https://github.com/user-attachments/assets/c4a5ac6d-c763-4d19-a5df-b8f7690b5956">

#### Kysymys 4
select elevation_ft
from airport, game
where location = ident and screen_name = 'Heini';

<img width="512" alt="Kysymys 4" src="https://github.com/user-attachments/assets/66a4e149-a040-4996-8aa9-41c70a517365">

#### Kysymys 5
select elevation_ft * 0.3048 as elevation_m
from airport, game
where location = ident and screen_name = 'Heini';

<img width="488" alt="Kysymys 5" src="https://github.com/user-attachments/assets/83de16d4-2d35-4964-92b0-a32dd641cf6d">

#### Kysymys 6
select name
from airport, game
where location = ident and screen_name = 'Ilkka';

<img width="504" alt="Kysymys 6" src="https://github.com/user-attachments/assets/020dc2ee-bcdc-492b-8dbc-49f66ff61214">

#### Kysymys 7
select country.name
from airport, game, country
where location = ident and airport.iso_country = country.iso_country  and screen_name = 'Ilkka';

<img width="843" alt="Kysymys 7" src="https://github.com/user-attachments/assets/06811e48-a01c-4586-baad-71fa109cb216">

#### Kysymys 8
select name
from goal, goal_reached, game
where game.id = game_id and goal.id = goal_id and screen_name = 'Heini';

<img width="679" alt="Kysymys 8" src="https://github.com/user-attachments/assets/058e7c25-3b36-4f86-a9da-742468790dc2">

#### Kysymys 9
select airport.name
from airport, game, goal, goal_reached
where ident = location and game.id = game_id and goal.id = goal_id and screen_name = 'Ilkka' and goal.name = 'CLOUDS';

<img width="949" alt="Kysymys 9" src="https://github.com/user-attachments/assets/29b05f84-fa77-4950-be6c-0775ee21996e">

#### Kysymys 10
select country.name
from country, airport, game, goal, goal_reached
where airport.iso_country = country.iso_country and ident = location and
      game.id = game_id and goal.id = goal_id and screen_name = 'Ilkka' and goal.name = 'CLOUDS';
      
<img width="812" alt="Kysymys 10" src="https://github.com/user-attachments/assets/146193ad-e91a-414a-845b-2d50510658ff">

## week4
### Exercise 4 (I checked with DataGrip)
#### Kysymys 1
select country.name as "country name", airport.name as "airport name"
from country inner join airport on airport.iso_country = country.iso_country
where country.name = "Finland" and scheduled_service = "yes";
![Kysymys 1](https://github.com/user-attachments/assets/d15a98e6-fe26-45dd-b704-c5bd74470461)


#### Kysymys 2
select screen_name, airport.name
from game inner join airport on location = ident;
![Kysymys 2](https://github.com/user-attachments/assets/1303a26e-bbbe-408f-96fb-be6b883726a7)


#### Kysymys 3
select screen_name, country.name
from game inner join airport on location =
     ident inner join country on airport.iso_country = country.iso_country;
![Kysymys 3](https://github.com/user-attachments/assets/ec84c530-4dd9-4cd8-ad1c-2639d29417e4)


#### Kysymys 4
select airport.name, screen_name
from airport left join game on ident = location where name like "%Hels%";
![Kysymys 4](https://github.com/user-attachments/assets/71b73237-a874-4e48-97d4-bd2746377f92)


#### Kysymys 5
select name, screen_name
from goal left join goal_reached on goal.id = goal_id  left join game on game.id = game_id;
![Kysymys 5](https://github.com/user-attachments/assets/c687cef3-621a-440f-bba0-a45abb4e0ba0)

## week4
### Exercise 5 (I checked with DataGrip)
#### Kysymys 1
select name
from country
where iso_country in(
select iso_country
from airport
where name like 'Satsuma%'
);
![1](https://github.com/user-attachments/assets/d5866f65-1ce9-4358-b16d-4a4b4716b583)


#### Kysymys 2
select name
from airport where
iso_country in(
select iso_country
from country
where name = 'Monaco'
);
![2](https://github.com/user-attachments/assets/f37600e2-3291-4b9e-8bb5-3de5f2a23239)


#### Kysymys 3
select screen_name
from game
where id in (
select game_id
from goal_reached
where goal_id in(
select id
from goal
where name = 'CLOUDS'
)
);
![3](https://github.com/user-attachments/assets/3acd8b6b-6450-4280-892f-80a69cfaca0d)


#### Kysymys 4
select country.name
from country
where iso_country not in
(select airport.iso_country
from airport);
![4](https://github.com/user-attachments/assets/e85026d4-d149-41a0-9817-0e774998b78d)


#### Kysymys 5
select name
from goal
where id not in(
select goal.id
from goal, goal_reached, game
where game.id = game_id and goal.id = goal_id and screen_name = 'Heini'
);
![5](https://github.com/user-attachments/assets/f95171b3-3478-47f0-87d6-a91934197ae5)

## week5
### Exercise 6 (I checked with DataGrip)
#### Kysymys 1
select max(elevation_ft)
from airport;
![1](https://github.com/user-attachments/assets/7d9fd6f8-0775-486c-b6bd-fa6ff37b496a)


#### Kysymys 2
select continent, count(*)
from country
group by continent;
![2](https://github.com/user-attachments/assets/deabca31-1d57-4ea6-82c4-a4496dcc8ce2)

#### Kysymys 3
select screen_name, count(*)
from game, goal_reached
where id = game_id
group by screen_name;
![3](https://github.com/user-attachments/assets/dbf97aa9-7541-45a3-8bf5-6436a99d2e7e)

#### Kysymys 4
select screen_name
from game
where co2_consumed in(
select min(co2_consumed)
from game
);
![4](https://github.com/user-attachments/assets/6b963427-6d56-4a74-9e33-825c82b0c6e6)

#### Kysymys 5
select country.name, count(*)
from airport, country
where airport.iso_country = country.iso_country
group by country.iso_country
order by count(*) desc
limit 50;
![5](https://github.com/user-attachments/assets/dbdb6b9a-5074-49ab-8c3d-6e3fd8d2bf49)

#### Kysymys 6
select country.name
from airport, country
where airport.iso_country = country.iso_country
group by country.iso_country
having count(*) > 1000;
![6](https://github.com/user-attachments/assets/d92908d7-4bae-4330-84b2-2093082f07b5)

#### Kysymys 7
	
select name
from airport
where elevation_ft in (
select max(elevation_ft)
from airport
);
![7](https://github.com/user-attachments/assets/d304a86a-1027-4002-82e7-5738d82cab30)

#### Kysymys 8
	
select name
from country
where iso_country in (
select iso_country
from airport
where elevation_ft in(
select max(elevation_ft)
from airport
)
);
![8](https://github.com/user-attachments/assets/b18ee95b-489e-4d0e-bb3b-bc14bf85ab2f)

#### Kysymys 9
	
select count(*)
from game, goal_reached
where id = game_id and screen_name = "Vesa"
group by screen_name;
![9](https://github.com/user-attachments/assets/0e59b24b-6243-48ca-9e17-fba08e120ef1)

#### Kysymys 10
select name
from airport
where latitude_deg in(
select min(latitude_deg)
from airport
);
![10](https://github.com/user-attachments/assets/1f8c8695-8612-4e91-a3ad-1844534a760a)

## week5
### Exercise 7 (I checked with DataGrip)
#### Kysymys 1
update game
set  location = (select ident from airport where name = "Nottingham Airport"), co2_consumed = co2_consumed+500
where screen_name = "Vesa";
select * from game;
![1](https://github.com/user-attachments/assets/53d7a365-be7c-4393-bf7c-fe1a09376963)

#### Kysymys 2

#### Kysymys 3
delete from goal_reached;
select * from goal_reached;

![3](https://github.com/user-attachments/assets/8ee87770-5254-4dde-8633-7e93360f6e0d)

#### Kysymys 4
delete from game;
select * from game
![4](https://github.com/user-attachments/assets/9fdc1293-aaa0-40de-9995-29c6e2724c57)

## week1 of Software2
### Exercise 8 (I checked with DataGrip)
#### Kysymys 1

