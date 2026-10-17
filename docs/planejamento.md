# 🗺️ Planejamento do Repositório

## 1. Objetivo

Centralizar meus projetos acadêmicos e pessoais em um único repositório público, organizado e versionado, que funcione como portfólio profissional e possa ser compartilhado no LinkedIn.

## 2. Seções definidas

| Seção | Pasta | Conteúdo |
|---|---|---|
| Página web | raiz (`index.html`, `style.css`) | Site publicado no GitHub Pages |
| Projetos acadêmicos | `projetos-academicos/` | Trabalhos da faculdade, um por pasta (ex.: este portfólio) |
| Projetos pessoais | `projetos-pessoais/` | Projetos feitos por iniciativa própria (ex.: PATRI) |
| Documentação | `docs/` | Planejamento e boas práticas |
| Recursos | `assets/` | Imagens, prints e slides |

## 3. Padrões adotados

**Nomes de pastas:** minúsculas, sem acento, separadas por hífen (`meu-projeto`).

**Commits (Conventional Commits):**

| Prefixo | Uso | Exemplo |
|---|---|---|
| `feat:` | nova funcionalidade ou conteúdo | `feat: adiciona seção de projetos` |
| `fix:` | correção | `fix: corrige link quebrado do LinkedIn` |
| `docs:` | documentação | `docs: cria README do projeto 1` |
| `style:` | ajuste visual | `style: melhora responsividade` |

**Versões (SemVer):** `v1.0.0` é a primeira versão publicada. Novos conteúdos aumentam o número do meio (`v1.1.0`) e correções aumentam o último (`v1.0.1`).

**Branches:** a `main` é a versão publicada. Mudanças maiores são feitas em branches `feat/...` e integradas via Pull Request.

## 4. Fluxo Git utilizado

```
Working Directory → git add → Staging Area → git commit → Repositório Local → git push → GitHub
```

## 5. Integrações

- **GitHub Pages:** publica a página a partir da branch `main`.
- **LinkedIn:** link do site e dos projetos na seção *Projetos* e em *Destaques*.
