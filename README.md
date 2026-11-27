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

- 🧩 **Evolução Incremental em POO:** Partir de uma estrutura procedural básica e evoluir progressivamente para a aplicação prática de classes e objetos, coleções tipadas, encapsulamento, construtores, pacotes Java, padrões arquiteturais (DAO/MVC), interface gráfica (JavaFX/FXML) e persistência de dados (arquivos e banco de dados relacional MySQL).

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
| **`v1.1.0`** | List + ArrayList | Separação das responsabilidades e métodos em arquivos/classes utilitárias |
| **`v1.1.1`** | List + ArrayList | Correção de bug no fluxo de encerramento do sistema (opção Sair) |
| **`v2.1.0`** | Arquivo TXT (I/O Java) | Persistência de dados em arquivo texto utilizando `java.io` |
| **`v3.0.0`** | Classes e Objetos | Introdução à Programação Orientada a Objetos com a criação da classe `Contato` |
| **`v3.1.0`** | Coleção de Objetos | Armazenamento de objetos `Contato` utilizando `List<Contato>` |
| **`v3.2.0`** | CRUD Orientado a Objetos | Adaptação das operações CRUD e da persistência para utilizar `List<Contato>` |
| **`v3.3.0`** | Encapsulamento | Encapsulamento e melhoria da modelagem da classe `Contato` |
| **`v4.0.0`** *(Atual)* | DAO e Pacotes Java | Organização das classes em pacotes e centralização da persistência utilizando o padrão DAO |

### 📌 Versão Atual: `v4.0.0` — Introdução ao DAO e Organização em Pacotes
Evolução da arquitetura da Agenda de Contatos por meio da distribuição das classes em pacotes Java conforme suas responsabilidades e da introdução do padrão **DAO (Data Access Object)**, substituindo a antiga classe `Persistencia` por `ContatoDAO`.

- **Principais Características e Conceitos:**
  - Organização das classes em pacotes (`principal`, `modelo`, `servico`, `dao` e `uteis`) com uso de `package` e `import`;
  - Aplicação do **Princípio da Responsabilidade Única** e separação da lógica de acesso aos dados;
  - Criação da classe `ContatoDAO` com os métodos `carregarContatos(contatos)` e `salvarContatos(contatos)` operando sobre `List<Contato>`;
  - Preservação das funcionalidades do CRUD e do formato de armazenamento `nome;celular;email` em `contatos.txt`.

#### Estrutura de Pacotes e Responsabilidades (`v4.0.0`)

```text
src/
└── br/
    └── edu/
        ├── principal/
        │   └── Principal.java
        ├── modelo/
        │   └── Contato.java
        ├── servico/
        │   └── Agenda.java
        ├── dao/
        │   └── ContatoDAO.java
        └── uteis/
            └── Uteis.java
```

| Classe | Responsabilidade |
| :--- | :--- |
| **`Principal`** | Inicialização da aplicação e controle do fluxo de execução |
| **`Contato`** | Representação e encapsulamento dos dados de um contato |
| **`Agenda`** | Implementação das operações de gerenciamento (CRUD) dos contatos |
| **`ContatoDAO`** | Leitura e gravação dos contatos em arquivo (`contatos.txt`) |
| **`Uteis`** | Disponibilização de métodos auxiliares |

```text
Principal
   │
   └── List<Contato>
           │
           ├── Agenda
           │     ├── adicionar()
           │     ├── listar()
           │     ├── pesquisar()
           │     ├── atualizar()
           │     └── excluir()
           │
           └── ContatoDAO
                 ├── carregarContatos()
                 └── salvarContatos()
```

### 📜 Histórico de Versões

#### `v3.3.0` — Encapsulamento e Modelagem da Classe
Proteção do estado interno da classe `Contato` com modificador `private`, métodos getters/setters e construtor parametrizado (`this`), eliminando o acesso direto aos atributos fora da classe.

#### `v3.2.0` — CRUD Orientado a Objetos
Evolução das operações da Agenda e da persistência para trabalhar diretamente com objetos `Contato` em uma única coleção `List<Contato>`, eliminando as listas paralelas de `String`.

#### `v3.1.0` — Coleção de Objetos
Evolução da representação dos contatos utilizando `List<Contato>` com `ArrayList` e Generics, percurso com `for-each` e referências de objetos em coleções.

#### `v3.0.0` — Introdução a Classes e Objetos
Início da transição para **Programação Orientada a Objetos (POO)** com a criação da entidade `Contato` (`nome`, `celular`, `email`) e instanciação via operador `new`.

#### `v2.1.0` — Persistência em Arquivo TXT
Introdução da persistência de dados em disco no arquivo `contatos.txt` (`nome;celular;email`) utilizando a classe `Persistencia` e a API `java.io`.

#### `v1.1.1` — Correção do Fluxo de Saída
Versão de ajuste da série `v1.x`, corrigindo o comportamento da opção Sair e o fluxo de encerramento da aplicação.

#### `v1.1.0` — Separação em Classes
Evolução da modularização com a criação das classes dedicadas `Agenda` e `Uteis`, reduzindo as responsabilidades da classe `Principal`.

#### `v1.0.0` — Modularização
Reorganização do código por meio da criação de métodos, passagem de parâmetros, separação das funcionalidades e redução do código no método `main`.

#### `v0.3.0` — Alteração de Contatos
Inclusão da funcionalidade de edição de registros já cadastrados através de pesquisa, identificação de posição e atualização com `set()`.

#### `v0.2.0` — List e ArrayList
Substituição dos arrays por coleções dinâmicas (`List<String>` / `ArrayList`), utilizando Generics e os métodos `add()`, `get()` e `remove()`.

#### `v0.1.0` — Arrays
Evolução para armazenar vários contatos com capacidade fixa utilizando arrays, índices e laços de repetição.

#### `v0.0.0` — Versão Inicial
Primeira versão procedural em console utilizando `Scanner`, estruturas condicionais, estruturas de repetição, menu de opções e armazenamento de apenas um contato em memória.

### 🗺️ Próxima Evolução (Roadmap)
- **`v4.1.0` — DAO Orientado a Objetos:** Substituição dos métodos estáticos do DAO por métodos de instância, aprimorando o encapsulamento e a gestão de dependências entre classes.
- **Versões Posteriores:** Padrão **MVC**, interface gráfica (**JavaFX/FXML**), integração **JDBC** e banco de dados **MySQL**.

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
  - v1.1.1
- v2
  - v2.1.0
- v3
  - v3.0.0
  - v3.1.0
  - v3.2.0
  - v3.3.0
- v4
  - v4.0.0
```

---

## 🛠️ Tecnologias Utilizadas

| Categoria | Tecnologia | Descrição |
| :--- | :--- | :--- |
| **Linguagem** | Java 17+ | Linguagem principal orientada a objetos (POO, pacotes, encapsulamento) |
| **Coleções** | Java Collections Framework | Estruturas dinâmicas (`List` e `ArrayList`) |
| **Persistência em Arquivo** | Java I/O (`java.io`) | Leitura e gravação de contatos em arquivos `.txt` via `ContatoDAO` |
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
│   └── 📦 br/edu/
│       ├── 🚀 principal/
│       ├── 🧩 modelo/
│       ├── ⚙️ servico/
│       ├── 💾 dao/
│       └── 🛠️ uteis/
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