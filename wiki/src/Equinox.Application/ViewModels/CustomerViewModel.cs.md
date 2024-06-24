# CustomerViewModel.cs: Modelo de Visualização do Cliente

## Visão Geral
Este arquivo define uma estrutura de dados chamada `CustomerViewModel`. Esta estrutura é usada para representar um cliente em uma aplicação, contendo informações como ID, Nome, E-mail e Data de Nascimento.

## Fluxo do Processo
Como este arquivo é uma estrutura de dados, não há um fluxo de processo. No entanto, os atributos da estrutura `CustomerViewModel` são:

| Atributo | Tipo | Descrição |
| --- | --- | --- |
| Id | Guid | Identificador único do cliente |
| Name | string | Nome do cliente |
| Email | string | E-mail do cliente |
| BirthDate | DateTime | Data de nascimento do cliente |

## Insights
- A estrutura `CustomerViewModel` é usada para representar um cliente na aplicação.
- Todos os campos são obrigatórios, conforme indicado pelas anotações `[Required]`.
- O campo `Name` tem um comprimento mínimo de 2 caracteres e um comprimento máximo de 100 caracteres.
- O campo `Email` deve ser um endereço de e-mail válido.
- O campo `BirthDate` deve ser uma data válida e é exibido no formato "yyyy-MM-dd".

## Vulnerabilidades
- O campo `Email` pode ser vulnerável a ataques de injeção se não for devidamente sanitizado antes de ser usado em consultas SQL ou outros comandos que aceitam entrada do usuário.
- O campo `Name` pode ser vulnerável a ataques de overflow de buffer se o comprimento da entrada não for verificado antes de ser usado.
- A falta de criptografia ou hashing para o campo `Email` pode expor informações sensíveis se os dados forem interceptados ou o banco de dados for comprometido.