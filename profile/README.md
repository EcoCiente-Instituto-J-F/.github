<div align="center">

<img src="/assets/Card README - Organização EcoCiente (GitHub).png" alt="Logo EcoCiente" width="140" />

# EcoCiente — Instituto J&F

**Tecnologia a serviço da reciclagem, da educação ambiental e das cooperativas.**

![Repositórios](https://img.shields.io/badge/reposit%C3%B3rios-20-2D5E40?style=for-the-badge&logo=github&logoColor=white)
![Licença](https://img.shields.io/badge/licen%C3%A7a-MIT-2D5E40?style=for-the-badge)
![Status](https://img.shields.io/badge/status-em%20desenvolvimento-F2C94C?style=for-the-badge)
![Brasil](https://img.shields.io/badge/feito%20no-Brasil-009C3B?style=for-the-badge)

[![Instagram](https://img.shields.io/badge/Instagram-@ecociente.app-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/ecociente.app/)
[![Email](https://img.shields.io/badge/Email-ecociente.jef@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ecociente.jef@gmail.com)

</div>

---

## Índice

- [Sobre](#-sobre)
- [Arquitetura](#-arquitetura)
- [Repositórios](#-repositórios)
- [Tecnologias](#-tecnologias)
- [Padrões da organização](#-padrões-da-organização)
- [Como contribuir](#-como-contribuir)
- [Contato](#-contato)

---

## Sobre

O **EcoCiente** é um projeto desenvolvido por alunos do **Instituto J&F** que conecta moradores, síndicos e cooperativas de reciclagem. A plataforma reúne:

- **Calendário de coletas** de materiais recicláveis por região
- **Pontuação e ranking** para engajar a comunidade
- **Assistente de IA** multiagente para educação ambiental
- **Aplicativo mobile** e **landing page**
- **Autenticação** de usuários, cooperativas e síndicos

> [!NOTE]
> Esta organização reúne todos os repositórios do ecossistema EcoCiente: backend, mobile, IA, dados e infraestrutura.

---

## Arquitetura

```mermaid
flowchart LR
    APP[mobile-app-ecociente] --> MOB[ds-mobile-api]
    WEB[landing-page]
    MOB --> AUTH[ds-autenticacao-api]
    MOB --> CAL[ds-calendario-api]
    MOB --> PONT[ds-pontuacao-api]
    MOB --> VAL[ds-validador-postagens-api]
    MOB --> IA[ia-eko]
    AUTH --> CAD[ds-cadastro-api]
    AUTH --> ESQ[ds-esqueceusenha-api]
    CAL --> NOT[ds-notificacoes-api]
    PONT --> REDIS[(Redis)]
    AUTH --> DB[(PostgreSQL)]
```

> [!TIP]
> O diagrama é uma visão geral por domínio. Consulte o README de cada repositório para os detalhes de integração.

---

## Repositórios

### Mobile e Web

| Repositório | Descrição | Stack |
| --- | --- | --- |
| [mobile-app-ecociente](https://github.com/EcoCiente-Instituto-J-F/mobile-app-ecociente) | Aplicativo mobile do projeto | ![Java](https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white) |
| [landing-page](https://github.com/EcoCiente-Instituto-J-F/landing-page) | Página de apresentação do projeto | ![CSS](https://img.shields.io/badge/CSS-1572B6?logo=css3&logoColor=white) |

### Backend — APIs (`ds-*`)

| Repositório | Descrição | Stack |
| --- | --- | --- |
| [ds-autenticacao-api](https://github.com/EcoCiente-Instituto-J-F/ds-autenticacao-api) | Login, cadastro de usuários e cooperativas, ativação de síndicos, recuperação de senha e tokens JWT | ![Java](https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white) |
| [ds-cadastro-api](https://github.com/EcoCiente-Instituto-J-F/ds-cadastro-api) | Cadastro de usuários no sistema | ![Java](https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white) |
| [ds-esqueceusenha-api](https://github.com/EcoCiente-Instituto-J-F/ds-esqueceusenha-api) | Recuperação de senha do usuário | ![Java](https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white) |
| [ds-calendario-api](https://github.com/EcoCiente-Instituto-J-F/ds-calendario-api) | Calendário de coletas por região, agendamentos recorrentes e avulsos, alterações, atrasos e cancelamentos | ![Java](https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white) |
| [ds-pontuacao-api](https://github.com/EcoCiente-Instituto-J-F/ds-pontuacao-api) | Concessão, estorno e restauração de pontos; rankings em Redis | ![Java](https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?logo=redis&logoColor=white) |
| [ds-validador-postagens-api](https://github.com/EcoCiente-Instituto-J-F/ds-validador-postagens-api) | Validação de postagens com modelo de ML | ![Java](https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white) |
| [ds-mobile-api](https://github.com/EcoCiente-Instituto-J-F/ds-mobile-api) | APIs consumidas pelo aplicativo mobile | ![Java](https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white) |
| [ds-notificacoes-api](https://github.com/EcoCiente-Instituto-J-F/ds-notificacoes-api) | API de notificações | ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white) |
| [servlet-ecociente](https://github.com/EcoCiente-Instituto-J-F/servlet-ecociente) | Backend com Servlets, DAOs e operações CRUD | ![Java](https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white) |
| [ds-dad-api](https://github.com/EcoCiente-Instituto-J-F/ds-dad-api) | APIs utilizadas na disciplina de DAD | ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white) |
| [dad-crud](https://github.com/EcoCiente-Instituto-J-F/dad-crud) | CRUD da disciplina de DAD | ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white) |

### Inteligência Artificial

| Repositório | Descrição | Stack |
| --- | --- | --- |
| [ia-eko](https://github.com/EcoCiente-Instituto-J-F/ia-eko) | API em FastAPI, backend do sistema de IA multiagente do EcoCiente | ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white) |

### Dados

| Repositório | Descrição | Stack |
| --- | --- | --- |
| [md-rpa-integration](https://github.com/EcoCiente-Instituto-J-F/md-rpa-integration) | Migração RPA/ETL do banco legado para o schema normalizado | ![PLpgSQL](https://img.shields.io/badge/PLpgSQL-336791?logo=postgresql&logoColor=white) |
| [md-populador-pgsql](https://github.com/EcoCiente-Instituto-J-F/md-populador-pgsql) | Massa de dados: carga inicial de 500+ registros verossímeis para testes de volume | ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white) |

### DevOps e Padronização

| Repositório | Descrição | Stack |
| --- | --- | --- |
| [devops-infra-ecociente](https://github.com/EcoCiente-Instituto-J-F/devops-infra-ecociente) | Infraestrutura como código, Cloud, Kubernetes e automações | ![Shell](https://img.shields.io/badge/Shell-4EAA25?logo=gnubash&logoColor=white) ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white) |
| [devops-repo-creator](https://github.com/EcoCiente-Instituto-J-F/devops-repo-creator) | Automação para criação de repositórios ([acessar o Criador](https://ecociente-repo-creator.vercel.app/docs)) | ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black) |
| [ecociente-repo-template](https://github.com/EcoCiente-Instituto-J-F/ecociente-repo-template) | Template padrão para novos repositórios | ![Template](https://img.shields.io/badge/template-2D5E40) |
| [.github](https://github.com/EcoCiente-Instituto-J-F/.github) | Configurações globais que padronizam os demais repositórios | ![Config](https://img.shields.io/badge/config-global-lightgrey) |

---

## Tecnologias

<div align="center">

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)

</div>

---

## Padrões da organização

<details>
<summary><b> Convenção de nomes de repositórios</b></summary>

<br />

| Prefixo | Domínio |
| --- | --- |
| `ds-*` | APIs e serviços de backend (Desenvolvimento de Sistemas) |
| `md-*` | Modelagem de Dados |
| `ia-*` | Inteligência Artificial |
| `devops-*` | Infraestrutura e automação |
| `mobile-*` | Aplicativo mobile |
| `dad-*` | Projetos da disciplina de DAD |

</details>

<details>
<summary><b>Criando um novo repositório</b></summary>

<br />

> [!TIP]
> Você pode criar um repositório já no padrão EcoCiente **só acessando o [Criador de Repositórios](https://ecociente-repo-creator.vercel.app/docs)**, sem configurar nada manualmente.

**Como usar:**

1. Acesse o [Criador de Repositórios](https://ecociente-repo-creator.vercel.app/docs) e clique em **Entrar com GitHub** (apenas membros ativos da organização).
2. Informe o **nome** seguindo o padrão `<matéria>-<nome-do-repositório>` e a **descrição**.
3. Escolha a **visibilidade** (público ou privado).
4. Se for uma API, marque **Spring Boot** e preencha Group ID, Artifact ID e Package Name.
5. Revise e clique em **Confirmar e criar**.

**O que já vem configurado automaticamente:**

- Template oficial [`ecociente-repo-template`](https://github.com/EcoCiente-Instituto-J-F/ecociente-repo-template)
- Automação de PR herdada do template
- Licença **MIT**
- Ruleset **Proteção Main** na branch `main`
- Para APIs: Spring Boot 3.5.4, Java 19, Gradle, Docker, CI/CD, Spring Web, Springdoc/Swagger UI, Lombok e DevTools

> [!NOTE]
> Em repositórios privados, a Proteção Main depende do plano e das políticas da organização. Se o GitHub não permitir, o repositório é criado normalmente e você recebe um aviso.

Prefere manual? Use o botão **Use this template** em [`ecociente-repo-template`](https://github.com/EcoCiente-Instituto-J-F/ecociente-repo-template), siga o prefixo do domínio e mantenha a licença MIT.

</details>

<details>
<summary><b>Configurações globais</b></summary>

<br />

O repositório [`.github`](https://github.com/EcoCiente-Instituto-J-F/.github) centraliza as configurações compartilhadas entre os repositórios da organização.

</details>

---

## Como contribuir

1. Faça um **fork** do repositório desejado
2. Crie uma branch: `git checkout -b feat/minha-melhoria`
3. Faça o commit: `git commit -m "feat: minha melhoria"`
4. Envie: `git push origin feat/minha-melhoria`
5. Abra um **Pull Request**

> [!IMPORTANT]
> Antes de contribuir, leia o README do repositório e siga os padrões descritos acima.

> [!WARNING]
> Nunca versione credenciais, chaves JWT ou arquivos `.env`.

---

## 📬 Contato

<div align="center">

[![Instagram](https://img.shields.io/badge/Instagram-@ecociente.app-E4405F?style=flat-square&logo=instagram&logoColor=white)](https://www.instagram.com/ecociente.app/)
[![Email](https://img.shields.io/badge/Email-ecociente.jef@gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:ecociente.jef@gmail.com)

**EcoCiente — Instituto J&F** 💚 Feito por alunos, para o planeta.

</div>
