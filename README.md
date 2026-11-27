# 📞 Agenda de Contatos — Prosa Code

> *"Conectando pessoas, ideias e histórias através do código."* ☕📖

**Startup:** Prosa Code  
**Disciplina:** Programação Orientada a Objetos (POO) — IFCE  
**Docente:** Prof. Roger Moura Sarmento  

![Java](https://img.shields.io/badge/Java-17-47232C?style=for-the-badge&logo=openjdk&logoColor=D2E7AA)
![JavaFX](https://img.shields.io/badge/Interface-JavaFX-66997B?style=for-the-badge&logo=java&logoColor=white)
![MySQL](https://img.shields.io/badge/Banco_de_Dados-MySQL-A4CA8B?style=for-the-badge&logo=mysql&logoColor=27081D)
![License](https://img.shields.io/badge/Licen%C3%A7a-MIT-27081D?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Em_Desenvolvimento-66997B?style=for-the-badge)

---

## 📝 Descrição

A **Agenda de Contatos** é um módulo desktop de gestão de contatos pessoais e profissionais desenvolvido como parte do ecossistema de sistemas da **Prosa Code**, além de atuar como um projeto didático incremental para acompanhar a evolução dos conceitos trabalhados na disciplina de **Programação Orientada a Objetos (POO)**.

O sistema é desenvolvido de forma incremental — iniciando com uma solução procedural simples em console e evoluindo gradualmente, versão a versão, para uma aplicação completa organizada com princípios de POO, persistência relacional e uma interface gráfica rica em estilo *pixel art*, inspirada na estética botânica e acolhedora de cafés.

Na sua versão final, o módulo oferece uma solução prática e intuitiva para organização de rede de contatos, permitindo a filtragem rápida por categorias (*Favoritos*, *Amigos*, *Família*, *Trabalho*), busca dinâmica e navegação por índice alfabético (A-Z).

---

## 🎯 Objetivos

- 📇 **Gestão de Contatos:** Registrar, atualizar, consultar e remover contatos da agenda de forma simples e intuitiva.

- 🗂️ **Categorização Prática:** Organizar registros em grupos definidos (*Todos*, *Favoritos*, *Amigos*, *Família* e *Trabalho*).

- 🔍 **Busca e Navegação Ágil:** Oferecer barra de pesquisa dinâmica por nome/telefone e filtro lateral por índice alfabético (A, B, C, D...).

- 🎨 **Interface Temática em Pixel Art:** Proporcionar uma experiência gráfica imersiva alinhada à paleta de cores oficial da Prosa Code.

- 🧩 **Evolução Incremental em POO:** Partir de uma estrutura procedural básica e evoluir progressivamente para a aplicação prática de encapsulamento, herança, polimorfismo, padrões arquiteturais (DAO/MVC), interface gráfica (JavaFX/FXML) e persistência de dados via JDBC com MySQL.

---

## 🚀 Evolução do Projeto

Cada versão introduz novos conceitos, estruturas de dados e melhorias arquiteturais sobre a entrega anterior:

| Versão | Armazenamento | Descrição |
| :--- | :--- | :--- |
| **`v0.0.0`** | Variáveis simples | Permite armazenar apenas um contato |
| **`v0.1.0`** | Arrays | Permite vários contatos com capacidade fixa |
| **`v0.2.0`** | List + ArrayList | Permite vários contatos com tamanho dinâmico |
| **`v0.3.0`** | List + ArrayList | Adiciona a opção de alteração de contatos cadastrados |
| **`v1.0.0`** *(Atual)* | List + ArrayList | Modularização das funcionalidades em métodos |

### 📌 Versão Atual: `v1.0.0` — Modularização das Funcionalidades
Nesta etapa, o projeto Agenda de Contatos foi reorganizado por meio da criação de métodos, mantendo as funcionalidades da `v0.3.0` enquanto reestrutura a organização interna do código.

- **Principais Alterações:**
  - Modularização do código procedural com criação dos métodos `adicionar()`, `listar()`, `pesquisar()`, `atualizar()` e `excluir()`;
  - Simplificação do `switch-case` e organização das responsabilidades do método `main()`;
  - Uso de parâmetros para compartilhar os dados entre os métodos.
- **Armazenamento:** Os contatos continuam armazenados em três listas do tipo `List<String>` (`nomes`, `celulares` e `e-mails`).
- **Conceitos Trabalhados:** Métodos, parâmetros, argumentos, retorno, `void`, escopo de variáveis, modularização e refatoração.

### 📜 Histórico de Versões

#### `v0.3.0` — Alteração de Contatos
Quarta versão da Agenda, adicionando edição de registros existentes.
- **Funcionalidade:** Nova opção no menu (**Alterar contato**) com busca prévia do registro.
- **Operações:** Atualização dos dados nas listas (`List` / `ArrayList`) utilizando o método `set()` e reutilização da lógica de validação/busca antes da modificação.

#### `v0.2.0` — Armazenamento Dinâmico com ArrayList
Terceira versão da Agenda, adotando coleções dinâmicas do Java.
- **Armazenamento:** Uso da API de Coleções do Java (`List` e `ArrayList`) com Generics (`<String>`) e redimensionamento dinâmico.
- **Operações:** Uso dos métodos da API (`add`, `get`, `remove`, `size`, `indexOf`, etc.), iteração com `for-each` e simplificação de inserção, busca e remoção.

#### `v0.1.0` — Arrays e Capacidade Fixa
Segunda versão da Agenda, expandindo a capacidade de armazenamento em memória.
- **Armazenamento:** Uso de arrays simples (`String[]`) para cada atributo com capacidade máxima pré-definida.
- **Manipulação:** Controle através de índices e estrutura `for`.
- **Operações:** Busca sequencial nos arrays e remoção de elementos com reorganização física (deslocamento de itens).

#### `v0.0.0` — Programação Procedural Básica
Primeira versão funcional da agenda executada em console.
- **Estrutura:** Uma única classe `Principal`, com todo o código concentrado no método `main()`.
- **Armazenamento:** Variáveis simples (`nome`, `celular` e `email`) capazes de armazenar apenas **um contato** por vez (um novo registro sobrescreve o anterior).
- **Recursos da Linguagem:** Entrada de dados com `Scanner`, estruturas condicionais (`if-else`, `switch-case`) e laço de repetição (`while`).
- **Funcionalidades:** Adicionar contato, listar contato, procurar contato, excluir contato e sair.

### 🗺️ Próximas Versões (Roadmap)
- **Versões Posteriores** — Introdução de classes e objetos, encapsulamento, padrões **DAO** e **MVC**, interface gráfica (**JavaFX**), integração **JDBC** e banco de dados **MySQL**.

### 🏷️ Controle de Versões
As entregas estáveis do projeto são identificadas no repositório por meio de **tags Git**:

```text
- V0
  - V0.0.0
  - V0.1.0
  - V0.2.0
  - V0.3.0
- V1
  - V1.0.0
```

---

## 🛠️ Tecnologias Utilizadas

| Categoria | Tecnologia | Descrição |
| :--- | :--- | :--- |
| **Linguagem** | Java 17+ | Linguagem principal orientada a objetos |
| **Interface Gráfica** | JavaFX (FXML) | Construção das telas e componentes visuais (`02-agenda-contatos.fxml`) |
| **Banco de Dados** | MySQL | Armazenamento relacional dos contatos e categorias |
| **Persistência** | JDBC | Conexão e execução de operações SQL nativas |
| **Modelagem & Design** | Pixel Art UI / Scene Builder | Design visual temático e montagem dos componentes visuais |
| **Controle de Versão** | Git / GitHub | Gestão do código-fonte, releases (tags) e documentação do repositório |

---

## 📂 Organização do Projeto

```text
AGENDA_DE_CONTATOS/
├── 📖 README.md
├── ⚖️ LICENSE
├── 🚫 .gitignore
├── 💻 src/
├── 🎨 resources/
│   ├── 🔹 icons/
│   └── 🖼️ images/
├── 📚 docs/
│   ├── 📐 uml/
│   └── 🎨 ui-ux/
│       ├── ✏️ wireframes/
│       │   ├── 📖 README.md
│       │   └── 📷 esboco-agenda.jpeg
│       └── 🖼️ mockups/
│           ├── 📖 README.md
│           ├── 🖼️ agenda-contatos-v1.png
│           └── 🖼️ agenda-contatos-v2.png
└── 🗄️ database/
```