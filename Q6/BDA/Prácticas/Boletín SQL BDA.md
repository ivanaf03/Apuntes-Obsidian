[[Bases de datos avanzadas]]
$\space$
## 1.Introducción

```sql
-- Ver SQL Plus bonito:

SET LINESIZE 120
SET PAGESIZE 100

SET HEADINGS ON
SET UNDERLINE '-'
SET SQLPROMPT "_user'@'_connect_identifier > "
```

```sql
-- Crea a taboa artigo con campos codart numeric(3), nomart varchar(20) e prezoart numeric(5,2). A clave primaria e codart.

create table artigo (
    codart numeric(3),
    nomart varchar(20),
    prezoart numeric(5,2),
    constraint pk_artigo primary key (codart)
);
```

```sql
-- Crea unha taboa venda. Ningun campo debe admitir nulos.

create table venda(
	idven number(6) not null,
	codart number(3) not null,
	prezoven number(5,2) not null,
	cantven number(3) not null,
	data date not null,
	constraint pk_venda primary key (idven),
	constraint fk_venda_codart foreign key (codart) references artigo (codart) on delete cascade
);
```

```sql
-- Crea unha secuencia de nome SEQ_ARTIGO.

create sequence seq_artigo;
```

```sql
-- Usa a secuencia para xenerar o codigo do artigo e inserta as filas para os produtos. Fai commit e comproba os valores.

insert into artigo (codart, nomart, prezoart) values (seq_artigo.nextval, 'Folios', 3.75);

insert into artigo (codart, nomart, prezoart) values (seq_artigo.nextval, 'Calculadora', 17.00);

insert into artigo (codart, nomart, prezoart) values (seq_artigo.nextval, 'Ordenador', null);

commit;

select * from artigo;
```

```sql
-- Crea unha vista de nome VART4 que obtena todos os datos dos artigos que teñan un prezo superior a 4.

create view vart4 as
select *
from artigo
where prezoart > 4
```
$\space$
## 2.Catálogo

```sql
-- A vista que almacena informacion sobre o propio catalogo de oracle e DICTIONARY ou o seu sinonimo DICT. Examina a sua estrutura e comproba se aparecen: USER_TABLES, ALL_TABLES e DBA_TABLES.

describe dict;

select * from dict where table_name='user_tables';
select * from dict where table_name='all_tables';
select * from dict where table_name='dba_tables';
-- Non mostran nada porque non teño permisos de DBA.
```

```sql
-- En Oracle podemos ver informacion sobre os obxectos do noso usuario mediante diversas vistas. Comproba as diferencias que hai entre: TAB, USER_TABLES/TABS e USER_CATALOG/CAT. Fai uso de DESCRIBE e SELECT para comprobalo.

describe tab;
describe tabs;
describe cat;

select * from tab;
select * from tabs:
select * from cat;
```

```sql
-- A vista USER_TAB_COLUMNS e o seu sinonimo COLS contenen informacion sobre as columnas. Obten mediante elas informacion sobre as columnas da taboa artigo.

column nome format a30 
column tipo format a20 
column "nulos?" format a10

select column_name as nome, data_type as tipo, nullable as "nulos?"
from cols
where table_name='ARTIGO';

/*
NOME                           TIPO                 nulos?
------------------------------ -------------------- ----------
CODART                         NUMBER               N
NOMART                         VARCHAR2             Y
PREZOART                       NUMBER               Y
*/
```

```sql
-- A vista USER_OBJECTS e o seu sinonimo OBJ almacenan informacion sobre os obxectos do usuario. Examina a estrutura desa vista e obten o nome e tipo dos teus obxectos.

 select object_name, object_type 
 from user_objects;
```
$\space$
## 3.Vistas

```sql
-- Inserta a fila (6,’Libro BD’, 1) a traves da vista ´ VART4. Que ocorre? Anula a transaccion.

insert into vart4 values(6, 'Libro', 1); -- Inserta a fila, tupla migratoria
rollback;
```

```sql
-- Cambia a vista VART4 que mostra os artigos de mais de 4 euros, de xeito que a vista impida insertar filas artigos que non cumpran esa restricion (non queremos filas migratorias), e comproba que efectivamente funciona tratando de insertar de novo a fila (6,’Libro BD’, 1).

create or replace view vart4 as
select *
from artigo
where prezoart > 4
with check option;

insert into vart4 values(6, 'Libro', 1);
/*
insert into vart4 values(6, 'Libro', 1)
            *
ERROR en línea 1:
ORA-01402: violación de la cláusula WHERE en la vista WITH CHECK OPTION
*/
```
$\space$
## 4.Restriccións

```sql
-- Asegurate de que as taboas artigo e venda non contenen ningunha fila. Engade unha restricion, de nome ch_art_prezo_pos que garanta que o prezo dos artigos e positivo. A restricion debe ser aplazable e inicialmente aplazada.

delete from artigo;

alter table artigo
add constraint ch_art_prezo_pos check (prezoart > 0)
deferrable initially deferred;
```

```sql
-- Confirma, buscando no catalogo, que a restricion esta correctamente creada.

select constraint_name, constraint_type, deferrable, deferred
from user_constraints
where constraint_name = 'CH_ART_PREZO_POS';
```

```sql
-- Para os seguintes exercicios, intenta explicar que e o que sucede e por que. Engade a fila (1, Folios, 3.75) a taboa artigo.

insert into artigo (codart, nomart, prezoart)
values (1, 'Folios', 3.75); -- Fila insertada
```

```sql
-- Confirma os cambios da transaccion actual.

commit;
```

```sql
-- Engade a fila (2, Pluma, 0).

insert into artigo (codart, nomart, prezoart)
values (2, 'Pluma', 0); -- Fila insertada
```

```sql
-- Confirma os cambios da transaccion actual.

commit;

/*
commit
*
ERROR en línea 1:
ORA-02091: transacción con rollback
ORA-02290: restricción de control (ivan.alvarez.fernandez.CH_ART_PREZO_POS) violada
*/
```

```sql
-- Inserta as filas seguintes: (2, Pluma, 80) e (3, Libreta, 0). Examina o as filas que hai en artigo.

select * from artigo;

/*
    CODART NOMART                 PREZOART
---------- -------------------- ----------
         1 Folios                     3,75
*/

insert into artigo (codart, nomart, prezoart)
values (2, 'Pluma', 80); -- Fila insertada

insert into artigo (codart, nomart, prezoart)
values (3, 'Libreta', 0); -- Fila insertada

select * from artigo;

/*
    CODART NOMART                 PREZOART
---------- -------------------- ----------
         1 Folios                     3,75
         3 Libreta                       0
         2 Pluma                        80
*/
```

```sql
Actualiza o prezo da Libreta a 3,20. Confirma os cambios.

update artigo
set prezoart = 3.20
where nomart = 'Libreta';

commit;

select * from artigo;

/*
    CODART NOMART                 PREZOART
---------- -------------------- ----------
         1 Folios                     3,75
         3 Libreta                     3,2
         2 Pluma                        80
*/
```

```sql
-- Crea unha taboa proba cun campo id de tipo int, clave primaria.

create table proba (
    id number(3),
    constraint pk_proba primary key (id)
);
```

```sql
-- Inserta en artigo a fila (4, Boli, 0.9). Inserta na taboa proba a fila (1). Inserta en artigo a fila (5, Calculadora, -3). Confirma os datos. Que ocorre? Hai datos en proba?

insert into artigo (codart, nomart, prezoart) values (4, 'Boli', 0.9);

insert into proba (id) values (1);

insert into artigo (codart, nomart, prezoart) values (5, 'Calculadora', -3);

commit;

select * from artigo;

/*
    CODART NOMART                 PREZOART
---------- -------------------- ----------
         1 Folios                     3,75
         3 Libreta                     3,2
         2 Pluma                        80
*/

select * from proba;
-- ninguna fila seleccionada
```

```sql
-- Repitamos o exercicio anterior, pero indicando antes que a restricion´ ch_art_prezo_pos se execute de forma inmediata.

set constraint ch_art_prezo_pos immediate;

insert into artigo (codart, nomart, prezoart) values (4, 'Boli', 0.9);

insert into proba (id) values (1);

insert into artigo (codart, nomart, prezoart) values (5, 'Calculadora', -3);

/*
insert into artigo (codart, nomart, prezoart) values (5, 'Calculadora', -3)
*
ERROR en línea 1:
ORA-02290: restricción de control (ivan.alvarez.fernandez.CH_ART_PREZO_POS) violada
*/

commit;

select * from artigo;

/*
    CODART NOMART                 PREZOART
---------- -------------------- ----------
         1 Folios                     3,75
         3 Libreta                     3,2
         2 Pluma                        80
         4 Boli                         ,9
*/

select * from proba;

/*
        ID
----------
         1
*/
```

```sql
-- O estandar SQL permite especificar, para as claves foraneas (so ten sentido para as compostas de varios atributos), a clausula MATCH, coas opcions SIMPLE, PARTIAL e FULL. Oracle non permite esta especificacion, pero o seu comportamento corresponde a unha desas 3 opcions. Averigua, creando taboas e insertando datos, a que opcion correponde.

create table maestra(
a int,
b int,
constraint pk_maestra primary key(a,b)
);

create table esclava(
c int,
a int,
b int,
constraint fk_maestra foreign key (a, b) references maestra(a, b)
);

insert into maestra values (1, 2);
insert into esclava values (101, 1, 2); -- Funciona
insert into esclava values (101, null, 2);  -- Funciona
insert into esclava values (101, null, null); -- Funciona
insert into esclava values (101, 3, 4); -- No funciona
```
$\space$
## 5.Papelera

```sql
-- Elimina por completo a taboa proba (tanto o contido como a definicion). Examina as tuas taboas usando TAB.

drop table proba;

select * from tab where tname='PROBA'; -- No aparece
```

```sql
-- Mira se hai algo na papeleira de reciclaxe. Restaura a taboa proba e examina de novo TAB.

select * from recyclebin where original_name = 'PROBA';

flashback table proba to before drop;

select * from tab where tname='PROBA'; -- Aparece
```

```sql
-- Elimina por completo a taboa proba (contido e definicion) de feito que desapareza (que non quede na papeleira). Podes facelo de duas formas distintas.

drop table proba purge; -- Primera forma

drop table proba; -- Segunda forma
purge recyclebin;
```
$\space$
## 6.Actividad

```sql
-- Oracle 19c implementa a clausula generated [always] as identity, que internamente usa unha secuencia e un trigger para xenerar valores para unha columna. Imos facelo manualmente: utiliza a secuencia seq_artigo e trata de crear un trigger para simular ese comportamento. Comproba que funciona.

create or replace trigger trg_artigo_id
before insert on artigo
for each row
begin
    if :new.id is null then
        select seq_artigo.nextval into :new.id from dual;
    end if;
end;
/

-- Funciona mal
```

```sql
-- Oracle non implementa a accion referencial ON UPDATE CASCADE, pero podemos simular esa accion utilizando un trigger. Crea un trigger para que a clave foranea de venda que referencia a artigo implemente a accion referencial de actualizacion en cascada.

create or replace trigger trg_artigo_on_update
before update on artigo
for each row
begin
    update venda
    set codart = :new.codart
    where codart = :old.codart;
end;
/
```
$\space$
## 7.Seguridad

```sql
-- Na base de datos de docencia estan creados os usuarios u1 e u2, ambos con clave como contrasinal. O teu usuario ten creada a taoba artigo. Da permisos o usuario u1 para seleccionar da taboa, coa potestade de pasarllo a outros.

grant select on artigo to u1 with grant option;
```

```sql
-- Comproba que u1 pode acceder a taboa. Fai que u1 otorgue o permiso de seleccion sobre a taboa artigo a u2. Comproba que u2 pode acceder.

-- Desde u1
 select * from "ivan.alvarez.fernandez".artigo;

/*
    CODART NOMART                 PREZOART
---------- -------------------- ----------
         1 Camiseta                      2
*/

grant select on "ivan.alvarez.fernandez".artigo to u2 with grant option;

-- Desde u2
select * from "ivan.alvarez.fernandez".artigo;

/*
    CODART NOMART                 PREZOART
---------- -------------------- ----------
         1 Camiseta                      2
*/
```

```sql
-- Fai que o teu usuario revoque o privilexio a u2. Que ocorre?

revoke select on artigo from u2;

/*
ERROR en línea 1:
ORA-01927: no se puede revocar (REVOKE) privilegios que no se han otorgado
*/
```

```sql
-- Fai que o teu usuario revoque o privilexio a U1. Que ocorre?

revoke select on artigo from u1; -- Se elimina en cascada el permiso

-- En u2
select * from "ivan.alvarez.fernandez".artigo;

/*                    
ERROR en línea 1:
ORA-00942: la tabla o vista no existe
*/
```
$\space$
## 8.Optimización

```sql
-- Obten o plan de execucion para a consulta que mostra todos os datos de todos os empregados. Utiliza tanto explain plan como set autotrace. Revisa as diferencias entre ambas aproximacions.

explain plan for
select * from emp; -- No ejecuta la consulta

select * from table(dbms_xplan.display);

/*
--------------------------------------------------------------------------
| Id  | Operation         | Name | Rows  | Bytes | Cost (%CPU)| Time     |
--------------------------------------------------------------------------
|   0 | SELECT STATEMENT  |      |    14 |   532 |     3   (0)| 00:00:01 |
|   1 |  TABLE ACCESS FULL| EMP  |    14 |   532 |     3   (0)| 00:00:01 |
--------------------------------------------------------------------------
*/

set autotrace traceonly explain;

select * from emp; -- Ejecuta la consulta

/*
--------------------------------------------------------------------------
| Id  | Operation         | Name | Rows  | Bytes | Cost (%CPU)| Time     |
--------------------------------------------------------------------------
|   0 | SELECT STATEMENT  |      |    14 |   532 |     3   (0)| 00:00:01 |
|   1 |  TABLE ACCESS FULL| EMP  |    14 |   532 |     3   (0)| 00:00:01 |
--------------------------------------------------------------------------
*/
```

```sql
-- Mostra o plan de execucion para a consulta que selecciona todos os datos do empregado 7902.

select * from emp where empno=7902;

/*
--------------------------------------------------------------------------------------
| Id  | Operation                   | Name   | Rows  | Bytes | Cost (%CPU)| Time     |
--------------------------------------------------------------------------------------
|   0 | SELECT STATEMENT            |        |     1 |    38 |     1   (0)| 00:00:01 |
|   1 |  TABLE ACCESS BY INDEX ROWID| EMP    |     1 |    38 |     1   (0)| 00:00:01 |
|*  2 |   INDEX UNIQUE SCAN         | PK_EMP |     1 |       |     0   (0)| 00:00:01 |
--------------------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   2 - access("EMPNO"=7902)
*/
```

```sql
-- Fai o mesmo, pero forza a que se utilize unha exploracion completa da taboa emp. Revisa as diferencias co plan do exercicio anterior. Fixate especialmente na informacion sobre os predicados.

select /*+ full(emp) */ * from emp where empno = 7902; -- Sin alias

/*
--------------------------------------------------------------------------
| Id  | Operation         | Name | Rows  | Bytes | Cost (%CPU)| Time     |
--------------------------------------------------------------------------
|   0 | SELECT STATEMENT  |      |     1 |    38 |     3   (0)| 00:00:01 |
|*  1 |  TABLE ACCESS FULL| EMP  |     1 |    38 |     3   (0)| 00:00:01 |
--------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   1 - filter("EMPNO"=7902)
*/

select /*+ full(e) */ * from emp e where empno = 7902; -- Con alias fuerza el hint

/*
--------------------------------------------------------------------------
| Id  | Operation         | Name | Rows  | Bytes | Cost (%CPU)| Time     |
--------------------------------------------------------------------------
|   0 | SELECT STATEMENT  |      |     1 |    38 |     3   (0)| 00:00:01 |
|*  1 |  TABLE ACCESS FULL| EMP  |     1 |    38 |     3   (0)| 00:00:01 |
--------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   1 - filter("EMPNO"=7902)
*/
```

```sql
-- Aında que a consulta pareza absurda, busca os codigos dos empregados 7902, 7839 e 5432 (obten so o campo empno, para verificar cales deles existen). Mostra o plan de execucion

select empno from emp where empno in (7902, 7839, 5432);

/*
-----------------------------------------------------------------------------
| Id  | Operation          | Name   | Rows  | Bytes | Cost (%CPU)| Time     |
-----------------------------------------------------------------------------
|   0 | SELECT STATEMENT   |        |     2 |     8 |     1   (0)| 00:00:01 |
|   1 |  INLIST ITERATOR   |        |       |       |            |
|
|*  2 |   INDEX UNIQUE SCAN| PK_EMP |     2 |     8 |     1   (0)| 00:00:01 |
-----------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   2 - access("EMPNO"=5432 OR "EMPNO"=7839 OR "EMPNO"=7902)
*/
```

```sql
-- E que pasa se queremos obter todos os codigos de empregado?

select empno from emp;

/*
---------------------------------------------------------------------------
| Id  | Operation        | Name   | Rows  | Bytes | Cost (%CPU)| Time     |
---------------------------------------------------------------------------
|   0 | SELECT STATEMENT |        |    14 |    56 |     1   (0)| 00:00:01 |
|   1 |  INDEX FULL SCAN | PK_EMP |    14 |    56 |     1   (0)| 00:00:01 |
---------------------------------------------------------------------------
*/
```

```sql
-- Busca agora o codigo e salario do empregado “SMITH”. Mostra o plan.

select empno, sal from emp where ename = 'SMITH';

/*
--------------------------------------------------------------------------
| Id  | Operation         | Name | Rows  | Bytes | Cost (%CPU)| Time     |
--------------------------------------------------------------------------
|   0 | SELECT STATEMENT  |      |     1 |    14 |     3   (0)| 00:00:01 |
|*  1 |  TABLE ACCESS FULL| EMP  |     1 |    14 |     3   (0)| 00:00:01 |
--------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   1 - filter("ENAME"='SMITH')
*/
```

```sql
-- Repite o exercicio anterior, pero antes crea un ´ındice sobre o campo ename de emp

create index idx_ename on emp(ename);
select empno, sal from emp where ename = 'SMITH';

/*
-------------------------------------------------------------------------------------------------
| Id  | Operation                           | Name      | Rows  | Bytes | Cost (%CPU)| Time |
-------------------------------------------------------------------------------------------------
|   0 | SELECT STATEMENT                    |           |     1 |    14 |     2   (0)| 00:00:01 |
|   1 |  TABLE ACCESS BY INDEX ROWID BATCHED| EMP       |     1 |    14 |     2   (0)| 00:00:01 |
|*  2 |   INDEX RANGE SCAN                  | IDX_ENAME |     1 |       |     1   (0)| 00:00:01 |
-------------------------------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   2 - access("ENAME"='SMITH')
*/
```

```sql
-- Obten agora todos os nomes dos empregados. Discute por que utiliza ou non o ındice.

select ename from emp;

/*
--------------------------------------------------------------------------
| Id  | Operation         | Name | Rows  | Bytes | Cost (%CPU)| Time     |
--------------------------------------------------------------------------
|   0 | SELECT STATEMENT  |      |    14 |    84 |     3   (0)| 00:00:01 |
|   1 |  TABLE ACCESS FULL| EMP  |    14 |    84 |     3   (0)| 00:00:01 |
--------------------------------------------------------------------------
*/
```

```sql
-- Que plan obtemos para listar o ultimo empregado, por orde alfabetica, da empresa? Por que?

select * from emp order by ename desc fetch first 1 row only;

/*
---------------------------------------------------------------------------------
| Id  | Operation                | Name | Rows  | Bytes | Cost (%CPU)| Time|
---------------------------------------------------------------------------------
|   0 | SELECT STATEMENT         |      |     1 |   119 |     4  (25)| 00:00:01 |
|*  1 |  VIEW                    |      |     1 |   119 |     4  (25)| 00:00:01 |
|*  2 |   WINDOW SORT PUSHED RANK|      |    14 |   532 |     4  (25)| 00:00:01 |
|   3 |    TABLE ACCESS FULL     | EMP  |    14 |   532 |     3   (0)| 00:00:01 |
---------------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   1 - filter("from$_subquery$_002"."rowlimit_$$_rownumber"<=1)
   2 - filter(ROW_NUMBER() OVER ( ORDER BY
              NLSSORT("EMP"."ENAME",'nls_sort=''SPANISH''') DESC )<=1)
*/
```

```sql
-- Sabemos que o contido actual da taboa EMP non ten ning ´ un nulo no campo ENAME (e que, de feito, non vai telo nunca; probablemente foi unha desafortunada decision de dese no). Usando 2 alternativas, obten todos os nomes dos empregado da empresa de xeito que o plan utilice o ındice.

select ename from emp where ename is not null;

/*
------------------------------------------------------------------------------
| Id  | Operation        | Name      | Rows  | Bytes | Cost (%CPU)| Time     |
------------------------------------------------------------------------------
|   0 | SELECT STATEMENT |           |    14 |    84 |     1   (0)| 00:00:01 |
|*  1 |  INDEX FULL SCAN | IDX_ENAME |    14 |    84 |     1   (0)| 00:00:01 |
------------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   1 - filter("ENAME" IS NOT NULL)
*/

alter table emp modify ename varchar(10) not null;
select ename from emp;

/*
------------------------------------------------------------------------------
| Id  | Operation        | Name      | Rows  | Bytes | Cost (%CPU)| Time     |
------------------------------------------------------------------------------
|   0 | SELECT STATEMENT |           |    14 |    84 |     1   (0)| 00:00:01 |
|   1 |  INDEX FULL SCAN | IDX_ENAME |    14 |    84 |     1   (0)| 00:00:01 |
------------------------------------------------------------------------------
*/
```

```sql
call dbms_stats.gather_schema_stats('"ivan.alvarez.fernandez"'); -- Actualizar stats
```

```sql
-- Crea un ındice sobre o campo CODART da taboa VENDA. Selecciona agora as vendas do artigo 1 e mostra o plan. Utiliza o ındice? Se non o fai, asegurate de que as estatısticas da taboa estean actualizadas.

create index idx_codart on venda(codart);

select * from venda where codart=1;

/*
--------------------------------------------------------------------------------------------------
| Id  | Operation                           | Name       | Rows  | Bytes | Cost (%CPU)| Time         |
--------------------------------------------------------------------------------------------------
|   0 | SELECT STATEMENT                    |            |     1 |    61 |     1   (0)| 00:00:01 |
|   1 |  TABLE ACCESS BY INDEX ROWID BATCHED| VENDA      |     1 |    61 |     1   (0)| 00:00:01 |
|*  2 |   INDEX RANGE SCAN                  | IDX_CODART |     1 |       |     1   (0)| 00:00:01 |
--------------------------------------------------------------------------------------------------
*/
```

```sql
-- Serıa posible que cambiando o artigo que buscamos Oracle modifique o plan, podendo usar ou non o ındice anterior?

select * from venda where codart=2; -- Existen muchas ventas de todos los artículos menos del 1

/*
---------------------------------------------------------------------------
| Id  | Operation         | Name  | Rows  | Bytes | Cost (%CPU)| Time     |
---------------------------------------------------------------------------
|   0 | SELECT STATEMENT  |       |    50 |  1100 |     4   (0)| 00:00:01 |
|*  1 |  TABLE ACCESS FULL| VENDA |    50 |  1100 |     4   (0)| 00:00:01 |
---------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   1 - filter("CODART"=2)
*/
```

```sql
-- Mostra o plan para obter todos os datos dos artigos e as suas vendas.

select * from artigo natural join venda;

/*
-----------------------------------------------------------------------------
| Id  | Operation          | Name   | Rows  | Bytes | Cost (%CPU)| Time     |
-----------------------------------------------------------------------------
|   0 | SELECT STATEMENT   |        |  1002 | 47094 |     7   (0)| 00:00:01 |
|*  1 |  HASH JOIN         |        |  1002 | 47094 |     7   (0)| 00:00:01 |
|   2 |   TABLE ACCESS FULL| ARTIGO |    20 |   500 |     3   (0)| 00:00:01 |
|   3 |   TABLE ACCESS FULL| VENDA  |  1002 | 22044 |     4   (0)| 00:00:01 |
-----------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   1 - access("ARTIGO"."CODART"="VENDA"."CODART")
*/
```

```sql
-- Forza a que o join se faga usando nested loops utilizando un hint e compara o coste co anterior.

select /*+ use_nl(artigo venda) */ * from artigo natural join venda;

/*
-----------------------------------------------------------------------------
| Id  | Operation          | Name   | Rows  | Bytes | Cost (%CPU)| Time     |
-----------------------------------------------------------------------------
|   0 | SELECT STATEMENT   |        |  1002 | 47094 |    43   (0)| 00:00:01 |
|   1 |  NESTED LOOPS      |        |  1002 | 47094 |    43   (0)| 00:00:01 |
|   2 |   TABLE ACCESS FULL| ARTIGO |    20 |   500 |     3   (0)| 00:00:01 |
|*  3 |   TABLE ACCESS FULL| VENDA  |    50 |  1100 |     2   (0)| 00:00:01 |
-----------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   3 - filter("ARTIGO"."CODART"="VENDA"."CODART")

Hint Report (identified by operation id / Query Block Name / Object Alias):
Total hints for statement: 1 (U - Unused (1))
---------------------------------------------------------------------------

   2 -  SEL$58A6D7F6 / ARTIGO@SEL$1
         U -  use_nl(artigo venda)
*/
```

```sql
-- Forza agora a que utilize sort merge join.

select /*+ use_merge(artigo venda) */ * from artigo natural join venda;

/*
------------------------------------------------------------------------------
| Id  | Operation           | Name   | Rows  | Bytes | Cost (%CPU)| Time     |
------------------------------------------------------------------------------
|   0 | SELECT STATEMENT    |        |  1002 | 47094 |     9  (23)| 00:00:01 |
|   1 |  MERGE JOIN         |        |  1002 | 47094 |     9  (23)| 00:00:01 |
|   2 |   SORT JOIN         |        |    20 |   500 |     4  (25)| 00:00:01 |
|   3 |    TABLE ACCESS FULL| ARTIGO |    20 |   500 |     3   (0)| 00:00:01 |
|*  4 |   SORT JOIN         |        |  1002 | 22044 |     5  (20)| 00:00:01 |
|   5 |    TABLE ACCESS FULL| VENDA  |  1002 | 22044 |     4   (0)| 00:00:01 |
------------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   4 - access("ARTIGO"."CODART"="VENDA"."CODART")
       filter("ARTIGO"."CODART"="VENDA"."CODART")

Hint Report (identified by operation id / Query Block Name / Object Alias):
Total hints for statement: 1 (U - Unused (1))
---------------------------------------------------------------------------

   3 -  SEL$58A6D7F6 / ARTIGO@SEL$1
         U -  use_merge(artigo venda)
*/
```

```sql
-- Forza agora a que se utilize un hash join.

select /*+ use_hash(artigo venda) */ * from artigo natural join venda;

/*
-----------------------------------------------------------------------------
| Id  | Operation          | Name   | Rows  | Bytes | Cost (%CPU)| Time     |
-----------------------------------------------------------------------------
|   0 | SELECT STATEMENT   |        |  1002 | 47094 |     7   (0)| 00:00:01 |
|*  1 |  HASH JOIN         |        |  1002 | 47094 |     7   (0)| 00:00:01 |
|   2 |   TABLE ACCESS FULL| ARTIGO |    20 |   500 |     3   (0)| 00:00:01 |
|   3 |   TABLE ACCESS FULL| VENDA  |  1002 | 22044 |     4   (0)| 00:00:01 |
-----------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   1 - access("ARTIGO"."CODART"="VENDA"."CODART")

Hint Report (identified by operation id / Query Block Name / Object Alias):
Total hints for statement: 1 (U - Unused (1))
---------------------------------------------------------------------------

   2 -  SEL$58A6D7F6 / ARTIGO@SEL$1
         U -  use_hash(artigo venda)
*/
```

```sql
-- Que estratexia usarıa se queremos obter o antes posible as primeiras filas? Por que? Discute o coste obtido polo planificador.

select /*+ first_rows */ * from artigo natural join venda;

/*
-----------------------------------------------------------------------------
| Id  | Operation          | Name   | Rows  | Bytes | Cost (%CPU)| Time     |
-----------------------------------------------------------------------------
|   0 | SELECT STATEMENT   |        |  1002 | 47094 |     7   (0)| 00:00:01 |
|*  1 |  HASH JOIN         |        |  1002 | 47094 |     7   (0)| 00:00:01 |
|   2 |   TABLE ACCESS FULL| ARTIGO |    20 |   500 |     3   (0)| 00:00:01 |
|   3 |   TABLE ACCESS FULL| VENDA  |  1002 | 22044 |     4   (0)| 00:00:01 |
-----------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   1 - access("ARTIGO"."CODART"="VENDA"."CODART")
*/

select /*+ all_rows */ * from artigo natural join venda;

/*
-----------------------------------------------------------------------------
| Id  | Operation          | Name   | Rows  | Bytes | Cost (%CPU)| Time     |
-----------------------------------------------------------------------------
|   0 | SELECT STATEMENT   |        |  1002 | 47094 |     7   (0)| 00:00:01 |
|*  1 |  HASH JOIN         |        |  1002 | 47094 |     7   (0)| 00:00:01 |
|   2 |   TABLE ACCESS FULL| ARTIGO |    20 |   500 |     3   (0)| 00:00:01 |
|   3 |   TABLE ACCESS FULL| VENDA  |  1002 | 22044 |     4   (0)| 00:00:01 |
-----------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   1 - access("ARTIGO"."CODART"="VENDA"."CODART")
*/

 select /*+ first_rows(1) */ * from artigo natural join venda;

/*
-----------------------------------------------------------------------------
| Id  | Operation          | Name   | Rows  | Bytes | Cost (%CPU)| Time     |
-----------------------------------------------------------------------------
|   0 | SELECT STATEMENT   |        |     2 |    94 |     4   (0)| 00:00:01 |
|   1 |  NESTED LOOPS      |        |     2 |    94 |     4   (0)| 00:00:01 |
|   2 |   TABLE ACCESS FULL| ARTIGO |    20 |   500 |     2   (0)| 00:00:01 |
|*  3 |   TABLE ACCESS FULL| VENDA  |     2 |    44 |     2   (0)| 00:00:01 |
-----------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   3 - filter("ARTIGO"."CODART"="VENDA"."CODART")
*/
```

```sql
-- Mostra o plan de execucion da consulta que obten o total vendido de cada artigo, obtendo o codigo e a suma de prezo de venda pola cantidade. Atopas algo extrano?

select codart, sum(prezoven*cantven)
from artigo natural join venda
group by codart; -- La idea es que no usara la tabla artigo

/*
------------------------------------------------------------------------------
| Id  | Operation           | Name   | Rows  | Bytes | Cost (%CPU)| Time     |
------------------------------------------------------------------------------
|   0 | SELECT STATEMENT    |        |    20 |   260 |     8  (13)| 00:00:01 |
|   1 |  HASH GROUP BY      |        |    20 |   260 |     8  (13)| 00:00:01 |
|*  2 |   HASH JOIN         |        |  1002 | 13026 |     7   (0)| 00:00:01 |
|   3 |    TABLE ACCESS FULL| ARTIGO |    20 |    60 |     3   (0)| 00:00:01 |
|   4 |    TABLE ACCESS FULL| VENDA  |  1002 | 10020 |     4   (0)| 00:00:01 |
------------------------------------------------------------------------------

Predicate Information (identified by operation id):
---------------------------------------------------

   2 - access("ARTIGO"."CODART"="VENDA"."CODART")
*/
```
$\space$
## 9.Concurrencia

```sql
-- Crea una taboa XEMP coa mesma estructura que EMP, pero so cos datos dos empregados SMITH e KING.

create table xemp as
select * from emp
where ename in ('SMITH', 'KING');

select * from xemp;
```

```sql
-- Fai que a sesion 1 actualice o salario de SMITH a 1000.

update emp set sal = 1000 where ename = 'SMITH';
```

```sql
-- Fai que a sesion 2 actualice a comision de SMITH a 100

update emp set comm = 100 where ename = 'SMITH'; 

-- Espera a que terminal 1 haga commit
```

```sql
-- Fai que a sesion 1 baixe o salario de KING a 4000.

update xemp set sal = 4000 where ename = 'KING';
```

```sql
-- Fai que a sesion 2 suba o salario de SMITH a 1500.

update xemp set sal = 1500 where ename = 'SMITH';
```

```sql
-- Fai que a sesion 1 estableza o salario de SMITH a 1350.

update xemp set sal = 1350 where ename = 'SMITH';

-- Espera commit de sesión 2
```

```sql
-- A sesion 2 cambia o salario de KING a 4700.

update xemp set sal = 4700 where ename = 'KING';

-- Detección de interbloqueo en sesión 1
```

```sql
-- Para empezar, nunha sesion 1 de SQL*Plus borra o contido de XEMP e inserta os datos de KING. Confirma a transaccion. Logo inicia unha sesion 2 de SQL*Plus.

delete from xemp;

insert into xemp
select *
from emp
where ename='KING';

commit;
```

```sql
-- Sen modificar o nivel de aillamento de Oracle, na sesion 1 duplica o salario de KING e engade un novo empregado de codigo 1234, nome NOBODY e salario 1000.

update xemp set sal = sal * 2 where ename = 'KING';

insert into xemp (empno, ename, sal) values (1234, 'NOBODY', 1000);

-- Sesión 1
/*
     EMPNO ENAME      JOB              MGR HIREDATE        SAL       COMM
---------- ---------- --------- ---------- -------- ---------- ----------
    DEPTNO PHONE
---------- --------------------
      1234 NOBODY                                         1000


      7839 KING       PRESIDENT            17/11/81      10000
        10
*/

-- Sesión 2
/*
     EMPNO ENAME      JOB              MGR HIREDATE        SAL       COMM
---------- ---------- --------- ---------- -------- ---------- ----------
    DEPTNO PHONE
---------- --------------------
      7839 KING       PRESIDENT            17/11/81       5000
        10
*/
```

```sql
-- Confirma os datos na sesion 1, e verifica o que se ve en ambas sesions.

commit; -- Se ve en ambas.
```

```sql
-- Na sesion 1, actualiza o salario de NOBODY a 2000.

update xemp set sal = 2000 where ename = 'NOBODY';
```

```sql
-- Na sesion 2, consulta os datos de NOBODY, que debe mostrar 1000. Actualiza o seu salario incrementandoo un 50 %.

update xemp set sal = sal * 1.5 where ename = 'NOBODY'; -- Espera por el commit de la sesión 1
```

```sql
-- Fai que a sesion 1 confirme os cambios

commit; -- Sal en sesión 1=2000, sal en sesión 2=3000

-- Oracle es read commited por defecto
```

```sql
-- Confirma as transaccions de ambas sesions, para empezar transaccion novas. Fai que ambas se poñan en modo serializable (para este grupo de exercicios realmente so necesitarıamos que a sesion 2 usase este modo).

commit;
alter session set isolation_level = serializable;
```

```sql
-- Na sesion 1 establece o salario de KING en 3000.

update xemp set sal = 3000 where ename = 'KING';
```

```sql
-- Na sesion 2, selecciona os datos de KING. Logo duplica o seu salario.

select * from xemp where ename = 'KING';

/*
     EMPNO ENAME      JOB              MGR HIREDATE        SAL       COMM
---------- ---------- --------- ---------- -------- ---------- ----------
    DEPTNO PHONE
---------- --------------------
      7839 KING       PRESIDENT            17/11/81      10000
        10
*/

update xemp set sal = sal * 2 where ename = 'KING'; -- Espera al commit de la sesión 1. Cuando se haga el commit salta error de serialización

/*
update xemp
       *
ERROR en línea 1:
ORA-08177: no se puede serializar el acceso para esta transacción
*/
```

```sql
-- Confirma as 2 transaccions e pon a sesion 2 en modo READ ONLY.
set transaction read only;
```

```sql
-- Na sesion 1 establece o salario de KING a 5000, e inserta unha nova fila cun empregado 5432, SOMEBODY, que cobra 1900. Confirma os cambios e comproba que se ve en cada sesion.

update xemp set sal = 5000 where ename = 'KING';

insert into xemp (empno, ename, sal) values (5432, 'SOMEBODY', 1900);

-- En sesión 1
select ename, sal from xemp;

/*
ENAME             SAL
---------- ----------
NOBODY           3000
SOMEBODY         1900
KING             5000
*/

-- En sesión 2
select ename, sal from xemp; -- Con read only no hubo cambios

/*
ENAME             SAL
---------- ----------
NOBODY           3000
KING             3000
*/
```






