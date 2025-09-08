# 🎓 Sistema de Cadastro - Faculdade

---

## 🔐 Login
**Usuário:** [____________________]  
**Senha:**   [____________________]  

[Entrar]

---

## 📋 Menu Principal
Após o login, escolha uma das opções de cadastro:

- [Cadastro de Pessoa Física](#cadastro-de-pessoa-física)  
- [Cadastro de Pessoa Jurídica](#cadastro-de-pessoa-jurídica)  
- [Cadastro de Professores](#cadastro-de-professor)  
- [Cadastro de Fornecedores](#cadastro-de-fornecedores)  
- [Cadastro de Alunos](#cadastro-de-aluno)  

---

## 📑 Cadastro de Pessoa Física
**Nome Completo:** [____________________]  
**CPF:** [____________________]  

**Endereço:** [____________________] **Número:** [____]  
**CEP:** [____] **Cidade:** [____] **UF:** [__] **Complemento:** [________]  

**Contato:**  
- Telefone: [________]  
- Celular: [________]  
- E-mail: [____________________]

- [Cadastrar]

---

## 📑 Cadastro de Pessoa Jurídica
**Razão Social:** [____________________]  
**Nome Fantasia:** [____________________]  
**CNPJ:** [____________________]  

**Endereço:** [____________________] **Número:** [____]  
**CEP:** [____] **Cidade:** [____] **UF:** [__] **Complemento:** [________]  

**Contato:**  
- Telefone: [________]  
- Celular: [________]  
- E-mail: [____________________]
- [Cadastrar]

---

## 📑 Cadastro de Professor
**Nome Completo:** [____________________]  
**CPF:** [____________________]  

**Endereço:** [____________________] **Número:** [____]  
**CEP:** [____] **Cidade:** [____] **UF:** [__] **Complemento:** [________]  

**Contato:**  
- Celular: [________]  
- E-mail: [____________________]  

**Graduação:**  
- Curso: [____________________]  
- Disciplina: [____________________]
- [Cadastrar]

---

## 📑 Cadastro de Fornecedores
**Razão Social:** [____________________]  
**CNPJ:** [____________________]  

**Endereço:** [____________________] **Número:** [____]  
**CEP:** [____] **Cidade:** [____] **UF:** [__] **Complemento:** [________]  

**Contato:**  
- Telefone: [________]  
- Celular: [________]  
- E-mail: [____________________]
- [Cadastrar]

---

## 📑 Cadastro de Aluno
**Nome Completo:** [____________________]  
**Data de Nascimento:** [____________________]  
**CPF:** [____________________]  

**Endereço:** [____________________] **Número:** [____]  
**CEP:** [____] **Cidade:** [____] **UF:** [__] **Complemento:** [________]  

**Contato:**  
- Telefone: [________]  
- Celular: [________]  
- E-mail: [____________________]  

**Graduação:**  
- Curso: [____________________]  
- Disciplina: [____________________]
- [Cadastrar]

---

## Diagrama de Caso de Uso (Corrigido)

```mermaid
graph TD
    subgraph Sistema de Gestão da Universidade
        uc1["Cadastrar Pessoa Física"]
        uc2["Cadastrar Pessoa Jurídica"]
        uc3["Cadastrar Professor"]
        uc4["Cadastrar Fornecedor"]
        uc5["Cadastrar Aluno"]
        uc6["(Validar Documento)"]
    end

    ator["Administrador"] --> uc1
    ator --> uc2
    ator --> uc3
    ator --> uc4
    ator --> uc5

    uc1 --> uc6
    uc2 --> uc6
    uc3 --> uc6
    uc4 --> uc6
    uc5 --> uc6

    classDef usecase fill:#f9f,stroke:#333,stroke-width:2px;
    class uc1,uc2,uc3,uc4,uc5,uc6 usecase;
## Diagrama de Classe (Corrigido)

```mermaid
classDiagram
    class Pessoa {
        +String nome
        +Date dataNascimento
        +String endereco
        +String telefone
        +String email
        +validarDocumento(): boolean
    }

    class PessoaFisica {
        +String cpf
        +String rg
    }

    class PessoaJuridica {
        +String cnpj
        +String razaoSocial
        +String inscricaoEstadual
    }

    class Professor {
        +String idProfessor
        +String areaAtuacao
        +List<Disciplina> disciplinas
    }

    class Aluno {
        +String matricula
        +String statusAcademico
        +Curso curso
    }

    class Disciplina {
        +String codigo
        +String nome
        +String ementa
    }

    class Curso {
        +String codigoCurso
        +String nomeCurso
    }

    Pessoa <|-- PessoaFisica
    Pessoa <|-- PessoaJuridica
    PessoaFisica <|-- Professor
    PessoaFisica <|-- Aluno

    Professor "1" -- "*" Disciplina : ensina
    Aluno "*" -- "1" Curso : cursa

