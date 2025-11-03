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
## tiempo de ejecucion 
```
SELECT TOP 10
    qs.total_elapsed_time / qs.execution_count AS TiempoPromedioMs,
    qs.total_elapsed_time AS TiempoTotalMs,
    qs.execution_count AS VecesEjecutada,
    SUBSTRING(st.text, qs.statement_start_offset / 2, 
              (CASE WHEN qs.statement_end_offset = -1 
                    THEN LEN(CONVERT(NVARCHAR(MAX), st.text)) * 2 
                    ELSE qs.statement_end_offset END - qs.statement_start_offset) / 2) AS ConsultaSQL
FROM 
    sys.dm_exec_query_stats qs
CROSS APPLY 
    sys.dm_exec_sql_text(qs.sql_handle) st
ORDER BY 
    TiempoPromedioMs DESC;
```
