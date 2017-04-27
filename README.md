# postgres-jsonb-examples
postgres 9.5 examples for jsonb


## Add elements in array
```SQL
SELECT jsonb_set('{"name": "Edgar", "lastname": "Huamani", "activities": [{"comment": "comentario 1", "reporter":"Juan"}]}'::jsonb, 
'{activities}', '{"name": "Edgar", "lastname": "Huamani", "activities": [{"comment": "comentario 1", "reporter":"Juan"}]}'::jsonb->'activities' ||
                              jsonb_build_object('comment', 'No entiendo',
                                                 'reporter', 'Gonzalo'
                                                )
                             );
```
                             
## Result
```SQL
jsonb_set
----------------------------------------------------------------
{"name": "Edgar", "lastname": "Huamani", "activities": [{"comment": "comentario 1", "reporter": "Juan"}, {"comment": "No entiendo", "reporter": "Gonzalo"}]}
(1 row)
```
