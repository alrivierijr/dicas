# Dicas de Postgresql

## SQL

### Colocar Máscara em Número 
```
0D0000 -> inclui uma vírgula e força zero (D = Decimal / G = Grupo)
```

## PLSQL

### Exemplo de uso de tratamento de Exceção com retorno do erro (plsql):
```
EXCEPTION
			WHEN OTHERS THEN
        		RAISE NOTICE 'Ocorreu um erro em : %', SQLERRM;
```

### Exemplo de CONTINUE dentro de um LOOP (plsql):
```
	FOR Reg IN
			SELECT *
			FROM tabela
			WHERE regra
	LOOP 		
		CONTINUE WHEN campo_bool is true and campo_valor > 0;
	END LOOP;
```
### Tipos de Raise (plsql)
```
RAISE INFO
RAISE NOTICE
RAISE WARNING
```
