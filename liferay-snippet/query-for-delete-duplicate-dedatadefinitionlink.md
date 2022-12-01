
### POM.XML
```
SELECT 
*
FROM 
    public.dedatadefinitionfieldlink
WHERE
    dedatadefinitionfieldlinkid in (
        SELECT 
            dedatadefinitionfieldlinkid
        FROM 
            public.dedatadefinitionfieldlink
        WHERE
            fieldname in (
            SELECT 
                fieldname 
            FROM public.dedatadefinitionfieldlink 
            WHERE 
                1=1 
            GROUP BY fieldname having count(fieldname)>1
            )
            and mvccversion  = 0
        )
```

