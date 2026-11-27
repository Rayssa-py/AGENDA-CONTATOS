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

O sistema é desenvolvido de forma incremental — iniciando com uma solução procedural simples em console e evoluindo gradualmente, versão a versão, para uma aplicação completa organizada com princípios de POO, persistência de dados e uma interface gráfica rica em estilo *pixel art*, inspirada na estética botânica e acolhedora de cafés.

Na sua versão final, o módulo oferece uma solução prática e intuitiva para organização de rede de contatos, permitindo a filtragem rápida por categorias (*Favoritos*, *Amigos*, *Família*, *Trabalho*), busca dinâmica e navegação por índice alfabético (A-Z).

---

## 🎯 Objetivos

- 📇 **Gestão de Contatos:** Registrar, atualizar, consultar e remover contatos da agenda de forma simples e intuitiva.

- 🗂️ **Categorização Prática:** Organizar registros em grupos definidos (*Todos*, *Favoritos*, *Amigos*, *Família* e *Trabalho*).

- 🔍 **Busca e Navegação Ágil:** Oferecer barra de pesquisa dinâmica por nome/telefone e filtro lateral por índice alfabético (A, B, C, D...).

- 🎨 **Interface Temática em Pixel Art:** Proporcionar uma experiência gráfica imersiva alinhada à paleta de cores oficial da Prosa Code.

- 🧩 **Evolução Incremental em POO:** Partir de uma estrutura procedural básica e evoluir progressivamente para a aplicação prática de encapsulamento, herança, polimorfismo, padrões arquiteturais (DAO/MVC), interface gráfica (JavaFX/FXML) e persistência de dados (arquivos e banco de dados relacional MySQL).

---

## 🚀 Evolução do Projeto

Cada versão introduz novos conceitos, estruturas de dados e melhorias arquiteturais sobre a entrega anterior:

| Versão | Armazenamento / Recursos | Descrição |
| :--- | :--- | :--- |
| **`v0.0.0`** | Variáveis simples | Permite armazenar apenas um contato em memória |
| **`v0.1.0`** | Arrays | Permite vários contatos com capacidade fixa |
| **`v0.2.0`** | List + ArrayList | Permite vários contatos com tamanho dinâmico |
| **`v0.3.0`** | List + ArrayList | Adiciona a opção de alteração de contatos cadastrados |
| **`v1.0.0`** | List + ArrayList | Modularização das funcionalidades em métodos na classe principal |
| **`v1.1.0`** | List + ArrayList | Separação em classes utilitárias e correção do encerramento do sistema (opção Sair) |
| **`v2.1.0`** *(Atual)* | Arquivo TXT (I/O Java) | Persistência de dados em arquivo texto utilizando `java.io` |

### 📌 Versão Atual: `v2.1.0` — Persistência de Dados em Arquivo Texto (TXT)
Nesta etapa, o projeto introduz a **persistência de dados**. Os contatos cadastrados deixam de ser perdidos ao encerrar a aplicação e passam a ser gravados em disco em arquivo texto formato `.txt`.

- **Principais Características e Conceitos:**
  - Leitura e escrita de dados em disco utilizando a API `java.io`;
  - Representação e verificação do arquivo com `File`;
  - Leitura estruturada linha a linha com `FileReader` e `BufferedReader`;
  - Gravação e manipulação de fluxo de escrita com `FileWriter` e `PrintWriter`;
  - Carregamento automático dos contatos ao iniciar a aplicação;
  - Atualização e sincronização do arquivo texto nas operações de inserção, alteração e exclusão;
  - Tratamento de exceções de entrada e saída (`IOException`).

### 📜 Histórico de Versões

#### `v1.1.0` — Modularização em Múltiplos Arquivos e Ajustes de Fluxo
Organização e separação das responsabilidades em diferentes arquivos do projeto, consolidando também os ajustes de encerramento da série `v1.x`.
- **Principais Alterações:** Criação de classes dedicadas para auxílio e gerenciamento da agenda (`Uteis`, `Agenda`), divisão entre a interface com o usuário (menu no console) e a lógica de processamento dos dados, além da correção no encerramento da execução da aplicação (opção de saída do menu) e fechamento adequado do `Scanner`.

#### `v1.0.0` — Modularização com Métodos
Reorganização do código procedural em funções/métodos na mesma classe.
- **Principais Alterações:** Criação dos métodos `adicionar()`, `listar()`, `pesquisar()`, `atualizar()` e `excluir()`, simplificação da estrutura do `switch-case` no `main()` e passagem de dados via parâmetros e argumentos.
- **Conceitos Trabalhados:** Escopo de variáveis, retornos (`void`) e refatoração.

#### `v0.3.0` — Atualização de Registros
Quarta versão da Agenda, adicionando edição de registros existentes.
- **Principais Características:** Nova opção no menu (**Alterar contato**), busca prévia do registro a ser modificado e atualização das listas utilizando o método `set()`.

#### `v0.2.0` — Armazenamento Dinâmico com ArrayList
Terceira versão da Agenda, adotando coleções dinâmicas do Java.
- **Principais Características:** Uso da API de Coleções do Java (`List` e `ArrayList`) com Generics (`<String>`), alocação e redimensionamento dinâmico, métodos da API (`add`, `get`, `remove`, `size`, `indexOf`) e iteração com `for-each`.

#### `v0.1.0` — Arrays e Capacidade Fixa
Segunda versão da Agenda, expandindo a capacidade de armazenamento em memória.
- **Principais Características:** Uso de arrays simples (`String[]`) para cada atributo com controle de capacidade máxima pré-definida, manipulação através de índices e estrutura `for`, busca sequencial e reorganização física do array na remoção.

#### `v0.0.0` — Programação Procedural Básica
Primeira versão funcional da agenda executada em console.
- **Principais Características:** Uma única classe `Principal` com todo o código dentro do método `main()`, armazenamento de apenas um contato nas variáveis `nome`, `celular` e `email`, menu interativo via console (`Scanner`, `if-else`, `switch-case`, `while`) e funcionalidades básicas (Adicionar, Listar, Procurar, Excluir e Sair).

### 🗺️ Próximas Versões (Roadmap)
- **Versões Posteriores** — Introdução de classes e objetos de domínio, encapsulamento, padrões **DAO** e **MVC**, interface gráfica (**JavaFX/FXML**), integração **JDBC** e banco de dados **MySQL**.

### 🏷️ Controle de Versões
As entregas estáveis do projeto são identificadas no repositório por meio de **tags Git**:

```text
- v0
  - v0.0.0
  - v0.1.0
  - v0.2.0
  - v0.3.0
- v1
  - v1.0.0
  - v1.1.0
- v2
  - v2.1.0
```

---

## 🛠️ Tecnologias Utilizadas

| Categoria | Tecnologia | Descrição |
| :--- | :--- | :--- |
| **Linguagem** | Java 17+ | Linguagem principal orientada a objetos |
| **Persistência em Arquivo** | Java I/O (`java.io`) | Leitura e gravação de contatos em arquivos `.txt` |
| **Interface Gráfica** | JavaFX (FXML) | Construção das telas e componentes visuais (`02-agenda-contatos.fxml`) |
| **Banco de Dados** | MySQL | Armazenamento relacional dos contatos e categorias |
| **Persistência Relacional** | JDBC | Conexão e execução de operações SQL nativas |
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