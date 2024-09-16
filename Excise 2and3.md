# Database
## week3
### Exercise 3
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

