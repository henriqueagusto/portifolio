# 📦 PATRI — Controle de Equipamentos Patrimoniais

> Sistema web para localizar, emprestar e controlar equipamentos audiovisuais e patrimoniais, feito para ser usado no tablet e no celular.

**Tipo:** Pessoal / uso real · **Status:** ✅ Em uso
🔗 **Repositório:** https://github.com/henriqueagusto/patri-cautela

---

## 🎯 Objetivo

Substituir o controle em papel e planilhas por um sistema único que responde rápido a três perguntas: **onde está o equipamento, com quem está e quando volta**. O sistema também gera a **cautela** (termo de empréstimo) preenchida, idêntica ao formulário oficial, pronta para imprimir e assinar.

## ✨ Funcionalidades

- **Cadastro de equipamentos** com PR, número de série, categoria, foto e local.
- **Locais em níveis livres**: prédio → sala → armário → prateleira → gaveta.
- **Cautelas**: um empréstimo reúne vários itens, com data única de devolução e numeração por ano (`300/2026`).
- **Impressão da cautela** no modelo oficial, com as assinaturas em branco para o papel.
- **Devolução** registrando quem recebeu e o estado de cada item.
- **Busca tolerante**: encontra por nome, PR, marca, modelo, local ou responsável, sem depender de acento.
- **Situação calculada**: status como *Atrasado* e *Retorno próximo* são derivados na leitura, sem rotina manual.
- **Permissões**: administrador e usuário comum, com senhas criptografadas e login por token.
- **Lixeira e auditoria**: exclusão recuperável e registro de toda alteração de cadastro.
- **Instalável como app** (PWA) no Android e no iPad/iPhone.

## 🛠️ Tecnologias

| Camada | Tecnologias |
|---|---|
| Frontend | React 19, TypeScript, Vite, React Router |
| Backend | Node.js 20, Express, Zod (validação) |
| Banco de dados | PostgreSQL 16, Prisma ORM |
| Segurança | bcryptjs (senhas), JSON Web Token (sessão) |
| Infraestrutura | Docker Compose, Render, servidor local Windows |

## 🧱 Arquitetura

```
patri-cautela/
├─ src/              frontend React (páginas, estado, design system)
├─ server/
│  ├─ prisma/        schema do banco
│  └─ src/routes/    API REST em Express
├─ public/           ícones e manifesto do PWA
├─ windows/          scripts de instalação, backup e início automático
└─ docs/             design, deploy e servidor local
```

## ▶️ Como executar

Requisitos: **Node 20+** e **Docker Desktop**.

```bash
git clone https://github.com/henriqueagusto/patri-cautela.git
cd patri-cautela
docker compose up -d        # sobe o PostgreSQL

cd server
cp .env.example .env
npm install
npm run setup               # cria as tabelas e o administrador
npm run dev                 # API em http://localhost:3333

# em outro terminal, na raiz do projeto
npm install
npm run dev                 # interface em http://localhost:5173
```

## 🧠 Decisões de projeto

- **Pessoa ≠ usuário:** quem pega o equipamento não precisa ter login.
- **Situação é gravada, condição é calculada:** evita dados inconsistentes.
- **Exclusão lógica:** nada se perde por engano.
- **Configurável:** prazos, numeração da cautela, nome e logo da instituição.

## 📚 O que aprendi

- Modelar um banco relacional com Prisma a partir de regras reais de negócio.
- Separar frontend e API, com validação dos dois lados.
- Publicar o sistema na nuvem (Render) e depois migrar para um servidor local.
- Versionar e documentar um projeto em uso real com Git e GitHub.

## 👤 Autor

Henrique Augusto de Oliveira Souza — [GitHub](https://github.com/henriqueagusto)
