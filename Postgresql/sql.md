# SQL

### Colocar Máscara em Número 
```
0D0000 -> inclui uma vírgula e força zero (D = Decimal / G = Grupo)
```
### Select com Sequencial
```
select row_number() over (order by nome_da_coluna_para_ordenar) AS numero_sequencial, coluna1, coluna2
from sua_tabela
order by nome_da_coluna_para_ordenar;
```
### Criar índice único:
```
create unique index nome_indice_idx on schema.tabela (campo)
```

### Drop Index
```
DROP INDEX CONCURRENTLY IF EXISTS schema.indice;
```
### Listar Atividade
```
select * from pg_stat_activity;
```
### Tirar Acentos
```
CREATE EXTENSION IF NOT EXISTS unaccent;

CREATE INDEX IF NOT EXISTS idx_cliente_unaccent 
ON clientes (unaccent(upper(nome)));
```
