# 🛠️ Esboço da Stack do Projeto (INDECX)

> **Contexto de Atendimento:**  
> - **UNDB:** Atendimento aos critérios acadêmicos e pedagógicos da disciplina de **Programação Orientada a Objetos (POO - ES04BN)**.  
> - **CEDRO (Laboratório):** Entrega de uma solução funcional, moderna, estável e com foco em usabilidade e performance.

---

## 🏗️ Visão Geral da Arquitetura

```text
┌────────────────────────────────────────────────────────┐
│                   FRONT-END (Next.js)                  │
│       Interface web moderna, reativa e tipada          │
└───────────────────────────┬────────────────────────────┘
                            │ HTTP / REST (JSON)
┌───────────────────────────▼────────────────────────────┐
│              BACK-END (Node.js + Express)              │
│       Núcleo em POO estrita, serviços e entidades      │
└──────────────┬──────────────────────────┬──────────────┘
               │                          │
┌──────────────▼──────────┐    ┌──────────▼──────────────┐
│  PostgreSQL (Supabase)  │    │     Supabase Auth       │
│  Persistência de Dados  │    │  Autenticação & Storage │
└─────────────────────────┘    └─────────────────────────┘
```

---

## 📦 Definição da Stack por Camada

### 1. ⚙️ Back-end (API REST com POO Estrita)
* **Runtime:** Node.js
* **Linguagem:** TypeScript
* **Framework:** Express.js
* **Abordagem de POO:**
  - **Pilares:** Abstração, Encapsulamento, Herança e Polimorfismo.
  - **Arquitetura em Camadas:** Domínio (entidades ricas e regras de negócio) isolado de controladores Express e banco.
  - **Inversão de Dependências (DIP):** Injeção via construtor para facilitar testes e garantir baixo acoplamento.
* **Validação de Dados:** Zod

---

### 2. 💻 Front-end (Interface Web)
* **Framework:** Next.js (App Router)
* **Linguagem:** TypeScript
* **Estilização:** Tailwind CSS
* **Biblioteca de Componentes:** shadcn/ui
* **Consumo de API:** Fetch / TanStack Query (React Query)

---

### 3. 🗄️ Banco de Dados, Autenticação & Storage
* **SGBD:** PostgreSQL
* **Plataforma:** Supabase (self-hosted / cloud)
* **Autenticação:** Supabase Auth (tokens JWT com validação na API)
* **Armazenamento de Arquivos:** Supabase Storage (para anexos e documentos)

---

### 4. 🧪 Qualidade de Software & Testes (QA)
* **Testes de Domínio & POO (Unitários):** Vitest
* **Testes de Rotas e API (Integração):** Supertest
* **Testes Ponta a Ponta (E2E):** Playwright

---

## 🎯 Atendimento aos Dois Clientes

| Critério | UNDB (Cadeira de POO) | CEDRO (Laboratório) |
| :--- | :--- | :--- |
| **Foco Principal** | Avaliação do paradigma orientado a objetos, separação de responsabilidades e boas práticas. | Robustez de produto, interface amigável e resolução de demandas reais do laboratório. |
| **Entregáveis Chave** | Modelagem de classes, diagramas UML, entidades ricas e suíte de testes unitários. | Aplicação operacional, gestão de acessos, persistência de dados e painel administrativo. |
| **Garantia Técnica** | Tipagem forte com TypeScript e injeção de dependências sem código procedural solto. | Next.js + Tailwind garantindo alta performance, design responsivo e tempo de carregamento otimizado. |
