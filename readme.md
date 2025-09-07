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
