## UC01 — Realizar Login

### Ator Principal
Usuário (Aluno, Recepcionista, Instrutor, Gerente)

### Objetivo
Autenticar o usuário para acesso às funcionalidades do sistema de acordo com seu perfil.

### Pré-condições
- Usuário deve possuir cadastro ativo.

### Pós-condições
- Sessão iniciada com sucesso e permissões carregadas.

### Fluxo Principal
1. O usuário informa e-mail e senha.
2. O sistema valida as credenciais.
3. O sistema autentica o usuário e redireciona para a dashboard correspondente ao perfil.

### Fluxos Alternativos
- **A1 — Credenciais incorretas:**  
  O sistema exibe mensagem de erro e solicita nova tentativa.

- **A2 — Conta bloqueada:**  
  O sistema impede o login e instrui o usuário a recuperar o acesso.

### RF Relacionados
- RF01, RF09

### RNF Relacionados
- RNF02, RNF03, RNF04

### RN Relacionadas
- RN06



## UC02 — Cadastrar Novo Aluno

### Ator Principal
Recepcionista

### Objetivo
Registrar um novo cliente na base de dados da academia.

### Pré-condições
Recepcionista autenticado no sistema.

### Pós-condições
Registro do aluno criado no banco de dados.

### Fluxo Principal
1. O recepcionista acessa o menu "Matrículas".
2. Preenche dados pessoais, contato, endereço e seleciona o plano.
3. O sistema valida os campos obrigatórios.
4. O sistema salva o cadastro e gera o ID único do aluno.

### Fluxos Alternativos
- **A1 — Dados Inválidos: O sistema destaca os campos incorretos e solicita correção.**  

### RF Relacionados
- RF01

### RNF Relacionados
- RNF02, RNF04

### RN Relacionadas
- RN06
