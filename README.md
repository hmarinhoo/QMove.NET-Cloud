
# QMove.NET

API RESTful para gerenciamento de motos, com funcionalidades completas de CRUD, utilizando ASP.NET Core, banco de dados Oracle via Entity Framework Core, e documentação automática com Swagger.

---

## Descrição

Este projeto oferece uma API para gerenciar motos distribuídas em diferentes setores, permitindo:

- Criar novas motos
- Consultar todas as motos ou motos filtradas por setor
- Atualizar informações de uma moto existente
- Excluir motos
- Consultar moto por ID

### Tecnologias utilizadas

- ASP.NET Core Web API (Controllers)
- Entity Framework Core com Oracle Database
- Swagger para documentação interativa da API

---

## Como rodar o projeto

### Pré-requisitos

- [.NET 7 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/7.0) (ou superior)
- Banco de dados Oracle acessível
- EF Core Tools (opcional, para gerenciar migrations)

### Passos

1. Clone o repositório:
   ```bash
   git clone https://github.com/seuusuario/MotoMonitoramento.git
   cd MotoMonitoramento
   ```

2. Configure a connection string do Oracle no arquivo `appsettings.json`:
   ```json
   "ConnectionStrings": {
     "OracleConnection": "User Id=seu_usuario;Password=sua_senha;Data Source=seu_host:porta/seu_servico"
   }
   ```

3. (Opcional) Crie o banco de dados e aplique as migrations:
   ```bash
   dotnet ef migrations add InitialCreate
   dotnet ef database update
   ```

4. Execute a aplicação:
   ```bash
   dotnet run
   ```

5. Acesse a documentação Swagger para explorar e testar as rotas:
   ```
   http://localhost:<porta>/swagger/index.html
   ```

---

## Endpoints da API

| GET    | `/api/motos`           | Retorna todas as motos           
| GET    | `/api/motos/por-setor` | Retorna motos filtradas por setor
| GET    | `/api/motos/{id}`      | Retorna moto pelo ID             
| POST   | `/api/motos`           | Cria uma nova moto               
| PUT    | `/api/motos/{id}`      | Atualiza moto pelo ID             
| DELETE | `/api/motos/{id}`      | Exclui moto pelo ID              

### Exemplo JSON para POST e PUT

```json
{
  "placa": "ABC1234",
  "status": "No patio",
  "setor": "Disponivel"
}
```

