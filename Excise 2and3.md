# Database
## week3
### Exercise 2 (I checked with DataGrip)
#### Kysymys 1




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

