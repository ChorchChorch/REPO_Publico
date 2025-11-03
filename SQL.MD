# SQL 

## tamaño de tablas 
```
SELECT 
    t.NAME AS Tabla,
    SUM(p.rows) AS Filas,
    SUM(a.total_pages) * 8 / 1024 AS Tamaño_MB
FROM 
    sys.tables t
JOIN 
    sys.indexes i ON t.object_id = i.object_id
JOIN 
    sys.partitions p ON i.object_id = p.object_id AND i.index_id = p.index_id
JOIN 
    sys.allocation_units a ON p.partition_id = a.container_id
GROUP BY 
    t.NAME
ORDER BY 
    Tamaño_MB DESC;
```
## shrink (reducir el tamaño físico)
```
DBCC SHRINKDATABASE (NombreDeTuBaseDeDatos);
```
