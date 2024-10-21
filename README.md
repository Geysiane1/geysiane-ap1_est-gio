# Sistemas de Agendamento de Laboratórios

Este projeto é uma aplicação web que permite professores agendarem laboratórios para suas atividades, gerenciar reservas e consultar a disponibilidade de laboratórios.

● FUNCIONALIDADES PRINCIPAIS: 

- Cadastro de Professores: Permite que professores se cadastrem no sistema.

- Login de Professores: Autenticação segura de professores cadastradas.

- Listagem de Laboratórios: Exibe todos os laboratórios disponíveis para reserva.

- Agendamento de Laboratórios: Professores podem reservar laboratórios para datas e horários específicos.

- Consulta de Agendamentos: Visualização dos agendamentos de laboratórios em datas específicas.

- Atualização de Agendamento: Permite editar detalhes de um agendamento existente.

- Exclusão de Agendamento: Permite remover agendamentos do sistema.


● DEFINIÇÃO DO BANCO DE DADOS

O banco de dados do sistema é estruturado da seguinte forma:

> ENTIDADES:

- users: (Professores)

- id: Identificador único (PK)

- name: Nome do professor(STRING)

- email: Email do professor (STRING)

- password: Senha criptografada (STRING)

/

- labs (Laboratórios)

- id: Identificador único (PK)

- name: Nome do laboratório (STRING)

- bookings (Agendamentos)

/

- id: Identificador único (PK)

- user_id: Chave estrangeira referenciando a tabela de professores (FK)
  
- lab_id: Chave estrangeira referenciando a tabela de laboratórios (FK)

- date: Data do agendamento (STRING ou formato de data)

- time: Horário do agendamento (STRING)
  
● RELACIONAMENTOS:
- users possuem uma relação de um-para-muitos com bookings (um professor pode fazer vários agendamentos).

- labs possuem uma relação de um-para-muitos com bookings (um laboratório pode ser reservado várias vezes).


● Rotas da API (CRUD Funcional)
A aplicação utiliza ExpressJS para implementar as seguintes rotas:

- Cadastro de Professores:
POST /register: Criptografa a senha e cadastra os professores no sistema.

- Login de Professora:
POST /login: Autentica os professores registradps e retorna um token de sessão.

- Listar Laboratórios:
GET /labs: Exibe a lista de todos os laboratórios disponíveis para reserva.

- Agendar Laboratório:
POST /book: Permite que um professor reserve um laboratório para uma data e horário específicos.

- Listar Agendamentos:
GET /bookings: Exibe os agendamentos de um laboratório em uma data específica.

- Atualizar Agendamento:
PUT /bookings/:id: Atualiza os detalhes de um agendamento existente.

- Excluir Agendamento:
DELETE /bookings/:id: Remove um agendamento existente.


□ DIAGRAMA DE ROTAS 
Abaixo está um diagrama ilustrando as principais rotas da API:


■ TECNOLOGIAS UTILIZADAS:
Node.js e ExpressJS para o backend.
MySQL ou PostgreSQL para o banco de dados.
BCrypt para criptografia de senhas.
