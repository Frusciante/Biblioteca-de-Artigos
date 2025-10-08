# 📚 Biblioteca Digital de Artigos

Este projeto tem como objetivo desenvolver uma **biblioteca digital** para disponibilizar **acesso fácil e centralizado aos artigos publicados** em determinados eventos científicos. A plataforma será um repositório organizado, permitindo que usuários encontrem e acessem produções acadêmicas de forma eficiente.

As principais inspirações para o desenvolvimento são plataformas consagradas como:
- **ACM Digital Library**
- **SBC Open-Lib**
- **arXiv.org**
- **dblp.org**

Nosso objetivo é criar uma ferramenta robusta para a comunidade acadêmica, facilitando a disseminação do conhecimento científico.

---

## 👥 Membros da Equipe e Papéis

| Nome | Matrícula | Papel |
|--------------|------------|-----------|
| João | 2019027695 | Fullstack |
| Luis | - | Fullstack |
| Seungbin Han | - | Fullstack |

---

## 🛠️ Tecnologias Utilizadas

- **Linguagem**: Python
- **Backend**: Django
- **Frontend**: HTML + CSS
- **Banco de Dados**: SQLite
- **Agente IA**: Cursor e Gemini

---

## 📌 Backlog do Produto

- Como administrador, eu quero cadastrar, editar e deletar um evento.
- Como administrador, eu quero cadastrar, editar e deletar uma nova edição de um evento.
- Como administrador, eu quero cadastrar, editar e deletar um artigo manualmente, incluindo seu PDF.
- Como administrador, eu quero cadastrar artigos em massa a partir de um arquivo BibTeX.
- Como usuário, eu quero pesquisar artigos por título, autor e nome do evento.
- Como administrador, eu quero que todo evento tenha uma home page com suas edições, e que cada edição tenha uma home page com seus artigos.
- Como usuário, eu quero ter uma home page com os meus artigos, organizados por ano.
- Como usuário, eu quero me cadastrar para receber um e-mail sempre que um novo artigo de meu interesse for disponibilizado.

```mermaid
flowchart TD
  subgraph Papeis do Usuario
    A[Inicio: Visitar o site] --> B{Esta logado?}
    B -->|Nao - Visitante| C[Funcionalidades do Visitante]
    B -->|Sim| D{Conta de administrador?}
    D -->|Nao - Usuario comum| E[Funcionalidades do Usuario logado]
    D -->|Sim - Administrador| F[Funcionalidades do Administrador]
  end

  subgraph Funcionalidades Comuns
    C --> H[Pesquisar / Listar Artigos]
    H --> H1[Ver Detalhes do Artigo e Baixar PDF]
    C --> I[Listar Eventos e Edicoes]
    I --> I1[Ver Artigos por Edicao]
  end

  subgraph Funcionalidades do Usuario Logado
    E --> M[Gerenciar Interesses para Notificacao]
    E --> L[Visualizar Meus Artigos]
  end

  subgraph Funcionalidades do Administrador
    F --> O[Acessar Painel Admin]
    O --> P[Gerenciar Eventos / Edicoes]
    O --> Q[Gerenciar Artigos Individualmente]
    O --> R[Importacao em Massa via BibTeX]
  end

  subgraph Processo em Segundo Plano
    S[Sinal disparado]
    Q -->|Cria novo artigo| S
    R -->|Cria novo artigo| S
    S --> T[Compara palavras-chave do artigo com interesses]
    T --> U[Ha correspondencia?]
    U -->|Sim| V[Envia email de notificacao]
    style S fill:#f9f,stroke:#333,stroke-width:2px
  end
```
