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

O sistema acompanha a evolução dos conceitos de programação — desde a utilização de variáveis e estruturas de dados em console até a aplicação de princípios de orientação a objetos, organização em camadas, persistência e uma interface gráfica rica em estilo *pixel art*, inspirada na estética botânica e acolhedora de cafés.

Na sua versão final, o módulo oferece uma solução prática e intuitiva para organização de rede de contatos, permitindo a filtragem rápida por categorias (*Favoritos*, *Amigos*, *Família*, *Trabalho*), busca dinâmica e navegação por índice alfabético (A-Z).

---

## 🎯 Objetivos

- 📇 **Gestão de Contatos:** Cadastrar, listar, pesquisar, atualizar e excluir contatos (atributos: **Nome**, **Celular** e **E-mail**), além de apresentar informações sobre o sistema.

- 💾 **Persistência de Dados:** Salvar contatos em arquivo TXT e recuperá-los automaticamente ao iniciar a aplicação, evoluindo posteriormente para persistência relacional em MySQL.

- 🗂️ **Categorização Prática:** Organizar registros em grupos definidos (*Todos*, *Favoritos*, *Amigos*, *Família* e *Trabalho*).

- 🔍 **Busca e Navegação Ágil:** Oferecer barra de pesquisa dinâmica por nome/telefone e filtro lateral por índice alfabético (A, B, C, D...).

- 🎨 **Interface Temática em Pixel Art:** Proporcionar uma experiência gráfica imersiva alinhada à paleta de cores oficial da Prosa Code.

- 🧩 **Evolução Incremental em POO:** Aplicar progressivamente classes e objetos, coleções tipadas, encapsulamento, construtores, injeção de dependências, padrões arquiteturais (**DAO** e **MVC**), interface gráfica (**JavaFX/FXML**) e banco de dados (**JDBC/MySQL**).

---

## 🚀 Evolução do Projeto

### 📌 Versão Atual: `v5.1.0` — MVC Completo
Nesta versão, consolidamos a implementação do padrão arquitetural **MVC (Model-View-Controller)** introduzido na `v5.0.0`. Anteriormente, a classe `Principal` ainda controlava o menu e coordenava as chamadas entre View e Controller; agora, toda a interação com o usuário foi centralizada em `AgendaView` (absorvendo as responsabilidades da antiga classe `Uteis`), simplificando `Principal` e aprimorando o desacoplamento entre as camadas.

- **Principais Alterações:**
  - Transferência do controle do menu e das interações de apresentação de `Uteis` e `Principal` para `AgendaView` (remoção de métodos e classes obsoletas);
  - Associação entre `AgendaView` e `AgendaController` via construtor e criação de métodos dedicados para executar cada operação do CRUD na View;
  - Refinamento dos métodos de `AgendaController` com reutilização da pesquisa nas operações de atualização e exclusão;
  - Manutenção da persistência em arquivos TXT utilizando `ContatoDAO`, validando a separação de responsabilidades e testes de regressão.
- **Conceitos Trabalhados:** Padrão arquitetural MVC, separação de responsabilidades, princípio da responsabilidade única, baixo acoplamento, associação entre objetos, injeção de dependências por construtor, encapsulamento, compartilhamento de referências, reutilização de métodos, refatoração, integração entre MVC e DAO, persistência em arquivos, tratamento de exceções, testes de regressão e validação arquitetural.

#### Organização MVC (`v5.1.0`)

| Componente | Responsabilidade | Implementação |
| :--- | :--- | :--- |
| **Model** | Representar os dados da aplicação | `Contato` |
| **View** | Receber informações, controlar o menu e apresentar resultados | `AgendaView` |
| **Controller** | Executar as operações sobre os contatos | `AgendaController` |

| Classe | Responsabilidade |
| :--- | :--- |
| **`Principal`** | Inicializar e conectar os componentes da aplicação |
| **`Contato`** | Representar os dados de um contato (`nome`, `celular`, `email`) — *Model* |
| **`AgendaView`** | Controlar o menu, receber informações e apresentar resultados — *View* |
| **`AgendaController`** | Executar as operações do CRUD e coordenar a persistência — *Controller* |
| **`ContatoDAO`** | Realizar a leitura e gravação dos contatos em arquivo (`contatos.txt`) — *DAO* |

```java
// Inicialização e conexão dos componentes na classe Principal
List<Contato> contatos = new ArrayList<>();

ContatoDAO dao = new ContatoDAO("contatos.txt");
dao.carregarContatos(contatos);

AgendaController controller = new AgendaController(contatos, dao);

Scanner sc = new Scanner(System.in);
AgendaView view = new AgendaView(sc, controller);

view.iniciar();
sc.close();
```

```java
// Exemplo de fluxo na AgendaView (Inclusão)
public void executarInclusao() {
    Contato contato = lerContato();
    controller.adicionarContato(contato);
    mostrarMensagem("Contato adicionado com sucesso!");
}
```

#### Persistência dos Dados (`contatos.txt`)
Os contatos são armazenados no arquivo `contatos.txt` (criado automaticamente durante a gravação, caso ainda não exista) utilizando `;` como separador. Ao iniciar, os registros são carregados para a memória; ao selecionar sair, `AgendaView` solicita ao `AgendaController` a gravação, que encaminha ao `ContatoDAO` — caso ocorra erro, uma mensagem é exibida e a aplicação permanece em execução.

```text
Maria;85999999999;maria@email.com
João;85988888888;joao@email.com
```

### 📜 Histórico Completo de Versões

| Versão | Descrição |
| :--- | :--- |
| **`v0.0.0`** | Introdução às variáveis e cadastro de um contato |
| **`v0.1.0`** | Utilização de arrays para armazenar contatos |
| **`v0.2.0`** | Introdução a `List` e `ArrayList` |
| **`v0.3.0`** | Implementação das operações do CRUD |
| **`v1.0.0`** | Modularização das funcionalidades em métodos |
| **`v1.1.0`** | Organização dos métodos em classes |
| **`v1.1.1`** | Correção do funcionamento da opção de saída |
| **`v2.0.0`** | Introdução à manipulação de arquivos |
| **`v2.1.0`** | Persistência dos contatos em arquivo TXT |
| **`v3.0.0`** | Introdução aos conceitos de classe e objeto |
| **`v3.1.0`** | Utilização de `ArrayList<Contato>` |
| **`v3.2.0`** | CRUD utilizando objetos |
| **`v3.3.0`** | Encapsulamento e aprimoramento da classe `Contato` |
| **`v4.0.0`** | Introdução ao padrão DAO e organização em pacotes |
| **`v4.1.0`** | DAO orientado a objetos, com construtor e métodos de instância |
| **`v5.0.0`** | Introdução ao padrão MVC e separação entre Model, View e Controller |
| **`v5.1.0`** *(Atual)* | Consolidação do MVC, centralização das interações na View e simplificação da classe `Principal` |

### 🗺️ Próxima Evolução (Roadmap)
- **`v6.0.0` — JDBC + MySQL:** Substituir a persistência em arquivos TXT pelo banco de dados relacional **MySQL** utilizando **JDBC (Java Database Connectivity)**, adaptando `ContatoDAO` para comandos SQL sem precisar reescrever a interface ou a lógica de interação com o usuário.
- **Versões Posteriores:** Interface gráfica (**JavaFX/FXML**) integrada ao ecossistema visual da Prosa Code.

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
  - v2.0.0
  - v2.1.0
- v3
  - v3.0.0
  - v3.1.0
  - v3.2.0
  - v3.3.0
- v4
  - v4.0.0
  - v4.1.0
- v5
  - v5.0.0
  - v5.1.0
```

---

## ▶️ Como Executar

1. Instalar o **Java JDK** (17 ou superior).
2. Abrir o projeto em uma IDE Java (como o Eclipse).
3. Localizar a classe `Principal`, no pacote `br.edu.principal`.
4. Executar o método `main()` e utilizar o menu apresentado no terminal.

> *Nota:* Os contatos serão carregados automaticamente quando o arquivo `contatos.txt` estiver disponível.

---

## 🛠️ Tecnologias Utilizadas

| Categoria | Tecnologia | Descrição |
| :--- | :--- | :--- |
| **Linguagem** | Java 17+ | Linguagem principal orientada a objetos (POO, pacotes, encapsulamento, construtores) |
| **Arquitetura** | Padrões MVC e DAO | Separação completa entre Model, View, Controller e persistência desacoplada |
| **Coleções** | Java Collections Framework | Estruturas dinâmicas (`List` e `ArrayList`) |
| **Persistência em Arquivo** | Java I/O (`java.io`) | Manipulação de arquivos `.txt` e tratamento de exceções via `ContatoDAO` |
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
├── 📄 contatos.txt
├── 💻 src/
│   └── 📦 br/edu/
│       ├── 🚀 principal/
│       │   └── ☕ Principal.java
│       ├── 🧩 modelo/
│       │   └── ☕ Contato.java
│       ├── 🖥️ visao/
│       │   └── ☕ AgendaView.java
│       ├── 🎮 controle/
│       │   └── ☕ AgendaController.java
│       └── 💾 dao/
│           └── ☕ ContatoDAO.java
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