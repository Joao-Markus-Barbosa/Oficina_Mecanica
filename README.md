
# Oficina Mecânica - Modelo de Banco de Dados

## Introdução
Este projeto apresenta o modelo de banco de dados para uma aplicação de gestão de oficinas mecânicas. O objetivo é oferecer uma estrutura clara e organizada para gerenciar clientes, veículos, serviços, equipes e oficinas, garantindo que as operações do negócio sejam bem documentadas e eficientes.

## Estrutura do Modelo de Dados
O modelo de dados foi projetado para refletir as relações entre os diversos elementos de uma oficina mecânica. Abaixo está um resumo das tabelas e seus principais atributos:

### 1. **Cliente**
- `idCliente` (INT): Identificador único do cliente.
- `Nome` (VARCHAR(45)): Nome do cliente.
- `Endereço` (VARCHAR(45)): Endereço do cliente.
- `Contato` (VARCHAR(45)): Informações de contato.
- `Tipo de Cliente` (VARCHAR(45)): Tipo de cliente (por exemplo, pessoa física ou jurídica).
- `Oficina_idOficina` (INT): Relacionamento com a oficina onde o cliente está registrado.

### 2. **Veículo**
- `idVeículo` (INT): Identificador único do veículo.
- `Placa` (VARCHAR(45)): Placa do veículo.
- `Modelo` (VARCHAR(45)): Modelo do veículo.
- `Oficina_idOficina` (INT): Relacionamento com a oficina associada ao veículo.

### 3. **Oficina**
- `idOficina` (INT): Identificador único da oficina.
- `Razão social` (VARCHAR(45)): Razão social da oficina.
- `CNPJ` (VARCHAR(45)): CNPJ da oficina.
- `Endereço` (VARCHAR(45)): Endereço da oficina.
- `e-mail` (VARCHAR(45)): E-mail de contato.
- `Telefone` (INT): Telefone de contato.

### 4. **Equipe Mecânica**
- `idMecânico` (INT): Identificador único do mecânico.
- `Nome` (VARCHAR(45)): Nome do mecânico.
- `Endereço` (VARCHAR(45)): Endereço do mecânico.
- `Especialidade` (VARCHAR(45)): Especialidade do mecânico.

### 5. **Ordem de Serviço**
- `idOrdem de Serviço` (INT): Identificador único da ordem de serviço.
- `Nº OS` (INT): Número da ordem de serviço.
- `Data emissão` (DATE): Data de emissão da ordem de serviço.
- `Status` (VARCHAR(45)): Status atual da ordem de serviço.
- `Data conclusão serviço` (DATE): Data de conclusão do serviço.
- `Descrição do serviço realizado` (VARCHAR(45)): Detalhes do serviço executado.
- `Valor total` (DOUBLE): Valor total do serviço.

### 6. **Interação Equipe Mecânica/Veículo**
- `Veículo_idVeículo` (INT): Identificador do veículo associado.
- `Veículo_Oficina_idOficina` (INT): Identificador da oficina associada ao veículo.
- `Equipe mecânica_idMecânico` (INT): Identificador do mecânico associado.

### 7. **Interação Mecânico e Serviço a Ser Executado**
- `Ordem de serviço_idOrdem de serviço` (INT): Identificador da ordem de serviço associada.
- `Equipe mecânica_idMecânico` (INT): Identificador do mecânico associado ao serviço.

## Relacionamentos
O modelo conta com os seguintes relacionamentos principais:
- Cada **Cliente** está associado a uma **Oficina**.
- Cada **Veículo** está associado a um **Cliente** e a uma **Oficina**.
- Cada **Equipe Mecânica** pode ser associada a vários **Veículos**.
- Cada **Ordem de Serviço** detalha o trabalho realizado por um ou mais **Mecânicos** em um **Veículo**.
- As tabelas de interação auxiliam no mapeamento das relações entre veículos, mecânicos e ordens de serviço.

## Benefícios do Modelo
- **Organização de Dados**: Estrutura clara para armazenar informações sobre clientes, veículos, serviços e equipes.
- **Flexibilidade**: Facilita a expansão do banco para incluir novas funcionalidades, como relatórios e gestão de estoque.
- **Eficiência Operacional**: Permite gerenciar ordens de serviço e alocação de equipes de forma eficiente.![Oficina Mecânica DIO](https://github.com/user-attachments/assets/fd4368ac-a152-4912-86e7-97e6efc3b845)

