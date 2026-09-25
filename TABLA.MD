# Tablas




# CREATE TABLE 

``` sql

CREATE TABLE [tblcliente](
    [Patient_ID] [bigint] IDENTITY(1,1),
    [cliente_code] [varchar](50) NOT NULL,
    [cliente_name] [varchar](50),
    [direcion] [varchar](25),
    [ciudad] [varchar](50),
    [fecha] [datetime],
  ) ON [PRIMARY]

```

> (Crear una tabla )

# CREATE TABLE con llave fk (FOREIGN)

``` sql 

CREATE TABLE controles(
    [cliente_ID] [bigint] IDENTITY(1,1),
    [controles] [varchar](50) NOT NULL,
    [consola] [varchar](50),
    [pc] [varchar](25),
    [sistema_operativo] [varchar]
    CONSTRAINT FK_controles_cliente_ID 
    FOREIGN KEY (cliente_ID) 
    REFERENCES tbljuego2(cliente_ID)

);

```

 > (crea una tabla con un tipo de llave foreigen escomo un join mas rapodo
   )


# SELECT

``` sql

SELECT
	cs.CustomerID
	,cs.Name
	,cs.CountryID
	,cn.CountryName
FROM Customers cs
INNER JOIN Countries cn
	ON cs.CountryID = cn.CountryID;

```
   > (seletciona un valor de la tabla en el ej. seletciona 4 para un join)

# insert

``` sql

insert into [tbljuego2] ([nombre_del_cliente],[rol_de_juego],[juego],[precio],[fecha_de_compra])
values ('PAULO','AAVENTURA','MINECRFT','24','2026-10-25'),
       ('ROCKY','SHOTER','VALORANT','60','2026-10-25'),
       ('ENYER','ACCION','BATLEFIELD','60','2026-10-25')
```
   > (insertar valores a la tabla)

# update

``` sql

update [dbo].[tblCliente] 
set [Fecha de la cita] = 2026-10-26
where cliente_ID IN (20,21,22)

```

  >  (para cambiar los valores de la tabla)

# delete

``` sql

delete from [dbo].[tblCliente]
where cliente_ID = 1

```

 >   (para eliminar valores de una tabla)

# join

``` sql

SELECT 
    c.[cliente_ID],
    c.[cliente_code],
    c.[cliente_name],
    c.[direcin],
    c.[ciudad],
    c.[Fecha de la cita],
    j.[nombre_del_cliente] AS juego_cliente,
    j.[rol_de_juego] AS rol,
    j.[juego],
    j.[precio],
    j.[fecha_de_compra]
FROM [master].[dbo].[tblCliente] AS c
INNER JOIN [master].[dbo].[tbljuego2] AS j 
    ON c.[cliente_ID] = j.[cliente_ID];

```

 >   (une dos tablas diferentes tablas)

# select


``` sql

    select *
from tblCliente order by cliente_ID;

 >   (para ordenar los valores de las tablas )

```

> (seletciona un valor de la tabla)