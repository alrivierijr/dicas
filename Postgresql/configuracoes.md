# Habilitar conexão em rede local
## Edite o arquivo /data/pg_hba.conf e acrescente a linha abaixo :

```
TYPE  DATABASE  USER  CIDR-ADDRESS  METHOD
host  all       all    0.0.0.0/0    md5
```
