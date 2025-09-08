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

actor "Administrador" as Adm
actor "Secretário Acadêmico" as Sec
actor "Receita Federal" as RF

rectangle "Sistema de Cadastro" {
  usecase "Cadastrar Pessoa Física" as CPF
  usecase "Cadastrar Pessoa Jurídica" as CNPJ
  usecase "Cadastrar Professor" as Prof
  usecase "Cadastrar Aluno" as Aluno
  usecase "Cadastrar Fornecedor" as Forn
}

Adm --> CPF
Adm --> CNPJ
Adm --> Prof
Adm --> Aluno
Adm --> Forn

Sec --> Prof
Sec --> Aluno

RF --> CPF
RF --> CNPJ

## Diagrama Classes


class Pessoa {
  -id: int
  -endereco: String
  -email: String
  -telefone: String
}

class PessoaFisica {
  -cpf: String
  -rg: String
  -dataNascimento: Date
}

class PessoaJuridica {
  -cnpj: String
  -razaoSocial: String
}

class Professor {
  -disciplinas: List<String>
  -areaAtuacao: String
}

class Aluno {
  -matricula: String
  -curso: String
  -statusAcademico: String
}

class Fornecedor {
  -produtosServicos: String
  -dadosFornecimento: String
}

class Administrador {
  -login: String
  -senha: String
}

class SecretarioAcademico {
  -login: String
  -senha: String
}

class ValidacaoReceitaFederal {
  +validarCPF(cpf: String): boolean
  +validarCNPJ(cnpj: String): boolean
}

Pessoa <|-- PessoaFisica
Pessoa <|-- PessoaJuridica

PessoaFisica <|-- Professor
PessoaFisica <|-- Aluno
PessoaJuridica <|-- Fornecedor

Administrador --> Pessoa
SecretarioAcademico --> Pessoa
PessoaFisica --> ValidacaoReceitaFederal
PessoaJuridica --> ValidacaoReceitaFederal

