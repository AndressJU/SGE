SISTEMA DE GESTION EMPRESARIAL
ACTIVIDAD 1

<--PRIMERO NOS CONECTADOS A LA DB DE empresa_afj con:
sudo su
su postgres
psql
Dentro de postgres hacemos:
\c empresa_afj





1. ¿Cuántas tablas hay en el esquema public?
 
SELECT COUNT(*)
FROM information_schema.tables
WHERE table_schema = 'public'
AND table_type = 'BASE TABLE';

2. ¿Qué prefijos ves que se repiten en los nombres de varias tablas?

SELECT table_name
FROM information_schema.tables
WHERE table_schema = 'public'
ORDER BY table_name;

<--Te aparecerá un listado de las 120 tablas.-->

3. ¿Qué propiedades tienen los usuarios postgres y odoo? 

\du

<--Aquí podrás visualizar los usuarios y sus permisos-->

Superuser: tiene todos los privilegios de administración.
Create role: puede crear y modificar usuarios y roles.
Create DB: puede crear bases de datos.
Replication: tiene permisos para realizar replicaciones.
Bypass RLS: puede ignorar las políticas de seguridad por filas.
odoo – Create DB: tiene permiso para crear bases de datos.




4. ¿Qué usuario es el propietario de las tablas?


SELECT tablename, tableowner
FROM pg_tables
WHERE schemaname = 'public';






