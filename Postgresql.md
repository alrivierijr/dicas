Dicas de Postgresql

Colocar Máscara em Número 
```
0D0000 -> inclui uma vírgula e força zero (D = Decimal / G = Grupo)
```

Exemplo de uso de tratamento de Exceção com retorno do erro no PLSQL:
```
EXCEPTION
			WHEN OTHERS THEN
        		RAISE NOTICE 'Ocorreu um erro em : %', SQLERRM;
```



