SISTEMA DE GESTION EMPRESARIAL

ACTIVIDAD 1



<--PRIMERO NOS CONECTADOS A LA DB DE empresa\_afj con:
sudo su

su postgres
psql
Dentro de postgres hacemos:
\\c empresa\_afj











##### **1. ¿Cuántas tablas hay en el esquema public?**

&#x20;

SELECT COUNT(\*)

FROM information\_schema.tables

WHERE table\_schema = 'public'

AND table\_type = 'BASE TABLE';



##### **2. ¿Qué prefijos ves que se repiten en los nombres de varias tablas?**



SELECT table\_name

FROM information\_schema.tables

WHERE table\_schema = 'public'

ORDER BY table\_name;



<--Te aparecerá un listado de las 120 tablas.-->



##### 3\. ¿Qué propiedades tienen los usuarios postgres y odoo? 



\\du

<--Aquí podrás visualizar los usuarios y sus permisos-->



Superuser: tiene todos los privilegios de administración.

Create role: puede crear y modificar usuarios y roles.

Create DB: puede crear bases de datos.

Replication: tiene permisos para realizar replicaciones.

Bypass RLS: puede ignorar las políticas de seguridad por filas.

odoo – Create DB: tiene permiso para crear bases de datos.









##### 4\. ¿Qué usuario es el propietario de las tablas?





SELECT tablename, tableowner

FROM pg\_tables

WHERE schemaname = 'public';























