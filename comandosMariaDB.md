
# Comandos de MariaDB: simular una GUI

Nota inicial: todos os exemplos deste documento fan referencia a algúns da web oficial de MariaDB e á táboa `naves_espaciais`.

DESCRIBE = proporciona información sobre las columanas de una tabla.
Sintaxis:
	{DESCRIBE | DESC} tbl_name [col_name | wild];
*ej de naves*

EXPLAIN = puede ser usado como un sinónimo de `DESCRIBE` o como una forma de obtener información sobre cómo MariaDB ejecuta una instrucción `SELECT`.
Sintaxis:
	 EXPLAIN tbl_name;
*ej de naves*

---------SHOW------------

SHOW DATABASES = lista todas las BD creadas en el servidor de MariaDB. Su sinónimo es SHOW SCHEMAS.
Sintaxis: 
	SHOW {DATABASES | SCHEMAS}
    		[LIKE 'pattern' | WHERE expr];
*ej de mariadb*

SHOW CREATE DATABASE = muestra la declaración de `CREATE DATABASE` que crea la base de datos dada. Su sinónimo es `SHOW CREATE SCHEMA`.
Sintaxis:
	SHOW CREATE {DATABASE | SCHEMA} db_name;
*ej de naves*

SHOW TABLES = lista todas las tablas de una BD determinada.
Sintaxis: 
	SHOW [FULL] TABLES [FROM db_name]
   	 [LIKE 'pattern' | WHERE expr];
*ej de naves*

SHOW CREATE TABLE = muestra la declaración de `CREATE TABLE` que crea la tabla dada.
Sintaxis:
	SHOW CREATE TABLE tbl_name;
*ej de naves*

SHOW TABLE STATUS = funciona como `SHOW TABLES` pero proporciona información más extensa sobre cada tabla.
Sintaxis:
	SHOW TABLE STATUS [{FROM | IN} db_name]
 	   [LIKE 'pattern' | WHERE expr];
*ej de mariadb?*

SHOW COLUMNS = muestra información sobre las columnas de una tabla determinada. 
Sintaxis:
	SHOW [FULL] {COLUMNS | FIELDS} FROM tbl_name [FROM db_name]
   	 [LIKE 'pattern' | WHERE expr];
*ej de naves*

SHOW VARIABLES = muestra los valores de las variables del sistema MariaDB.
Sintaxis:
	SHOW [GLOBAL | SESSION] VARIABLES
   	 [LIKE 'pattern' | WHERE expr];
*ej de mariadb*

SHOW WARNINGS = muestra los mensajes de error, advertencia(warning) y nota que resultaron de la útlima declaración que generó mensajes en la sesión actual. No muestra nada si la última declaración utilizó una tabla y no generó ningún mensaje. Pueden contarse el número de warnings con el comando `SHOW COUNT(*) WARNINGS`.
Sintaxis:
	SHOW WARNINGS [LIMIT [offset,] row_count];
	SHOW COUNT(*) WARNINGS;
*ej de mariadb - division by zero*

SHOW ERRORS =  a diferencia de `SHOW WARNINGS`, sólo muestra los errores. Pueden contarse la cantidad de errores con el comando `SHOW COUNT(*) ERRORS`
Sintaxis:
	SHOW ERRORS [LIMIT [offset,] row_count];
	SHOW COUNT(*) ERRORS;    
*ej de mariadb*

SHOW OPEN TABLES = lista las tablas que están actualmente abiertas en la caché.
Sintaxis:
	SHOW OPEN TABLES [FROM db_name]
    	    [LIKE 'pattern' | WHERE expr];
*ej de naves?*

SHOW TRIGGERS = lista

---HELP = se usa para conseguir ayuda básica con la sintaxis y una breve descripción de la mayoría de comandos y funciones. Podemos escribir un texto de búsqueda concreto, o usar `HELP contents` para ver el listado de categorías de ayuda.
Sintaxis: 
	HELP algo; (p ej create)
	HELP contents
