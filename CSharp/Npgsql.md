# Npgsql
## Provedor de dados oficial para PostgreSQL no ecossistema .NET

### Instalar pacote Npgsql para acessar Postgresql:
```
dotnet add package Npgsql
dotnet add package Npgsql.EntityFrameworkCore.PostgreSQL
dotnet tool install --global dotnet-ef
```
### Incluir a string de conexão em appsettings.json:
```
{
  "ConnectionStrings": {
    "DefaultConnection": "Host=localhost;Port=5432;Database=tool;Username=postgres;Password=123456"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*"
}
```
### Criar pasta Data e dentro, o arquivo AppDbContext.cs :
```
using JWebCore.Model;
using Microsoft.EntityFrameworkCore;

namespace JWebCore.Data
{
    public class AppDbContext : DbContext
    {
        public AppDbContext(DbContextOptions<AppDbContext> options) : base(options)
        {
        }

        // Exemplo de entidade
        public DbSet<Usuario> Usuarios { get; set; } = default!;

        protected override void OnModelCreating(ModelBuilder modelBuilder)
        {
            modelBuilder.ApplyConfigurationsFromAssembly(typeof(AppDbContext).Assembly);
        }
    }
}
```

### Incluir builder.Services em Program.cs :
```
builder.Services.AddDbContext<AppDbContext>(Options =>
        Options.UseNpgsql(builder.Configuration.GetConnectionString("DefaultConnection")));
```

### Criar uma tabela no banco via Migrations
```
- Adicionar a classe no DbContext.cs
- dotnet ef migrations add CriarTabelaNova
- dotnet ef database update
```
