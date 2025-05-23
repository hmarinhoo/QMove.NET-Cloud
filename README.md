
# QMove.NET

API RESTful para gerenciamento de motos, com funcionalidades completas de CRUD, utilizando **ASP.NET Core**, banco de dados **Oracle** via **Entity Framework Core**, e documentação automática com **Swagger**.

---

## Descrição

Este projeto oferece uma API para gerenciar motos distribuídas em diferentes setores, permitindo:

- Criar novas motos  
- Consultar todas as motos ou motos filtradas por setor  
- Atualizar informações de uma moto existente  
- Excluir motos  
- Consultar moto por ID  

---

## Endpoints da API

| Método | Endpoint                | Descrição                            |
|--------|-------------------------|--------------------------------------|
| GET    | `/api/motos`            | Retorna todas as motos               |
| GET    | `/api/motos/por-setor`  | Retorna motos filtradas por setor    |
| GET    | `/api/motos/{id}`       | Retorna moto pelo ID                 |
| POST   | `/api/motos`            | Cria uma nova moto                   |
| PUT    | `/api/motos/{id}`       | Atualiza moto pelo ID                |
| DELETE | `/api/motos/{id}`       | Exclui moto pelo ID                  |

A documentação interativa está disponível via Swagger após execução:

```
http://<IP_PÚBLICO_DA_VM>:5082/swagger/index.html
```

---

# QMove Cloud

## Instalação local

### Passos:

```bash
# Clone o projeto
git clone https://github.com/hellomesq/MotoMonitoramento.git
cd MotoMonitoramento

# Build e execução local
dotnet build
dotnet run
```

---

## Docker e Deploy

### Build e push da imagem para Docker Hub

```bash
docker build -t hellomesq/motomonitoramento:latest .
docker login
docker push hellomesq/motomonitoramento:latest
```

---

## Criação da VM e Deploy na Azure CLI

### Executar o script de criação da VM

```bash
chmod +x deploy.sh
./deploy.sh
```

### Acessar a VM pela CLI da Azure

```bash
ssh usuario@ip-da-vm
```

---

## Instalar Docker na VM

```bash
sudo apt update
sudo apt install docker.io -y
sudo usermod -aG docker $USER
newgrp docker
```

---

## Subir a aplicação com Docker

```bash
# Verifique se o Docker está funcionando
docker ps

# Baixe a imagem
docker pull hellomesq/motomonitoramento:latest

# Execute o container
docker run -d -p 5082:5082 --name motomonitor hellomesq/motomonitoramento:latest
```

---

## Acessar a aplicação

Abra no navegador:

```
http://<IP_PÚBLICO_DA_VM>:5082/swagger/index.html
```

---

