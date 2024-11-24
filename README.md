# Sistema da Universidade

Este projeto tem como objetivo apresentar um modelagem de um Sistema de Gestão de Dados para uma universidade fictícia.
Esses processos são representados por diagramas UML, como o Diagrama de Casos de Uso e o Diagrama de Classes e a descriação dos cenários do programa.
Através dessa modelagem, é possível entender o processo de cadastro, consulta e exclusão de dados, de pessoas físicas e jurídicas, que podem ser realizados. 

---

## Atores
- **Administrador**: Responsável por gerenciar o sistema, incluindo criação, alteração e exclusão de usuários.
- **Funcionário**: Pode cadastrar, consultar e alterar informações de pessoas físicas e jurídicas.
- **Aluno**: Usuário que pode autenticar-se no sistema e consultar dados.
- **Professor**: Usuário que pode autenticar-se no sistema e consultar dados.
- **Fornecedor**: Usuário que pode autenticar-se no sistema e consultar dados.

---

## Cenários do Sistema
1. [[UC001] Autenticação de Usuário](#uc003-autenticar-no-sistema)
2. [[UC002] Cadastro de Pessoas](#uc001-cadastrar-pessoa-física)
3. [[UC003] Consulta de Dados](#uc004-consultar-dados)
4. [[UC004] Alteração de Dados](#uc005-alterar-dados)
5. [[UC005] Exclusão de Usuários](#uc006-deletar-usuário)
6. [[UC006] Validação de CPF e CNPJ](#uc001-cadastrar-pessoa-física)
7. [[UC007] Recuperação de Senha](#fluxo-alternativo-3--usuário-esqueceu-a-senha)
8. [[UC008] Bloqueio após Tentativas de Login](#fluxo-de-exceção--excesso-de-tentativas)

---

## Telas do Sistema
1. [Tela de login](#1---tela-de-login)  
2. [Cadastrar aluno (Através da tela de login)](#2---cadastrar-aluno-através-da-tela-de-login)  
3. [Solicitar uma nova senha](#3---solicitar-uma-nova-senha)  
4. [Cadastrar uma nova senha](#4---cadastrar-uma-nova-senha)  
5. [Tela de início](#5---tela-de-início)  
6. [Meu cadastro](#6---meu-cadastro)  
7. [Cadastrar novo usuário](#7---cadastrar-novo-usuário)  
8. [Consultar dados](#8---consultar-dados)  
9. [Alteração de dados](#9---alteração-de-dados)  
10. [Deletar usuário](#10---deletar-usuário)  

---

## Diagramas do Sistema
1. [Diagrama de Casos de Uso](#diagrama-de-casos-de-uso)  
2. [Diagrama de Classes](#diagrama-de-classes) 

---

## [UC001] Cadastrar Pessoa Física

**Atores:** Administrador, Funcionário  
**Pré-condições:** Estar logado no sistema ([UC006 – Autenticar no sistema])  
**Pós-condições:** Cadastra nova Pessoa Física  

### Fluxo Básico

1. O usuário acessa a tela de Cadastro de Pessoa Física;
2. O usuário seleciona o tipo de Pessoa Física;
3. O usuário digita as informações solicitadas;
4. O usuário confirma os dados colocados;
5. O sistema confirma o cadastro de nova Pessoa Física;
6. O sistema retorna à tela de Cadastro de Pessoa Física.

### Fluxo Alternativo 1 – CPF já cadastrado

1. No passo 4, se o sistema encontra um cadastro já existente com o CPF digitado:
2. O sistema exibe uma mensagem informando que o CPF colocado não é válido;
3. Retorna ao passo 1 do fluxo básico.

---

## [UC002] Cadastrar Pessoa Jurídica

**Atores:** Administrador, Funcionário  
**Pré-condições:** Estar logado no sistema ([UC006 – Autenticar no sistema])  
**Pós-condições:** Cadastra nova Pessoa Jurídica  

### Fluxo Básico

1. O usuário acessa a tela de Cadastro de Pessoa Jurídica;
2. O usuário seleciona o tipo de Pessoa Jurídica;
3. O usuário digita as informações solicitadas;
4. O usuário confirma os dados colocados;
5. O sistema confirma o cadastro de nova Pessoa Jurídica;
6. O sistema retorna à tela de Cadastro de Pessoa Jurídica.

### Fluxo Alternativo 1 – CNPJ já cadastrado

1. No passo 4, se o sistema encontra um cadastro já existente com o CNPJ digitado:
2. O sistema exibe uma mensagem informando que o CNPJ colocado não é válido;
3. Retorna ao passo 1 do fluxo básico.

---

## [UC003] Autenticar no Sistema

**Atores:** Administrador, Funcionário, Aluno, Professor e Fornecedor  
**Pré-condições:** Cliente com conta cadastrada no sistema  
**Pós-condições:** Usuário autenticado  

### Fluxo Básico

1. O sistema exibe a tela de login;
2. O usuário insere seu nome de usuário e senha;
3. O usuário confirma seus dados;
4. O sistema autentica o usuário com sucesso;
5. O sistema exibe a tela inicial.

### Fluxo Alternativo 1 – Aluno não cadastrado

1. O sistema solicita os dados para cadastro de nova conta de aluno;
2. O aluno digita as informações solicitadas;
3. O sistema confirma o cadastro de novo aluno;
4. O sistema retorna ao passo 1 do fluxo principal.

### Fluxo Alternativo 2 – Dados inválidos

1. O sistema exibe uma mensagem de falha de login;
2. O sistema retorna ao passo 1 do fluxo principal.

### Fluxo Alternativo 3 – Usuário esqueceu a senha

1. O usuário solicita a redefinição de senha por email;
2. O sistema envia um email ao usuário com um link para redefinição de senha;
3. O usuário acessa o email e clica no link;
4. O usuário cadastra uma nova senha;
5. O usuário confirma os dados;
6. O usuário confirma a alteração;
7. O sistema redireciona o cliente ao passo 1 do fluxo principal.

### Fluxo de Exceção – Excesso de tentativas

Após 3 tentativas de login:
1. O sistema bloqueia a conta do usuário;
2. O sistema exibe uma opção de recuperação da conta;
3. O usuário confirma o email de recuperação;
4. O sistema envia um link para redefinição da conta;
5. O usuário cadastra uma nova senha;
6. O sistema redireciona o usuário ao passo 1 do fluxo principal.

---

## [UC004] Consultar Dados

**Atores:** Administrador, Funcionário, Aluno, Professor e Fornecedor  
**Pré-condições:** Estar logado no sistema ([UC003 – Autenticar no sistema])  
**Pós-condições:** Dados listados  

### Fluxo Básico

1. O usuário acessa a tela de consulta de dados;
2. O sistema exibe os dados do usuário logado.

---

## [UC005] Alterar Dados

**Atores:** Administrador, Funcionário  
**Pré-condições:** Estar logado no sistema ([UC006 – Autenticar no sistema])  
**Pós-condições:** Dados alterados  

### Fluxo Básico

1. O usuário acessa a tela de alteração de dados;
2. O usuário digita o CPF ou CNPJ;
3. O usuário confirma ação;
4. O sistema exibe os dados do CPF/CNPJ colocado;
5. O usuário seleciona qual dado deseja alterar;
6. O usuário digita o novo dado;
7. O usuário confirma a alteração;
8. O dado é alterado.

### Fluxo Alternativo 1 – Nenhum CPF/CNPJ encontrado

1. No passo 4, se o sistema não encontrar usuários correspondentes ao CPF/CNPJ digitado:
2. O sistema exibe uma mensagem informando que nenhum dado foi encontrado;
3. Retorna ao passo 1 do fluxo básico.

---

## [UC006] Deletar Usuário

**Atores:** Administrador  
**Pré-condições:** Estar logado no sistema ([UC006 – Autenticar no sistema])  
**Pós-condições:** Usuário deletado  

### Fluxo Básico

1. O Administrador acessa a tela de deletar usuário;
2. O Administrador digita o CPF ou CNPJ;
3. O sistema exibe os dados do CPF/CNPJ colocado;
4. O Administrador confirma a ação;
5. O usuário pertencente ao CPF/CNPJ colocado é deletado do sistema.

### Fluxo Alternativo 1 – Nenhum CPF/CNPJ encontrado

1. No passo 3, se o sistema não encontrar usuários correspondentes ao CPF/CNPJ digitado:
2. O sistema exibe uma mensagem informando que nenhum dado foi encontrado;
3. Retorna ao passo 1 do fluxo básico.

## Imagens das Telas do Sistema

### 1 - Tela de login
![Tela de login](https://i.ibb.co/stZGPXV/1-Tela-de-login.png)

### 2 - Cadastrar aluno
![Cadastrar aluno](https://i.ibb.co/WFQ2DLK/2-Cadastra-aluno-Atrav-s-da-tela-de-login.png)

### 3 - Solicitar uma nova senha
![Solicitar uma nova senha](https://i.ibb.co/S3gpnH7/3-Solicitar-uma-nova-senha.png)

### 4 - Cadastrar uma nova senha
![Cadastrar uma nova senha](https://i.ibb.co/8ssL4MZ/4-Cadastrar-uma-nova-senha.png)

### 5 - Tela de início
![Tela de início](https://i.ibb.co/zRsqX0c/5-Tela-de-in-cio.png)

### 6 - Meu cadastro
![Meu cadastro](https://i.ibb.co/8KndSKQ/6-Meu-cadastro.png)

### 7 - Cadastrar novo usuário
![Cadastrar novo usuário](https://i.ibb.co/hfkVVx7/7-Cadastrar-novo-usuario.png)

### 8 - Consultar dados
![Consultar dados](https://i.ibb.co/GFNfdWL/8-Consultar-dados.png)

### 9 - Alteração de dados
![Alteração de dados](https://i.ibb.co/8j5FhZW/9-Altera-o-de-dados.png)

### 10 - Deletar usuário
![Deletar usuário](https://i.ibb.co/MS3Rf98/10-Deletar-usu-rio.png)

---

## Diagramas do Sistema

### Diagrama de Casos de Uso
![Diagrama de Casos de Uso](https://i.ibb.co/q7tQm3w/Diagrama-caso-de-uso.png)

### Diagrama de Classes
![Diagrama de Classes](https://i.ibb.co/4FnCVHZ/Diagrama-de-classe.png)
