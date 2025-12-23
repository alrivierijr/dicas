# Agrupamento de Lista
```
var groupResult = _lista.Where(t => t.id == id).GroupBy(p => p.campo1 + p.campo2);

foreach (var group in groupResult)
{
   var _campo1 = group.Key.Substring(0, 4);
   var _campo2 = group.Key.Substring(4, 2);

   string lin = _lista.Where(t => t.id == id && t.campo1 == _campo1 && t.campo2 == _campo2).FirstOrDefault().campo + "|";

   _Dict.Add(new Dict()
  {
      Bloco = "blocoX",
      Linha = "|XX|" + lin + "\r\n"
  });

}

```
