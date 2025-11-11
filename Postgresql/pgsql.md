# Dicas de Postgresql - PLSQL

### Exemplo de uso de tratamento de Exceção com retorno do erro:
```
EXCEPTION
			WHEN OTHERS THEN
        		RAISE NOTICE 'Ocorreu um erro em : %', SQLERRM;
```

### Exemplo de CONTINUE dentro de um LOOP:
```
	FOR Reg IN
			SELECT *
			FROM tabela
			WHERE regra
	LOOP 		
		CONTINUE WHEN campo_bool is true and campo_valor > 0;
		...
	END LOOP;
```
### Tipos de Raise
```
RAISE INFO
RAISE NOTICE
RAISE WARNING
```
