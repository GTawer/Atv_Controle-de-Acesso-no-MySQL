# 🔐 Controle de Acesso no MySQL — DCL

> *"Permissões definem quem pode acessar, alterar ou proteger os dados."*

![Status](https://img.shields.io/badge/Status-Concluído-brightgreen?style=for-the-badge&logo=github)
![Tecnologia](https://img.shields.io/badge/Tecnologia-MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Tema](https://img.shields.io/badge/Tema-DCL%20%7C%20Controle%20de%20Acesso-6C5CE7?style=for-the-badge&logo=database&logoColor=white)

## ◈ Descrição e objetivo

Esta atividade apresenta a implementação prática de **controle de acesso em bancos de dados MySQL**, utilizando comandos da **DCL (Data Control Language)**.

O experimento foi realizado utilizando o banco `escola_jujutsu_dcl` e a tabela `feiticeiro`, com a criação do usuário `aluno_bd` e a concessão de permissões para realizar operações de consulta e manipulação dos dados.

O objetivo foi compreender, na prática, como funciona o ciclo de **concessão, utilização e revogação de privilégios** em um banco de dados.

◆ Criar o banco de dados e a tabela.

◆ Criar o usuário `aluno_bd`.

◆ Inserir os registros iniciais.

◆ Conceder permissões de `SELECT`, `INSERT`, `UPDATE` e `DELETE`.

◆ Testar as operações utilizando o usuário `aluno_bd`.

◆ Revogar as permissões concedidas.

◆ Verificar o bloqueio do usuário após o `REVOKE`.

## 🗄️ Estrutura do projeto

| Item | Descrição |
|---|---|
| Banco de dados | `escola_jujutsu_dcl` |
| Tabela | `feiticeiro` |
| Usuário | `aluno_bd` |
| Linguagem | SQL |
| Controle | DCL |
| Permissões | SELECT, INSERT, UPDATE e DELETE |

## 🔑 Comandos DCL utilizados

### CREATE USER

O usuário `aluno_bd` foi criado para realizar os testes de acesso com permissões restritas.

    CREATE USER 'aluno_bd'@'localhost' IDENTIFIED BY 'senha';

### GRANT

Foram concedidas permissões para consultar e manipular os registros da tabela `feiticeiro`.

    GRANT SELECT, INSERT, UPDATE, DELETE
    ON escola_jujutsu_dcl.feiticeiro
    TO 'aluno_bd'@'localhost';

### REVOKE

Após a realização dos testes, as permissões concedidas ao usuário foram revogadas.

    REVOKE ALL PRIVILEGES
    ON escola_jujutsu_dcl.feiticeiro
    FROM 'aluno_bd'@'localhost';

## 🧪 Testes realizados

Após a criação e concessão das permissões, foi realizada uma nova conexão utilizando o usuário `aluno_bd`.

Foram testadas as seguintes operações:

◆ **SELECT** — consulta dos dados cadastrados.

◆ **INSERT** — inserção de um novo registro.

◆ **UPDATE** — alteração de um registro existente.

◆ **DELETE** — exclusão de um registro.

Os testes confirmaram o funcionamento das permissões concedidas ao usuário limitado.

## 🚫 Revogação e bloqueio

Depois da confirmação das operações, foi utilizada a conexão de administrador para executar o `REVOKE` e remover os privilégios do usuário `aluno_bd`.

Em seguida, uma nova tentativa de acesso foi realizada com o usuário limitado.

O MySQL bloqueou as operações por falta de privilégios, apresentando mensagens de erro relacionadas às permissões de acesso.

## 🖥️ Registros da atividade

#### 01 — Criação do usuário e Concessão das permissões 

  <img src="https://github.com/GTawer/Controle-de-Acesso-no-MySQL/blob/main/imgs/2.png" alt="Listagem de clientes" width="65%" />
</div>


#### 02 — Criação do banco e da tabela

  <img src="https://github.com/GTawer/Controle-de-Acesso-no-MySQL/blob/main/imgs/1.png" alt="Listagem de clientes" width="40%" />
</div>


#### 03 — Acesso utilizando `aluno_bd`

  <img src="https://github.com/GTawer/Controle-de-Acesso-no-MySQL/blob/main/imgs/3.png" alt="Listagem de clientes" width="50%" />
</div>


#### 04 — Execução das operações

  <img src="https://github.com/GTawer/Controle-de-Acesso-no-MySQL/blob/main/imgs/4.png" alt="Listagem de clientes" width="40%" />
</div>

### 05 — Revogação das permissões

  <img src="https://github.com/GTawer/Controle-de-Acesso-no-MySQL/blob/main/imgs/5.png" alt="Listagem de clientes" width="50%" />
</div>


#### 06 — Tentativa de acesso após o REVOKE

  <img src="https://github.com/GTawer/Controle-de-Acesso-no-MySQL/blob/main/imgs/6.png" alt="Listagem de clientes" width="50%" />
</div>


## 🧠 Conceitos praticados

◆ **DCL (Data Control Language)**

◆ Criação e gerenciamento de usuários.

◆ Controle de privilégios em bancos de dados.

◆ `CREATE USER`

◆ `GRANT`

◆ `REVOKE`

◆ Operações DML: `SELECT`, `INSERT`, `UPDATE` e `DELETE`.

◆ Controle de acesso e segurança de dados.

## 🛠️ Tecnologias e ferramentas utilizadas

◆ **MySQL** — gerenciamento do banco de dados.

◆ **MySQL Workbench** — criação de conexões e execução dos comandos SQL.

◆ **SQL** — linguagem utilizada para manipulação e controle do banco.

## ◈ Resultado

A atividade permitiu compreender e comprovar, na prática, o funcionamento dos mecanismos de controle de acesso do MySQL.

Primeiramente, o usuário `aluno_bd` recebeu permissões para realizar operações de consulta e manipulação na tabela `feiticeiro`. Após os testes, seus privilégios foram revogados e novas tentativas de acesso foram bloqueadas pelo sistema por falta de permissão.

## 🎓 Atividade acadêmica

Esta atividade faz parte das aulas de **Banco de Dados / Linguagem SQL** do curso **Técnico em Desenvolvimento de Sistemas** do **SENAI**.

O exercício teve como objetivo compreender o funcionamento do **controle de acesso em bancos de dados utilizando comandos DCL**, principalmente `CREATE USER`, `GRANT` e `REVOKE`.

A atividade também permitiu testar o ciclo completo de **criação de usuário, concessão de privilégios, execução de operações, revogação de acesso e verificação dos bloqueios de segurança**.

---

## 👾 Autoria

- **Aluno:** Gabriel de Araujo Torres (Nº 08)
- **Disciplina:** Banco de Dados / Linguagem SQL
- **Atividade:** Controle de Acesso no MySQL — DCL
- **Data:** 22/09/2026

#### Projeto desenvolvido no SENAI A. Jacob Lafer.

---

<p align="center">
  <img src="https://media.tenor.com/2Xnh-2tG8pYAAAAi/scott-pilgrim-scott-pilgrim-takes-off.gif" width="275" height="auto" alt="Scott Pilgrim GIF" />
</p>

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-GTawer-181717?style=for-the-badge&logo=github)](https://github.com/GTawer)

**🔐 MySQL • SQL • DCL • SENAI**

<sub>*Projeto acadêmico desenvolvido para prática de controle de acesso em bancos de dados.*</sub>

</div>
