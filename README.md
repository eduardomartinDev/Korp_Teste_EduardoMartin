# 📊 Sistema NF - Gestão Completa de Notas Fiscais# 📊 Sistema NF - Gestão Completa de Notas Fiscais



<div align="center"><div align="center">



**Sistema empresarial com arquitetura de microsserviços para gestão de produtos, estoque e notas fiscais****Sistema empresarial com arquitetura de microsserviços para gestão de produtos, estoque e notas fiscais**



![Status](https://img.shields.io/badge/status-produção-success?style=for-the-badge)![Status](https://img.shields.io/badge/status-produção-success?style=for-the-badge)

![Angular](https://img.shields.io/badge/Angular-19.2-DD0031?style=for-the-badge&logo=angular)![Angular](https://img.shields.io/badge/Angular-19.2-DD0031?style=for-the-badge&logo=angular)

![Go](https://img.shields.io/badge/Go-1.23-00ADD8?style=for-the-badge&logo=go)![Go](https://img.shields.io/badge/Go-1.23-00ADD8?style=for-the-badge&logo=go)

![MariaDB](https://img.shields.io/badge/MariaDB-11.5-003545?style=for-the-badge&logo=mariadb)![MariaDB](https://img.shields.io/badge/MariaDB-11.5-003545?style=for-the-badge&logo=mariadb)

![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=for-the-badge&logo=typescript)![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=for-the-badge&logo=typescript)



</div></div>



---## 🎯 Visão Geral



## 🎯 Visão GeralSistema completo desenvolvido com **arquitetura de microsserviços** para gerenciar produtos, controlar estoque em tempo real e emitir notas fiscais. Utiliza tecnologias modernas com backend em Go, frontend em Angular e banco de dados MariaDB.



Sistema completo desenvolvido com **arquitetura de microsserviços** para gerenciar produtos, controlar estoque em tempo real e emitir notas fiscais. Utiliza tecnologias modernas com backend em Go, frontend em Angular e banco de dados MariaDB.---



---## ✨ Funcionalidades Principais



## ✨ Funcionalidades Principais### 📦 Gestão de Produtos

- ✅ **Cadastro completo**: Criar, editar, visualizar e remover produtos

### 📦 Gestão de Produtos- ✅ **Upload de imagens**: Suporte a Base64 com validação (máx. 2MB)

- ✅ **Cadastro completo**: Criar, editar, visualizar e remover produtos- ✅ **Busca inteligente**: Filtro em tempo real com debounce

- ✅ **Upload de imagens**: Suporte a Base64 com validação (máx. 2MB)- ✅ **Visualização flexível**: Cards ou tabela conforme preferência

- ✅ **Busca inteligente**: Filtro em tempo real com debounce

- ✅ **Visualização flexível**: Cards ou tabela conforme preferência### 📋 Notas Fiscais

- ✅ **Emissão completa**: Criar notas com múltiplos itens

### 📋 Notas Fiscais- ✅ **Status dinâmico**: ABERTA (editável) / FECHADA (finalizada)

- ✅ **Emissão completa**: Criar notas com múltiplos itens- ✅ **Atualização automática**: Estoque atualizado em tempo real

- ✅ **Status dinâmico**: ABERTA (editável) / FECHADA (finalizada)- ✅ **Formato profissional**: Visualização para impressão

- ✅ **Atualização automática**: Estoque atualizado em tempo real

- ✅ **Formato profissional**: Visualização para impressão### 🛡️ Sistema Resiliente

- ✅ **Circuit Breaker**: Proteção contra falhas em cascata

### 🛡️ Sistema Resiliente- ✅ **Retry automático**: Tentativas com backoff exponencial

- ✅ **Circuit Breaker**: Proteção contra falhas em cascata- ✅ **Controle de concorrência**: SELECT FOR UPDATE para transações seguras

- ✅ **Retry automático**: Tentativas com backoff exponencial- ✅ **Cache inteligente**: Redução de 66% nas requisições HTTP

- ✅ **Controle de concorrência**: SELECT FOR UPDATE para transações seguras

- ✅ **Cache inteligente**: Redução de 66% nas requisições HTTP### 🤖 Assistente IA

- ✅ **Chat inteligente**: Integração com Hugging Face

### 🤖 Assistente IA- ✅ **Análise de dados**: Insights sobre vendas e estoque

- ✅ **Chat inteligente**: Integração com Hugging Face- ✅ **Processamento natural**: Compreensão de linguagem natural

- ✅ **Análise de dados**: Insights sobre vendas e estoque

- ✅ **Processamento natural**: Compreensão de linguagem natural---



---## 🏗️ Arquitetura do Sistema

┌─────────────────────────────────────────────────────────────┐

## 🏗️ Arquitetura do Sistema│ FRONTEND (Angular) │

│ - Componentes Standalone │

```│ - RxJS para reatividade │

┌─────────────────────────────────────────────────────────────┐│ - Angular Material Design │

│                    FRONTEND (Angular)                        ││ - NGX-Toastr, Date-fns, NGX-Mask │

│         - Componentes Standalone                            │└────────────────────┬────────────────────────────────────────┘

│         - RxJS para reatividade                             ││ HTTP REST API

│         - Angular Material Design                           │┌───────────────┼───────────────┐

│         - NGX-Toastr, Date-fns, NGX-Mask                   │▼ ▼ ▼

└────────────────────┬────────────────────────────────────────┘┌────────────────┐ ┌────────────────┐ ┌────────────────┐

                     │ HTTP REST API│SERVIÇO ESTOQUE│ │SER. FATURAMENTO│ │ ASSISTENTE │

     ┌───────────────┼───────────────┐│ Porta: 3001 │ │ Porta: 3002 │ │ IA │

     ▼               ▼               ▼│ - CRUD Produtos│ │ - Notas Fiscais│ │ - Hugging Face │

┌────────────────┐ ┌────────────────┐ ┌────────────────┐│ - Controle Saldo│ │ - Circuit Br. │ │ - Analytics │

│SERVIÇO ESTOQUE │ │SER. FATURAMENTO│ │  ASSISTENTE    ││ - SELECT UPDATE │ │ - Validações │ │ - Chat │

│  Porta: 3001   │ │  Porta: 3002   │ │      IA        │└────────┬───────┘ └───────┬────────┘ └────────────────┘

│ - CRUD Produtos│ │ - Notas Fiscais│ │ - Hugging Face ││ │

│ - Controle Saldo│ │ - Circuit Br. │ │ - Analytics    │└────────┬─────────┘

│ - SELECT UPDATE │ │ - Validações   │ │ - Chat         │▼

└────────┬───────┘ └───────┬────────┘ └────────────────┘┌──────────────────┐

         │                 ││ MariaDB 11.5 │

         └────────┬─────────┘│ notafiscal_desafio│

                  ▼│ - produtos │

         ┌──────────────────┐│ - notasfiscais │

         │   MariaDB 11.5   ││ - itens │

         │notafiscal_desafio│└──────────────────┘

         │   - produtos     │

         │   - notasfiscais │text

         │   - itens        │

         └──────────────────┘### 🔧 Stack Tecnológica

```

**Frontend:**

### 🔧 Stack Tecnológica- Angular 19.2 (Standalone Components)

- TypeScript 5.7 + RxJS 7.8

| Camada | Tecnologias |- Angular Material 19.2

|--------|-------------|- NGX-Toastr, Date-fns, NGX-Mask

| **Frontend** | Angular 19.2 (Standalone), TypeScript 5.7, RxJS 7.8, Angular Material 19.2, NGX-Toastr, Date-fns, NGX-Mask |

| **Backend** | Go 1.23, Gin Framework, Zap Logger, Viper, Air (hot reload) |**Backend:**

| **Banco de Dados** | MariaDB 11.5.2, InnoDB Engine, Transações ACID |- Go 1.23 + Gin Framework

- Zap Logger (logs estruturados)

---- Viper (configurações)

- Air (hot reload)

## 🚀 Início Rápido

**Banco de Dados:**

### Pré-requisitos- MariaDB 11.5.2

- Node.js 20+ e npm- InnoDB Engine

- Go 1.23+- Transações ACID

- MariaDB 11.5+

- Git---



### Instalação e Execução## 🚀 Início Rápido



```bash### Pré-requisitos

# 1. Clone o repositório- Node.js 20+ e npm

git clone https://github.com/eduardomartinDev/Korp_Teste_EduardoMartin.git- Go 1.23+

cd Korp_Teste_EduardoMartin- MariaDB 11.5+

- Git

# 2. Configure o banco de dados

mysql -u root -p < database.sql### Instalação e Execução



# 3. Inicie o serviço de Estoque```bash

cd backend/estoque# 1. Clone o repositório

air  # ou: go run main.gogit clone <url-do-repositorio>

cd Korp_Teste_EduardoMartin

# 4. Em novo terminal, inicie o serviço de Faturamento

cd backend/faturamento# 2. Configure o banco de dados

air  # ou: go run main.gomysql -u root -p < database.sql



# 5. Em novo terminal, inicie o Frontend# 3. Inicie o serviço de Estoque

cd frontendcd servico-estoque-go

npm installair  # ou: go run main.go

npm start

```# 4. Em novo terminal, inicie o serviço de Faturamento

cd servico-faturamento-go

**Acesse:** http://localhost:4200air  # ou: go run main.go



---# 5. Em novo terminal, inicie o Frontend

cd frontend

## 📁 Estrutura do Projetonpm install

npm start

```Acesse: http://localhost:4200

Korp_Teste_EduardoMartin/

│📁 Estrutura do Projeto

├── frontend/                    # Aplicação Angulartext

│   ├── src/app/PROJETO KORP/

│   │   ├── components/         # Componentes standalone│

│   │   │   ├── home/├── frontend/                    # Aplicação Angular

│   │   │   ├── produtos/│   ├── src/app/

│   │   │   └── notas/│   │   ├── components/         # Componentes standalone

│   │   ├── services/           # Serviços HTTP│   │   │   ├── home/

│   │   └── models/             # Interfaces TypeScript│   │   │   ├── produtos/

│   └── package.json│   │   │   └── notas/

││   │   ├── services/           # Serviços HTTP

├── backend/│   │   └── models/             # Interfaces TypeScript

│   ├── estoque/                # Microsserviço de Estoque│   └── package.json

│   │   ├── main.go│

│   │   ├── config.yaml├── servico-estoque-go/         # Microsserviço de Estoque

│   │   └── .air.toml│   ├── main.go

│   ││   ├── config.yaml

│   └── faturamento/            # Microsserviço de Faturamento│   └── .air.toml

│       ├── main.go│

│       ├── config.yaml├── servico-faturamento-go/     # Microsserviço de Faturamento

│       └── .air.toml│   ├── main.go

││   ├── config.yaml

├── database.sql                # Schema do banco│   └── .air.toml

├── README.md│

├── COMO-INICIAR.md             # Guia detalhado├── database.sql                # Schema do banco

└── DETALHAMENTO-TECNICO.md     # Documentação técnica├── README.md

```├── COMO-INICIAR.md             # Guia detalhado

└── DETALHAMENTO-TECNICO.md     # Documentação técnica

---🔒 Segurança e Boas Práticas

✅ Validação de dados em frontend e backend

## 🔒 Segurança e Boas Práticas

✅ Transações ACID para consistência

- ✅ Validação de dados em frontend e backend

- ✅ Transações ACID para consistência✅ Locks pessimistas para controle de concorrência

- ✅ Locks pessimistas para controle de concorrência

- ✅ CORS configurado corretamente✅ CORS configurado corretamente

- ✅ Logs estruturados com Zap

- ✅ Configurações externalizadas✅ Logs estruturados com Zap



---✅ Configurações externalizadas



## 📊 Performance📊 Performance

Otimizações implementadas:

**Otimizações implementadas:**

🚀 Cache com shareReplay: 66% menos requisições HTTP

| Recurso | Melhoria |

|---------|----------|🚀 Debounce na busca: 87% menos operações de filtro

| Cache com shareReplay | 66% menos requisições HTTP |

| Debounce na busca | 87% menos operações de filtro |🚀 Retry automático: Maior resiliência a falhas

| Retry automático | Maior resiliência a falhas |

| Circuit Breaker | Proteção do sistema |🚀 Circuit Breaker: Proteção do sistema



---🧪 Testes do Sistema

Testar Concorrência

## 🧪 Testes do SistemaCrie produto com saldo 1



### Testar ConcorrênciaTente finalizar 2 notas simultaneamente

1. Crie produto com saldo 1

2. Tente finalizar 2 notas simultaneamenteResultado: Uma nota sucede, outra falha por saldo insuficiente

3. **Resultado:** Uma nota sucede, outra falha por saldo insuficiente

Testar Circuit Breaker

### Testar Circuit BreakerDesligue serviço de estoque

1. Desligue serviço de estoque

2. Tente operações → Circuit Breaker abre após 3 falhasTente operações → Circuit Breaker abre após 3 falhas

3. Ligue serviço e reset via endpoint

Ligue serviço e reset via endpoint

### Testar Cache

1. Acesse lista de produtos (1 requisição)Testar Cache

2. Navegue e volte (0 requisições - cache ativo)Acesse lista de produtos (1 requisição)

3. Crie produto (cache invalidado automaticamente)

Navegue e volte (0 requisições - cache ativo)

---

Crie produto (cache invalidado automaticamente)

## 🛠️ Comandos Úteis

🛠️ Comandos Úteis

```bashbash

# Desenvolvimento Frontend# Desenvolvimento Frontend

npm start              # Servidor dev (porta 4200)npm start              # Servidor dev (porta 4200)

npm run build          # Build produçãonpm run build          # Build produção



# Desenvolvimento Backend# Desenvolvimento Backend

air                    # Hot reloadair                    # Hot reload

go run main.go         # Execução diretago run main.go         # Execução direta



# Banco de Dados# Banco de Dados

mysql -u root -p notafiscal_desafiomysql -u root -p notafiscal_desafio

```🐛 Troubleshooting

Problema comum	Solução

---Frontend não conecta	Verifique serviços nas portas 3001/3002

Erro de saldo insuficiente	Confirme saldo disponível no banco

## 🐛 TroubleshootingCircuit Breaker aberto	POST em /circuit-breaker/reset

Air não funciona	Use go run main.go como alternativa

| Problema | Solução |📚 Documentação

|----------|---------|

| Frontend não conecta | Verifique serviços nas portas 3001/3002 |<div align="center">

| Erro de saldo insuficiente | Confirme saldo disponível no banco |Desenvolvido com ☕ e 💪

| Circuit Breaker aberto | POST em `/circuit-breaker/reset` |Sistema completo e pronto para produção

| Air não funciona | Use `go run main.go` como alternativa |

</div>

---Última atualização: Novembro 2025

## 📚 Documentação

- 📖 [COMO-INICIAR.md](COMO-INICIAR.md) - Guia completo de instalação
- 🔧 [DETALHAMENTO-TECNICO.md](DETALHAMENTO-TECNICO.md) - Documentação técnica detalhada

---

<div align="center">

**Desenvolvido com ☕ e 💪**

Sistema completo e pronto para produção

*Última atualização: Novembro 2025*

</div>
