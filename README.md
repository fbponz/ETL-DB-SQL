<img align="center" width="270" height="136" src="http://www.gepacv.org/wp-content/uploads/2017/01/EDEM-Logo--540x272.png">

### Master en Data Analytics para la Empresa

#### Asignatura tratamiento integral del dato

- Alumno:  [Fco de Borja Ponz](https://github.com/fbponz)
- Docente: [Pedro Nieto](https://github.com/a10pepo)

#### Enunciado entrega 1, Talend:

##### Ejercicio 1) Debéis leer un fichero CSV y escribirlo a fichero Json en la misma carpeta

Esquema de componentes utilizados para la realización del ejercicio.

![ETL_1](./Talend/resources/ETL_1.png)

Configuración de componente para importación de datos desde fichero CSV.

![ETL_1](./Talend/resources/ETL_2.png)

configuración del componente de exportación hacia fichero JSON.

![ETL_1](./Talend/resources/ETL_3.png)

##### Ejercicio 2) Debéis leer un fichero CSV y reemplazar: MALE-> M y FEMALE-> F

Esquema de componentes utilizados para la realización del ejercicio.

![ETL_1](./Talend/resources/ETL_4.png)

Configuración de componente para importación de datos desde fichero CSV.

![ETL_1](./Talend/resources/ETL_5.png)

Configuración del componente tReplace

![ETL_1](./Talend/resources/ETL_6.png)

Configuración para exportar a fichero json

![ETL_1](./Talend/resources/ETL_7.png)

##### Ejercicio 3)Leer tabla de actores y volcarlo a fichero JSON

Esquema de módulos utilizados para la realización del ejercicio.

![ETL_1](./Talend/resources/ETL_8.png)

Configuración del componente, que realiza la conexión entre la base de datos y Talend, en este caso tabla Actor.

![ETL_1](./Talend/resources/ETL_9.png)

Configuración para exportar a fichero json

![ETL_1](./Talend/resources/ETL_10.png)

##### Ejercicio 4) Agregar las películas por rating y mostrar un count, volcar a json el resultado

Esquema de módulos utilizados para la realización del ejercicio

![ETL_1](./Talend/resources/ETL_11.png)

Configuración del componente, que realiza la conexión entre la base de datos y Talend, en este caso tabla film.

![ETL_1](./Talend/resources/ETL_12.png)

Configuración componente que se encarga de generar la información que queremos por un lado devolver el rating de la película y por otro la operación de contar el total de películas con una rating concreto

![ETL_1](./Talend/resources/ETL_13.png)

Configuración para exportar a fichero json

![ETL_1](./Talend/resources/ETL_14.png)

##### Ejercicio 5) Realizar un Join entre Actor / Film / Film_Actor y volcar a json un fichero con estos campos: Nombre, Apellido y Película

Esquema de módulos utilizados para la realización del ejercicio

![ETL_1](./Talend/resources/ETL_15.png)

Configuración del componente, que realiza la conexión entre la base de datos y Talend, en este caso tabla actor

![ETL_1](./Talend/resources/ETL_16.png)

Configuración del componente, que realiza la conexión entre la base de datos y Talend, en este caso tabla film

![ETL_1](./Talend/resources/ETL_17.png)

Configuración del componente, que realiza la conexión entre la base de datos y Talend, en este caso tabla film_actor

![ETL_1](./Talend/resources/ETL_18.png)

La configuración de t_map

![ETL_1](./Talend/resources/ETL_19.png)

Configuración para exportar a fichero json

![ETL_1](./Talend/resources/ETL_20.png)

##### Ejercicio 6) Cargar una tabla con la cantidad de dinero Gastada por usuario, nombre y apellido: 

Esquema de módulos utilizados para la realización del ejercicio

![ETL_1](./Talend/resources/ETL_21.png)

Configuración del componente, que realiza la conexión entre la base de datos y Talend, en este caso tabla customer

![ETL_1](./Talend/resources/ETL_22.png)

Configuración del componente, que realiza la conexión entre la base de datos y Talend, en este caso tabla payment

![ETL_1](./Talend/resources/ETL_23.png)

La configuración de t_map

![ETL_1](./Talend/resources/ETL_24.png)

El componente agreggate_row

![ETL_1](./Talend/resources/ETL_25.png)

Configuración del componente, que realiza la conexión entre la base de datos y Talend, en este caso tabla Expenditures

![ETL_1](./Talend/resources/ETL_26.png)

Este ejercicio lo he resuelto también escribiendo directamente en la base datos

![ETL_1](./Talend/resources/ETL_27.png)

##### Ejercicio 7) Cargar una tabla con el numero de veces que se ha alquilado cada película, solo con aquellas que han sido alquiladas al menos una vez

Esquema de módulos utilizados para la realización del ejercicio

![ETL_1](./Talend/resources/ETL_28.png)

Configuración del componente, que realiza la conexión entre la base de datos y Talend, en este caso tabla rental

![ETL_1](./Talend/resources/ETL_29.png)

Configuración del componente, que realiza la conexión entre la base de datos y Talend, en este caso tabla film

![ETL_1](./Talend/resources/ETL_30.png)

Configuración del componente, que realiza la conexión entre la base de datos y Talend, en este caso tabla inventory

![ETL_1](./Talend/resources/ETL_31.png)

La configuración de t_map

![ETL_1](./Talend/resources/ETL_32.png)

En el componente aggregateRow,  vamos a calcular el numero de veces que hemos alquilado una película

![ETL_1](./Talend/resources/ETL_33.png)

##### Ejercicio 8) Leer de Big Query de la tabla alumnos filtrando los que contengan un nombre en concreto

Esquema de módulos utilizados para la realización del ejercicio

![ETL_1](./Talend/resources/ETL_34.png)

Para conectar con Big-query vamos a utilizar una clave de Service Account

![ETL_1](./Talend/resources/ETL_35.png)

Como la query que hacemos a Big-query es 

![ETL_1](./Talend/resources/ETL_36.png)

![ETL_1](./Talend/resources/ETL_37.png)

#### Enunciado entrega 1, SQL:

##### 1. Proporciona una SQL que muestre los siguientes datos: Nombre Actor y Apellido Actor Query: 

    SELECT first_name, last_name 
    FROM public.actor

##### 2. Proporciona una SQL que muestre los siguientes datos: Nombre Actor y Titulo de la Película Query: 

        SELECT actor.first_name, film.title 
        FROM actor 
        JOIN film_actor ON actor.actor_id = film_actor.actor_id 
        JOIN film ON film_actor.film_id = film.film_id;

##### 3. Proporciona una SQL que muestre los siguientes datos: Nombre Actor, Número de películas, Ordenar de mayor a menor Query: 

        SELECT actor.first_name, COUNT(actor.first_name) 
        FROM actor JOIN film_actor ON actor.actor_id = film_actor.actor_id JOIN film ON film_actor.film_id = film.film_id 
        GROUP BY actor.first_name
        ORDER BY 2 DESC;

##### 4. Proporciona una SQL que muestre los siguientes datos: Película y Numero de veces alquilada Query: 

    SELECT film.title, COUNT(rental.rental_id) 
    FROM film 
    JOIN inventory ON film.film_id = inventory.film_id 
    JOIN rental ON inventory.inventory_id = rental.inventory_id 
    GROUP BY film.title
    ORDER BY 2 DESC;

##### 5. Proporciona una SQL que muestre los siguientes datos: Película y Dinero recaudado por película Query: 

    SELECT film.title, SUM(payment.amount) 
    FROM film 
    JOIN inventory ON film.film_id = inventory.film_id 
    JOIN rental ON inventory.inventory_id = rental.inventory_id 
    JOIN payment on rental.rental_id = payment.rental_id
    GROUP BY film.title
    ORDER BY 2 DESC;

##### 6. Proporciona una SQL que muestre los siguientes datos: Nombre del mejor cliente (mayor gasto) Query: 

    SELECT customer.first_name,
      SUM(payment.amount) AS total
    FROM customer
    JOIN payment ON customer.customer_id = payment.customer_id
    GROUP BY customer.first_name
    ORDER BY total DESC
    LIMIT 1;

##### 7. Proporciona una SQL que muestre los siguientes datos: Nombre del mejor cliente (mayor num alquileres) Query: 

    SELECT customer.first_name, COUNT(payment.amount) AS total
    FROM customer
    JOIN payment ON customer.customer_id = payment.customer_id
    GROUP BY customer.first_name
    ORDER BY total DESC
    LIMIT 1;
