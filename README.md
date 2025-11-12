# Sistema de Emissão de Notas Fiscais

## Descrição
Sistema desenvolvido em **Angular** (frontend) e **C# (.NET 8)** (backend) para cadastro e gerenciamento de produtos e notas fiscais, com impressão e controle de estoque. O projeto segue arquitetura de **microsserviços** e demonstra tratamento de erros, concorrência e comunicação assíncrona entre serviços.

## Funcionalidades
- Cadastro de produtos (Código, Descrição, Saldo)
- Cadastro de notas fiscais (Numeração sequencial, Status Aberta/Fechada, múltiplos produtos)
- Impressão de notas fiscais
- Tratamento de erros do backend (ex.: saldo insuficiente, nota fechada, produto não encontrado)
- Controle de concorrência (atualização simultânea de produtos)
- Comunicação assíncrona entre microsserviços

## Tecnologias Utilizadas
**Frontend:**
- Angular
- Reactive Forms (FormBuilder e Validators)
- Angular Material
- RxJS para comunicação assíncrona

**Backend:**
- C# (.NET 8) com ASP.NET Core MVC
- Entity Framework Core para SQL Server
- LINQ para consultas
- Injeção de dependência
- Exceções customizadas para tratamento de erros

## Estrutura de Microserviços
1. **Serviço de Estoque** – controle de produtos e saldos
2. **Serviço de Faturamento** – gestão de notas fiscais

## Requisitos
- .NET 8 SDK
- Node.js (Angular CLI)
- SQL Server

## Como Executar
1. Clonar o repositório:
```bash
git clone https://github.com/clayton-oly/Korp_Teste_SeuNome.git
```
2. Backend:
```bash
cd backend
dotnet restore
dotnet ef database update
dotnet run
```
3. Frontend:
```bash
cd frontend
npm install
ng serve
```
4. Acesse `http://localhost:4200` no navegador.

## Observações
- Cada microserviço possui seu próprio banco SQL Server.
- Para testes de concorrência, utilize múltiplas requisições simultâneas ao backend.
- Mensagens de erro do backend são exibidas no frontend para feedback ao usuário.