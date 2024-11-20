# Casos de Uso do Sistema

---

## Atores

1. **Administrador**  
   - Responsável por gerenciar o sistema, incluindo criação, alteração e exclusão de usuários.

2. **Funcionário**  
   - Pode cadastrar, consultar e alterar informações de pessoas físicas e jurídicas.

3. **Aluno**  
   - Usuário que pode autenticar-se no sistema e consultar dados.

4. **Professor**  
   - Usuário que pode autenticar-se no sistema e consultar dados.

5. **Fornecedor**  
   - Usuário que pode autenticar-se no sistema e consultar dados.

---

## Requisitos do Sistema

1. **Autenticação de Usuário**  
   - Todo usuário deve estar autenticado para acessar funcionalidades do sistema.

2. **Cadastro de Pessoas**  
   - Deve permitir o cadastro de Pessoas Físicas e Jurídicas.

3. **Consulta de Dados**  
   - Usuários autenticados devem poder consultar informações pessoais.

4. **Alteração de Dados**  
   - Administradores e funcionários devem poder alterar dados de usuários.

5. **Exclusão de Usuários**  
   - Apenas administradores podem deletar usuários do sistema.

6. **Validação de CPF e CNPJ**  
   - O sistema deve verificar se o CPF ou CNPJ já está cadastrado e informar mensagens de erro quando necessário.

7. **Recuperação de Senha**  
   - Usuários devem poder recuperar sua conta em caso de esquecimento da senha.

8. **Bloqueio após Tentativas de Login**  
   - O sistema deve bloquear usuários após três tentativas malsucedidas de login.

---

## [UC001] Cadastrar Pessoa Física

**Atores:** Administrador, Funcionário  
**Pré-condições:**  
- Estar logado no sistema ([UC006 – Autenticar no sistema])  

**Pós-condições:**  
- Cadastra nova Pessoa Física  

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
**Pré-condições:**  
- Estar logado no sistema ([UC006 – Autenticar no sistema])  

**Pós-condições:**  
- Cadastra nova Pessoa Jurídica  

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
**Pré-condições:**  
- Cliente com conta cadastrada no sistema  

**Pós-condições:**  
- Usuário autenticado  

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
**Pré-condições:**  
- Estar logado no sistema ([UC003 – Autenticar no sistema])  

**Pós-condições:**  
- Dados listados  

### Fluxo Básico

1. O usuário acessa a tela de consulta de dados;
2. O sistema exibe os dados do usuário logado.

---

## [UC005] Alterar Dados

**Atores:** Administrador, Funcionário  
**Pré-condições:**  
- Estar logado no sistema ([UC006 – Autenticar no sistema])  

**Pós-condições:**  
- Dados alterados  

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
**Pré-condições:**  
- Estar logado no sistema ([UC006 – Autenticar no sistema])  

**Pós-condições:**  
- Usuário deletado  

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
