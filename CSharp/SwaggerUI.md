# Configurar o Wwagger no Dotnet 8 em diante:
## 1- Instalar o pacote Smashbuckle.AspNetCore.Swagger.UI
## 2- Incluir a linha no arquivo Program.cs: 
```
if (app.Environment.IsDevelopment())
{
  app.MapOpenApi();
  app.UseSwaggerUI(options => options.SwaggerEndpoint("/openapi/v1.json", "wheater api"));
}
```
## 3- incluir no arquivo launchsettings.json a linha no bloco "https" :  
```
"launchUrl": "swagger",
```

