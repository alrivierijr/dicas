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
