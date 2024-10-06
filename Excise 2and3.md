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
