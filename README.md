```sql
DELIMITER //

USE world;

CREATE PROCEDURE citycount (IN country CHAR(3), OUT cities INT)
BEGIN
    SELECT COUNT(*) INTO cities FROM world.city
    WHERE CountryCode = country;
END //

DELIMITER ;

CALL citycount('ESP', @cities);
SELECT @cities;
SELECT * FROM city;

SELECT * FROM country;

```
