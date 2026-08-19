# sql-select-fundamentals

1. ¿Por qué es mala práctica usar SELECT * en producción?

Usar SELECT * en producción se considera una mala práctica porque trae todas las columnas de una tabla, incluso aquellas que no son necesarias. Esto puede afectar el rendimiento, especialmente cuando se trabaja con tablas grandes, ya que se procesan y transfieren más datos de los necesarios.

También afecta la mantenibilidad. Si en el futuro se agregan nuevas columnas a la tabla, SELECT * comenzará a devolverlas automáticamente, aunque la consulta original no las necesitara.

Además, puede representar un problema de seguridad, porque podría exponer columnas con información sensible que el usuario de la consulta no necesita ver.

Por eso, es preferible indicar específicamente las columnas:

SELECT customer_id, product_id, total_amount
FROM sales;

2. ¿Por qué son importantes los alias para un stakeholder no técnico?

Los alias permiten cambiar temporalmente el nombre con el que se muestra una columna para que sea más fácil de entender, sin modificar el nombre original en la base de datos.

Por ejemplo:

SELECT total_amount AS monto_total
FROM sales;

Para una persona de Finanzas, total_amount puede ser un nombre técnico o poco familiar, mientras que monto_total comunica inmediatamente qué información contiene la columna.

Esto hace que los resultados de las consultas sean más claros y fáciles de interpretar para personas que necesitan analizar los datos pero no necesariamente conocen la estructura técnica de la base de datos.
