# Comandos de MariaDB: simular unha GUI

**Nota inicial**: todos os exemplos deste documento pertencen á [web oficial de MariaDB](https://mariadb.com/kb/es/comandos-sql/) e á táboa `naves_espaciais`.

Os seguintes comandos permiten ver a estrutura e datos dunha BD simulando unha GUI na ventana de comandos.

## DESCRIBE
`DESCRIBE` proporciona información sobre as columanas dunha táboa. 

Sintaxis:

```SQL
	{DESCRIBE | DESC} tbl_name [col_name | wild];
```
*ej de naves*

## EXPLAIN
`EXPLAIN` pode ser usado como un sinónimo de `DESCRIBE` ou coma una forma de obter información sobre como MariaDB executa una instrución `SELECT`.

Sintaxis:
```SQL
	 EXPLAIN tbl_name;
```
*ej de naves*

## SHOW
O comando `SHOW` ten unha gran cantidad de formas que proporcionan información sobre bases de datos, táboas, columnas ou información sobre o estado do servidor. Algunhas delas son:

### SHOW DATABASES 
`SHOW DATABASES` lista todas as BD creadas no servidor de MariaDB. Seu sinónimo é `SHOW SCHEMAS`.

Sintaxis: 
```SQL
	SHOW {DATABASES | SCHEMAS}
    		[LIKE 'pattern' | WHERE expr];
```
*ej de mariadb*

### SHOW CREATE DATABASE 
`SHOW CREATE DATABASE` mostra a declaración de `CREATE DATABASE` que crea a base de datos dada. Seu sinónimo é `SHOW CREATE SCHEMA`.

Sintaxis:
```SQL
	SHOW CREATE {DATABASE | SCHEMA} db_name;
```
*ej de naves*

### SHOW TABLES
`SHOW TABLES` lista todas as táboas dunha BD determinada.

Sintaxis: 
```SQL
	SHOW [FULL] TABLES [FROM db_name]
   	 [LIKE 'pattern' | WHERE expr];
```
*ej de naves*

### SHOW CREATE TABLE
`SHOW CREATE TABLE` mostra a declaración de `CREATE TABLE` que crea a táboa dada.

Sintaxis:
```SQL
	SHOW CREATE TABLE tbl_name;
```
*ej de naves*

### SHOW TABLE STATUS
`SHOW TABLE STATUS` funciona como `SHOW TABLES` pero proporciona información máIs extensa sobre cada táboa.

Sintaxis:
```SQL
	SHOW TABLE STATUS [{FROM | IN} db_name]
 	   [LIKE 'pattern' | WHERE expr];
```
*ej de mariadb?*

### SHOW COLUMNS
`SHOW COLUMNS` mostra información sobre as columnas dunha táboa determinada. 

Sintaxis:
```SQL
	SHOW [FULL] {COLUMNS | FIELDS} FROM tbl_name [FROM db_name]
   	 [LIKE 'pattern' | WHERE expr];
```
*ej de naves*

### SHOW VARIABLES
`SHOW VARIABLES` mostra os valores das variables do sistema MariaDB.

Sintaxis:
```SQL
	SHOW [GLOBAL | SESSION] VARIABLES
   	 [LIKE 'pattern' | WHERE expr];
```
*ej de mariadb*

### SHOW WARNINGS
`SHOW WARNINGS` mostra as mensaxes de error, advertencia(**warning**) e nota que resultaron da útlima declaración que xenerou mensaxes. Non mostra nada se a última declaración utilizou unha táboa e no xenerou ningunha mensaxe. Poden contarse o número de warnings co comando `SHOW COUNT(*) WARNINGS`.

Sintaxis:
```SQL
	SHOW WARNINGS [LIMIT [offset,] row_count];
	SHOW COUNT(*) WARNINGS;
```
*ej de mariadb - division by zero*

### SHOW ERRORS
A diferenza de `SHOW WARNINGS`, `SHOW ERRORS` só móstra os erros resultantes da última declaración. Poden contarse a cantidade de erros co comando `SHOW COUNT(*) ERRORS`.

Sintaxis:
```SQL
	SHOW ERRORS [LIMIT [offset,] row_count];
	SHOW COUNT(*) ERRORS;  
```
*ej de mariadb*

### SHOW OPEN TABLES
`SHOW OPEN TABLES`  lista as táboas que están actualmente abiertas na caché.

Sintaxis:
```SQL
	SHOW OPEN TABLES [FROM db_name]
    	    [LIKE 'pattern' | WHERE expr];
```
*ej de naves?*

## HELP
`HELP` é usado para conseguir axuda básica coa sintaxis e unha breve descrición da maioría de comandos e funcións. Podemos escribir un texto de búsqueda concreto, ou usar `HELP contents` para ver o listado de categorías de axuda.

Sintaxis: 
```SQL
	HELP algo; (p ej create)
	HELP contents
```
