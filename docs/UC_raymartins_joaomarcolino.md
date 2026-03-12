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
- **A1 — Credenciais Incorretas:**  
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
- **A1 — Dados Inválidos:**  
O sistema destaca os campos incorretos e solicita correção.

### RF Relacionados
- RF01

### RNF Relacionados
- RNF02, RNF04

### RN Relacionadas
- RN06



## UC03 — Gerenciar Tipos de Planos

### Ator Principal
Gerente

### Objetivo
Criar ou editar as modalidades de planos oferecidas pela academia.

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Plano atualizado ou criado na base de dados.

### Fluxo Principal
1. O gerente acessa "Configurações de Planos".
2. Define nome, valor, duração e descrição.
3. O sistema salva as alterações.

### Fluxos Alternativos
- **A1 — Desativar Plano:**
O gerente seleciona um plano existente e marca como "Inativo".

### RF Relacionados
- RF02

### RNF Relacionados
- RNF04

### RN Relacionadas
- RN06



## UC04 — Registrar Pagamento na Recepção

### Ator Principal
Recepcionista

### Objetivo
Processar o pagamento presencial de mensalidades.

### Pré-condições
- Aluno identificado no sistema.

### Pós-condições
- Status de pagamento atualizado e recibo gerado.

### Fluxo Principal
1. O recepcionista seleciona a parcela em aberto do aluno.
2. Escolhe o método (Dinheiro, Cartão ou PIX).
3. O sistema processa a transação e confirma o recebimento integral.
4. O sistema atualiza a regularidade do aluno instantaneamente.

### Fluxos Alternativos
- **A1 — Pagamento Parcial:**
O sistema bloqueia a operação informando que apenas valores integrais são aceitos.

### RF Relacionados
- RF03, RF04

### RNF Relacionados
- RNF02, RNF03

### RN Relacionadas
- RN04, RN07



## UC05 — Validar Acesso na Catraca (RFID)

### Ator Principal
Sistema de Catraca (API)

### Objetivo
Controlar a entrada física do aluno na unidade.

### Pré-condições
- Aluno aproxima o cartão/tag RFID no leitor.

### Pós-condições
- Acesso liberado ou bloqueado.

### Fluxo Principal
1. A API da catraca envia o ID do RFID para o sistema FitPass.
2. O sistema verifica a regularidade financeira do aluno.
3. O sistema retorna o comando de "Liberar" para a catraca.

### Fluxos Alternativos
- **A1 — Inadimplência (> 5 dias):**
O sistema retorna comando "Bloquear" e exibe mensagem na tela da catraca.
- **A2 — Plano Inativo:
O sistema nega o acesso.

### RF Relacionados
- RF04, RF05

### RNF Relacionados
- RNF03, RNF06

### RN Relacionadas
- RN01
