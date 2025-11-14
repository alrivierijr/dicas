# Serilog
## Log mais profissional com escrita em arquivo

### 1- Adicionar o pacote:
```
dotnet add package Serilog.AspNetCore
dotnet add package Serilog.Sinks.File

```

### 2- Alterar o arquivo Program.cs:
```
using Serilog;

Directory.CreateDirectory("Logs");

Log.Logger = new LoggerConfiguration()
    .WriteTo.Console()
    .WriteTo.File(
        "Logs/minhaapi-.log",
        rollingInterval: RollingInterval.Day, 
        retainedFileCountLimit: 7,
        restrictedToMinimumLevel: Serilog.Events.LogEventLevel.Information
    )
    .CreateLogger();

builder.Host.UseSerilog();
```

### 3 - Alterar o arquivo appsettings.json:
```
{
  "Serilog": {
    "MinimumLevel": "Information",
    "WriteTo": [
      { "Name": "Console" },
      { "Name": "File", "Args": { "path": "Logs/minhaapi-.log", "rollingInterval": "Day" } }
    ]
  }
}
```
Fonte: ChatGpt em 06112025


