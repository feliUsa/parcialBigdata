# parcialBigdata

La empresa de alquiler de películas de Sakila desea desarrollar una arquitectura de datos de analítica usando los servicios de AWS. La empresa decidió tener tanto un sistema de datawarehouse en RDS  como un datalake en S3.
La empresa desea tener a mano y analizar la siguiente información:

* Alquileres de películas de los clientes.
* Comportamiento de los alquileres según las fechas.
* Comportamiento de los alquileres según día de la semana
* Categorías de las películas que más se alquilan
* Clientes que más alquilan



1. Diseñar un sistema dimensional que permita realizar los análisis anteriormente mencionados.(la dimensión Date debe tener día de la semana, si es festivo o no, fin de semana, trimestre)
   
2. Implementar el modelo en MYSQL( este no es un motor que se suela usar para este propósito pero para el problema es una solución aceptable). La BD se debe llamar datawarehouse_sakila.

3. Poblar la bd con los datos actuales de Sakila.

4. Realizar las respectivas consultas que permitan analizar la información descrita.

5. Usando AWS Lambda que se activa a diario y simule la renta de nuevas películas por parte de 100 clientes cada dia. Los clientes y las películas se deben seleccionar de acuerdo con las respectivas distribuciones de probabilidad (entre más haya alquilado un cliente, este es más probable que alquile. Entre más se haya alquilado una película, más probabilidad tiene de que se alquile).

6. Escribir un job(con lambda o glue) que mantenga actualizada la dimensión Date ( ya sea mensual o anualmente.  Se puede alimentar a través de un api o de una biblioteca.

7. Crear los respectivos ETL que copien a diario de la base de datos transaccional de sakila a s3 y posteriormente a la bd datawarehouse.

8. Los datos parciales deben quedar en S3 en una carpeta stage o landing. Los datos finales en una carpeta final.

9. Implementar el modelo dimensional en un datalake en s3 particionado por día.

10. Crear en Quicksight los respectivos reportes que permitan analizar la información de la empresa. 

11. Crear un workflow de glue que articule los ETL y los cralwer(para mantener los catálogos actualizados).

** Toda la arquitectura debe tener despliegue continuo con pruebas unitarias.(Los jobs son archivos en s3. Todo se puede crear utilizando boto3).

