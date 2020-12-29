# Recuperação de senha

**RF (Requisitos Funcionais)**

- O usuário deve poder recuperar sua senha informando o seu e-mail;
- O usuário deve receber um e-mail com instruções de recuperação de senha;
- O usuário deve poder resetar sua senha;

**RNF (Requisitos Não Funcionais)**

- Utilizar Mailtrap para testar envios em ambiente de desenvolvimento;
- Utilizar Amazon SES para envios em produção;
- O envio de e-mails deve acontecer em segundo plano (background job);

**RN (Regras de Negócio)**

- O link enviado por e-mail para resetar a senha, deve expirar em 2 horas;
- O usuário precisa confirmar a nova senha ao resetá-la;

# Atualização do perfil

**RF (Requisitos Funcionais)**

- O usuário deve poder atualizar seu nome, e-mail e senha;

**RNF (Requisitos Não Funcionais)**

**RN (Regras de Negócio)**

- O usuário não pode alterar seu e-mail por outro já utilizado;
- Para atualizar sua senha, o usuário deve informar a senha antiga;
- Para atualizar sua senha, o usuário precisa confirmar a nova senha;

# Painel do prestador

**RF (Requisitos Funcionais)**

- O usuário deve poder listar seus agendamentos de um dia específico;
- O prestador deve receber uma notificação sempre que houver um novo agendamento;
- O prestador deve poder visualizar as notificações não lidas;

**RNF (Requisitos Não Funcionais)**

- Os agendamentos do prestador no dia devem ser armazenados em cache;
- As notificações do prestador devem ser armazenadas no MongoDB;
- As notificações do prestador devem ser enviadas em tempo-real utilizando Socket.io;

**RN (Regras de Negócio)**

- A notificação deve ter um status de lida ou não-lida para que o prestador possa controlar;

# Agendamento de serviços

**RF (Requisitos Funcionais)**

- O usuário deve poder listar todos prestadores de serviços cadastrados;
- O usuário deve poder listar os dias de um mês com pelo menos um horário disponível de um prestador;
- O usuário deve poder listar horários disponíveis em um dia específico de um prestador;
- O usuário deve poder realizar um novo agendamento com um prestador;

**RNF (Requisitos Não Funcionais)**

- A listagem de prestadores deve ser armazenada em cache;

**RN (Regras de Negócio)**

- Cada agendamento deve durar 1 hora exatamente;
- Os agendamentos devem estar disponíveis entre 8h às 18h (Primeiro horário às 8h, último às 17h);
- O usuário não pode agendar em um horário já ocupado;
- O usuário não pode agendar em um horário que já passou;
- O usuário não pode agendar serviços consigo mesmo;