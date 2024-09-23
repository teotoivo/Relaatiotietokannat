# Yhteen tauluun kohdistuvien kyselyiden harjoittelu

1.

```sql
select * from goal;
```

![](image.png)

2.

```sql
select name from airport where iso_country='FI';
```

![alt text](image-1.png)

3.

```sql
select name from airport where iso_country='FI' order by name asc;
```

![alt text](image-2.png)

4.

```sql
select name, type from airport where iso_country='FI' order by type, name;
```

![alt text](image-3.png)

5.

````sql
SELECT name FROM country WHERE name LIKE 'F%';
```t

![alt text](image-4.png)

6.

```sql
SELECT name FROM country WHERE name LIKE '%F%';
````

![alt text](image-5.png)

7.

```sql
select iso_country from airport where name='Vesa';
```

![alt text](image-6.png)

8.

```sql
select co2_consumed from game where screen_name='Ilkka';
```

![alt text](image-7.png)

9.

```sql
select co2_budget from game limit 1;
```

![alt text](image-8.png)

# Where-osan liitosehto harjoitukset

1.

```sql
SELECT c.name AS "country name", a.name AS "airport name"
FROM country c
JOIN airport a ON c.iso_country = a.iso_country
WHERE c.name = 'Iceland';
```

![alt text](image-9.png)

2.

```sql
select a.name as 'airport name' from airport a join country c on c.iso_country = a.iso_country where c.name = 'France' and a.type = 'large_airport';
```

![alt text](image-10.png)

3.

```sql
 select c.name as 'country_name', a.name as 'airport_name' from airport a join country c on c.iso_country = a.iso_country where a.continent = 'AN';
```

![alt text](image-11.png)

4.

```sql
select a.elevation_ft from game g join airport a on g.location = a.ident where g.screen_name = 'Heini';
```

![alt text](image-12.png)

5.

```sql
select a.elevation_ft / 0.3048 as 'elevation_m' from game g join airport a on g.location = a.ident where g.screen_name = 'Heini';
```

![alt text](image-13.png)

6.

```sql
select a.name from game g join airport a on g.location = a.ident where g.screen_name = 'Ilkka';
```

![alt text](image-14.png)

7.

```sql
select c.name from game g join airport a on g.location = a.ident join country c on a.iso_country = c.iso_country where g.screen_name = 'Ilkka';
```

![alt text](image-15.png)

8.

```sql
select go.name from game ga join goal_reached gr on gr.game_id = ga.id join goal
 go on gr.goal_id = go.id where ga.screen_name = 'Heini';
```

![alt text](image-16.png)

9.

```sql
select airport.name from game join goal_reached on goal_reached.game_id = game.id join goal on goal_reached.goal_id = goal.id join airport on airport.ident = game.location where game.screen_name = 'Ilkka' AND goal.name = 'CLOUDS';
```

![alt text](image-17.png)

10.

```sql
select country.name from game join goal_reached on goal_reached.game_id = game.id join goal on goal_reached.goal_id = goal.id join airport on airport.ident = game.location join country on country.iso_country = airport.iso_country where game.screen_name = 'Ilkka' AND goal.name = 'CLOUDS';
```

![alt text](image-18.png)

# Join harjoitukset

1.

```sql
select country.name as 'country name', airport.name as 'airport name' from airport join country on airport.iso_country = country.iso_country where country.name = 'Finland' and airport.scheduled_service = 'yes';
```

![alt text](image-19.png)

2.

```sql
select game.screen_name, airport.name from game join airport on airport.ident = game.location;
```

![alt text](image-20.png)

3.

```sql
select game.screen_name, country.name from game join airport on airport.ident = game.location join country on country.iso_country = airport.iso_country;
```

![alt text](image-21.png)
